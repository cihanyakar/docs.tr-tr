---
title: "Mimari ve tasarım"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f0dcad5d6287d5399dac6cea38b10984781770f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/18/2017
---
# <a name="architecture-and-design"></a><span data-ttu-id="7c902-102">Mimari ve tasarım</span><span class="sxs-lookup"><span data-stu-id="7c902-102">Architecture and Design</span></span>
<span data-ttu-id="7c902-103">SQL nesil modülünde [örnek sağlayıcı](http://go.microsoft.com/fwlink/?LinkId=180616) ziyaretçisi komut ağacı temsil eden ifade ağaç olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="7c902-103">The SQL generation module in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="7c902-104">Nesil tek geçişte ifade ağacına yapılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-104">The generation is done in a single pass over the expression tree.</span></span>  
  
 <span data-ttu-id="7c902-105">Ağaç düğümleri aşağıdan yukarı işlenir.</span><span class="sxs-lookup"><span data-stu-id="7c902-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="7c902-106">İlk olarak, bir ara yapısı üretilen: SqlSelectStatement veya SqlBuilder, hem uygulama ISqlFragment.</span><span class="sxs-lookup"><span data-stu-id="7c902-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="7c902-107">Ardından, SQL deyimini dize bu yapısından oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="7c902-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="7c902-108">Ara yapısı iki nedeni vardır:</span><span class="sxs-lookup"><span data-stu-id="7c902-108">There are two reasons for the intermediate structure:</span></span>  
  
-   <span data-ttu-id="7c902-109">Mantıksal olarak, SQL SELECT deyimine bozuk doldurulur.</span><span class="sxs-lookup"><span data-stu-id="7c902-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="7c902-110">FROM yan tümcesinde katılmak düğümleri, WHERE, GROUP BY ve ORDER BY yan tümcesi içinde katılmak düğümleri önce ziyaret edilen.</span><span class="sxs-lookup"><span data-stu-id="7c902-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="7c902-111">Diğer adlar yeniden adlandırmak için yeniden adlandırma sırasında çakışmaları önlemek için tüm kullanılan diğer adlarını tanımlamanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="7c902-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="7c902-112">SqlBuilder içinde yeniden adlandırma seçenekler erteleme simgenin nesneleri yeniden adlandırmak için adaylar sütunları göstermek için kullanın.</span><span class="sxs-lookup"><span data-stu-id="7c902-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>  
  
 <span data-ttu-id="7c902-113">![Diyagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="7c902-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>  
  
 <span data-ttu-id="7c902-114">İfade ağacına ziyaret sırasında ilk aşamasında, ifadeleri SqlSelectStatements gruplandırılır, birleştirmeler düzleştirilmiş ve birleştirme diğer adlar düzleştirilmiş.</span><span class="sxs-lookup"><span data-stu-id="7c902-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="7c902-115">Bu geçişi sırasında simgesi nesneleri, sütunları veya adlandırılabilir giriş diğer adı temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7c902-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>  
  
 <span data-ttu-id="7c902-116">Gerçek dize oluşturan sırasında ikinci aşamasında, diğer adlar yeniden adlandırılmıştır.</span><span class="sxs-lookup"><span data-stu-id="7c902-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>  
  
## <a name="data-structures"></a><span data-ttu-id="7c902-117">Veri yapıları</span><span class="sxs-lookup"><span data-stu-id="7c902-117">Data Structures</span></span>  
 <span data-ttu-id="7c902-118">Bu bölümde kullanılan türleri açıklanmaktadır [örnek sağlayıcı](http://go.microsoft.com/fwlink/?LinkId=180616) bir SQL deyimi oluşturmak için kullanın.</span><span class="sxs-lookup"><span data-stu-id="7c902-118">This section discusses the types used in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) that you use to build a SQL statement.</span></span>  
  
### <a name="isqlfragment"></a><span data-ttu-id="7c902-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="7c902-119">ISqlFragment</span></span>  
 <span data-ttu-id="7c902-120">Bu bölüm iki amaca hizmet eder ISqlFragment arabirimini uygulayan sınıflar kapsar:</span><span class="sxs-lookup"><span data-stu-id="7c902-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>  
  
-   <span data-ttu-id="7c902-121">Tüm ziyaretçi yöntemleri için ortak bir dönüş türü.</span><span class="sxs-lookup"><span data-stu-id="7c902-121">A common return type for all the visitor methods.</span></span>  
  
-   <span data-ttu-id="7c902-122">Son SQL dizesi yazmak için bir yöntem sağlar.</span><span class="sxs-lookup"><span data-stu-id="7c902-122">Gives a method to write the final SQL string.</span></span>  
  
```  
internal interface ISqlFragment {  
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);  
}  
```  
  
#### <a name="sqlbuilder"></a><span data-ttu-id="7c902-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="7c902-123">SqlBuilder</span></span>  
 <span data-ttu-id="7c902-124">SqlBuilder son SQL dizesi için StringBuilder için benzer bir toplama aygıttır.</span><span class="sxs-lookup"><span data-stu-id="7c902-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="7c902-125">Dizeleri dönüştürülebilir ISqlFragments birlikte en son SQL oluşturan dizeleri oluşur.</span><span class="sxs-lookup"><span data-stu-id="7c902-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>  
  
```  
internal sealed class SqlBuilder : ISqlFragment {  
   public void Append(object s)  
   public void AppendLine()  
   public bool IsEmpty  
}  
```  
  
#### <a name="sqlselectstatement"></a><span data-ttu-id="7c902-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="7c902-126">SqlSelectStatement</span></span>  
 <span data-ttu-id="7c902-127">Kurallı SQL SELECT deyimine "seçin... şeklin SqlSelectStatement temsil eder</span><span class="sxs-lookup"><span data-stu-id="7c902-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="7c902-128">KAYNAK..</span><span class="sxs-lookup"><span data-stu-id="7c902-128">FROM  ..</span></span> <span data-ttu-id="7c902-129">WHERE...</span><span class="sxs-lookup"><span data-stu-id="7c902-129">WHERE …</span></span> <span data-ttu-id="7c902-130">GRUPLANDIRMA ÖLÇÜTÜ...</span><span class="sxs-lookup"><span data-stu-id="7c902-130">GROUP BY …</span></span> <span data-ttu-id="7c902-131">SIRALAMA ÖLÇÜTÜ".</span><span class="sxs-lookup"><span data-stu-id="7c902-131">ORDER BY".</span></span>  
  
 <span data-ttu-id="7c902-132">Her SQL yan tümceleri StringBuilder temsil edilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="7c902-133">Ayrıca, DISTINCT belirtilen olup olmadığını ve deyim en üstteki olup olmadığını izler.</span><span class="sxs-lookup"><span data-stu-id="7c902-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="7c902-134">Deyim en üstteki değilse, deyim de TOP yan tümcesinde bulunmadığı sürece ORDER BY yan tümcesi atlanır.</span><span class="sxs-lookup"><span data-stu-id="7c902-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>  
  
 <span data-ttu-id="7c902-135">FromExtents SELECT deyimi girdileri listesini içerir.</span><span class="sxs-lookup"><span data-stu-id="7c902-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="7c902-136">Yoktur genellikle yalnızca tek bir öğede bu.</span><span class="sxs-lookup"><span data-stu-id="7c902-136">There is usually just one element in this.</span></span> <span data-ttu-id="7c902-137">SELECT deyimleri birleştirmelerde geçici olarak birden fazla öğe olabilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-137">SELECT statements for joins may temporarily have more than one element.</span></span>  
  
 <span data-ttu-id="7c902-138">SELECT deyimi bir birleşim düğümü tarafından oluşturduysanız, SqlSelectStatement AllJoinExtents birleştirmeye düzleştirilmiş tüm uzantıların listesini tutar.</span><span class="sxs-lookup"><span data-stu-id="7c902-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="7c902-139">OuterExtents SqlSelectStatement dış başvuruları temsil eder ve giriş diğer adı yeniden adlandırmak için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>  
  
```  
internal sealed class SqlSelectStatement : ISqlFragment {  
   internal bool IsDistinct { get, set };  
   internal bool IsTopMost  
  
   internal List<Symbol> AllJoinExtents { get, set };  
   internal List<Symbol> FromExtents { get};  
   internal Dictionary<Symbol, bool> OuterExtents { get};  
  
   internal TopClause Top { get, set };  
  
   internal SqlBuilder Select {get};  
   internal SqlBuilder From  
   internal SqlBuilder Where  
   internal SqlBuilder GroupBy  
   public SqlBuilder OrderBy  
}  
```  
  
#### <a name="topclause"></a><span data-ttu-id="7c902-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="7c902-140">TopClause</span></span>  
 <span data-ttu-id="7c902-141">TopClause bir SqlSelectStatement üst ifadesinde temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7c902-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="7c902-142">TopCount özelliği üst satır sayısını seçilmelidir gösterir.</span><span class="sxs-lookup"><span data-stu-id="7c902-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="7c902-143">WithTies true olduğunda, TopClause DbLimitExpession üretilmiştir.</span><span class="sxs-lookup"><span data-stu-id="7c902-143">When WithTies is true, the TopClause was built from a DbLimitExpession.</span></span>  
  
```  
class TopClause : ISqlFragment {  
   internal bool WithTies {get}  
   internal ISqlFragment TopCount {get}  
   internal TopClause(ISqlFragment topCount, bool withTies)  
   internal TopClause(int topCount, bool withTies)  
}  
```  
  
### <a name="symbols"></a><span data-ttu-id="7c902-144">Simgeleri</span><span class="sxs-lookup"><span data-stu-id="7c902-144">Symbols</span></span>  
 <span data-ttu-id="7c902-145">Simge ile ilgili sınıflar ve simge tablosunu giriş diğer adı yeniden adlandırma, diğer ad JOIN düzleştirme ve sütun diğer adı yeniden adlandırma gerçekleştirin.</span><span class="sxs-lookup"><span data-stu-id="7c902-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>  
  
 <span data-ttu-id="7c902-146">Sembol sınıfı bir kapsam, iç içe geçmiş bir SELECT deyimi veya bir sütunu temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7c902-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="7c902-147">Gerçek bir diğer ad yerine kullanılmış ve ayrıca (türü gibi) temsil eden yapı için ek bilgi taşıyan sonra yeniden adlandırma işlemi için izin vermek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>  
  
```  
class Symbol : ISqlFragment {  
   internal Dictionary<string, Symbol> Columns {get}  
   internal bool NeedsRenaming {get, set}  
   internal bool IsUnnest {get, set}   //not used  
  
   public string Name{get}  
   public string NewName {get,set}  
   internal TypeUsage Type {get, set}  
  
   public Symbol(string name, TypeUsage type)  
}  
```  
  
 <span data-ttu-id="7c902-148">Gösterilen azami ölçüde, iç içe geçmiş SELECT deyimi veya bir sütun özgün diğer adını depolar.</span><span class="sxs-lookup"><span data-stu-id="7c902-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>  
  
 <span data-ttu-id="7c902-149">NewName kullanılacak olan diğer SQL SELECT deyiminde depolar.</span><span class="sxs-lookup"><span data-stu-id="7c902-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="7c902-150">Bu özgün adına ayarlayın ve yalnızca son dizede sorgu oluşturulurken gerektiğinde yeniden adlandırıldı.</span><span class="sxs-lookup"><span data-stu-id="7c902-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>  
  
 <span data-ttu-id="7c902-151">Türü yalnızca kapsam ve iç içe geçmiş SELECT deyimi temsil eden simgelerini yararlıdır.</span><span class="sxs-lookup"><span data-stu-id="7c902-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>  
  
#### <a name="symbolpair"></a><span data-ttu-id="7c902-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="7c902-152">SymbolPair</span></span>  
 <span data-ttu-id="7c902-153">SymbolPair sınıfı kayıt düzleştirme giderir.</span><span class="sxs-lookup"><span data-stu-id="7c902-153">The SymbolPair class addresses record flattening.</span></span>  
  
 <span data-ttu-id="7c902-154">Bir özellik ifadesi (v, "j3.j2.j1.a.x") D VarRef, j1, j2 v olduğu düşünün, j3 birleştirme, bir bir kapsam, x ise bir sütun.</span><span class="sxs-lookup"><span data-stu-id="7c902-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>  
  
 <span data-ttu-id="7c902-155">Bu içine süre sonra çevrilmesi gerekiyor {j'}. {x'}.</span><span class="sxs-lookup"><span data-stu-id="7c902-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="7c902-156">Kaynak alanı birleştirme ifadesi (deyin j2); temsil eden dıştaki SqlStatement temsil eder her zaman bir birleşim simge budur.</span><span class="sxs-lookup"><span data-stu-id="7c902-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="7c902-157">Bir birleştirme dışı simgeyi durduruluncaya kadar sütun alanı bir birleşim simgesini diğerine taşır.</span><span class="sxs-lookup"><span data-stu-id="7c902-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="7c902-158">Bu bir DbPropertyExpression ziyaret eden döndürülür, ancak hiçbir zaman bir SqlBuilder eklendi.</span><span class="sxs-lookup"><span data-stu-id="7c902-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>  
  
```  
class SymbolPair : ISqlFragment {  
   public Symbol Source;  
   public Symbol Column;  
   public SymbolPair(Symbol source, Symbol column)  
}  
```  
  
#### <a name="joinsymbol"></a><span data-ttu-id="7c902-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="7c902-159">JoinSymbol</span></span>  
 <span data-ttu-id="7c902-160">Bir birleştirme simge bir birleşim veya Giriş birleşim iç içe geçmiş SELECT deyimiyle temsil eden bir simge ' dir.</span><span class="sxs-lookup"><span data-stu-id="7c902-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>  
  
```  
internal sealed class JoinSymbol : Symbol {  
   internal List<Symbol> ColumnList {get, set}  
   internal List<Symbol> ExtentList {get}  
   internal List<Symbol> FlattenedExtentList {get, set}  
   internal Dictionary<string, Symbol> NameToExtent {get}  
   internal bool IsNestedJoin {get, set}  
  
   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)  
}  
```  
  
 <span data-ttu-id="7c902-161">SQL SELECT deyimine bu simgeyi temsil ediyorsa ColumnList SELECT yan tümcesinde sütun listesini temsil eder.</span><span class="sxs-lookup"><span data-stu-id="7c902-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="7c902-162">ExtentList SELECT yan tümcesinde uzantıların listesi verilmiştir.</span><span class="sxs-lookup"><span data-stu-id="7c902-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="7c902-163">Birleşim en üst düzeyinde düzleştirilmiş birden çok kapsam varsa, diğer adlar doğru olarak adlandırılır, uzantı emin olmak için kapsam FlattenedExtentList izler.</span><span class="sxs-lookup"><span data-stu-id="7c902-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>  
  
 <span data-ttu-id="7c902-164">NameToExtent ExtentList tüm uzantıda bir sözlük olarak sahiptir.</span><span class="sxs-lookup"><span data-stu-id="7c902-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="7c902-165">IsNestedJoin bir JoinSymbol bir sıradan birleştirme simge veya karşılık gelen SqlSelectStatement içeren olup olmadığını belirlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="7c902-166">Tüm listeleri tam olarak bir kez ayarlayın ve sonra arama veya numaralandırma için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>  
  
#### <a name="symboltable"></a><span data-ttu-id="7c902-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="7c902-167">SymbolTable</span></span>  
 <span data-ttu-id="7c902-168">SymbolTable simgeleri değişken adları çözmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="7c902-169">SymbolTable her kapsam için yeni bir giriş yığın olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="7c902-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="7c902-170">Bir giriş bulunana kadar aramaları yığının üst kısmından altına arayın.</span><span class="sxs-lookup"><span data-stu-id="7c902-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>  
  
```  
internal sealed class SymbolTable {  
   internal void EnterScope()  
   internal void ExitScope()  
   internal void Add(string name, Symbol value)  
   internal Symbol Lookup(string name)  
}  
```  
  
 <span data-ttu-id="7c902-171">Sql üretimi modülü bir örneği başına yalnızca bir SymbolTable yoktur.</span><span class="sxs-lookup"><span data-stu-id="7c902-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="7c902-172">Kapsamları girilen ve ilişkisel her düğüm için çıkıldı.</span><span class="sxs-lookup"><span data-stu-id="7c902-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="7c902-173">Önceki kapsamlar tüm sembolleri aynı ada sahip başka sembollerin tarafından gizli sürece sonraki kapsamlar için görünür durumdadır.</span><span class="sxs-lookup"><span data-stu-id="7c902-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>  
  
### <a name="global-state-for-the-visitor"></a><span data-ttu-id="7c902-174">Ziyaretçi için genel durum</span><span class="sxs-lookup"><span data-stu-id="7c902-174">Global State for the Visitor</span></span>  
 <span data-ttu-id="7c902-175">Diğer adlar ve sütunları yeniden adlandırma yardımcı olmak üzere tüm sütun adlarının (AllColumnNames) listesini korumak ve ilk kullanılan ölçüde diğer adlarını (AllExtentNames) sorgu ağaç geçirin.</span><span class="sxs-lookup"><span data-stu-id="7c902-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="7c902-176">Sembol tablosuna değişken adları simgeleri çözümler.</span><span class="sxs-lookup"><span data-stu-id="7c902-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="7c902-177">IsVarRefSingle yalnızca kullanılan doğrulama amacıyla kesinlikle gerekli değildir.</span><span class="sxs-lookup"><span data-stu-id="7c902-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>  
  
 <span data-ttu-id="7c902-178">CurrentSelectStatement ve IsParentAJoin aracılığıyla kullanılan iki yığınları ziyaretçi düzeni bize parametreleri izin vermiyor bu yana "parametreleri" alt düğümleri için üst öğeden geçirmek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>  
  
```  
internal Dictionary<string, int> AllExtentNames {get}  
internal Dictionary<string, int> AllColumnNames {get}  
SymbolTable symbolTable = new SymbolTable();  
bool isVarRefSingle = false;  
  
Stack<SqlSelectStatement> selectStatementStack;  
private SqlSelectStatement CurrentSelectStatement{get}  
  
Stack<bool> isParentAJoinStack;  
private bool IsParentAJoin{get}  
```  
  
## <a name="common-scenarios"></a><span data-ttu-id="7c902-179">Yaygın senaryolar</span><span class="sxs-lookup"><span data-stu-id="7c902-179">Common Scenarios</span></span>  
 <span data-ttu-id="7c902-180">Bu bölümde, yaygın sağlayıcısı senaryolar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7c902-180">This section discusses common provider scenarios.</span></span>  
  
### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="7c902-181">SQL deyimleri ifade düğümleri gruplandırma</span><span class="sxs-lookup"><span data-stu-id="7c902-181">Grouping Expression Nodes into SQL Statements</span></span>  
 <span data-ttu-id="7c902-182">İlk ilişkisel düğümü karşılaşıldığında bir SqlSelectStatement oluşturulur (genellikle DbScanExpression ölçüde) ağacında yukarı Alttan ziyaret ederken.</span><span class="sxs-lookup"><span data-stu-id="7c902-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="7c902-183">Bir SQL SELECT deyimiyle az olarak üretmek için olabildiğince, üst düğümlerinden bu SqlSelectStatement mümkün olduğunca çoğunu olarak toplama sorguları iç içe geçmiş.</span><span class="sxs-lookup"><span data-stu-id="7c902-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="7c902-184">Verilen (ilişkisel) düğüm geçerli SqlSelectStatement (giriş ziyaret eden döndürülen bir) eklenebilmesi için veya yeni bir sistem başlatılması gerekip gerekmediğine karar IsCompatible yöntemi tarafından hesaplanır ve hangi zaten içinde olduğuna bağlıdır SqlSelectStatement ne düğümleri verilen düğüm olan üzerinde bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="7c902-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>  
  
 <span data-ttu-id="7c902-185">Genellikle, SQL deyimini yan tümceleri burada birleştirme için kabul düğümleri boş olmayan yan tümceleri sonra değerlendirildiğinde düğüm geçerli ifadesine eklenemez.</span><span class="sxs-lookup"><span data-stu-id="7c902-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="7c902-186">Bir sonraki düğüme bir filtre ise, yalnızca aşağıdaki doğruysa, örneğin, o düğümü geçerli SqlSelectStatement birleştirilebilir:</span><span class="sxs-lookup"><span data-stu-id="7c902-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>  
  
-   <span data-ttu-id="7c902-187">Seçim listesi boş.</span><span class="sxs-lookup"><span data-stu-id="7c902-187">The SELECT list is empty.</span></span> <span data-ttu-id="7c902-188">Seçim listesi boş değilse seçim listesi filtre önceki bir düğüm tarafından üretilen ve koşul bu seçim listesi tarafından üretilen sütunlara başvurabilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>  
  
-   <span data-ttu-id="7c902-189">GROUPBY boştur.</span><span class="sxs-lookup"><span data-stu-id="7c902-189">The GROUPBY is empty.</span></span> <span data-ttu-id="7c902-190">Filtre ekleme, GROUPBY boş değilse, doğru değil gruplandırma önce filtreleme anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="7c902-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>  
  
-   <span data-ttu-id="7c902-191">TOP yan tümcesi boştur.</span><span class="sxs-lookup"><span data-stu-id="7c902-191">The TOP clause is empty.</span></span> <span data-ttu-id="7c902-192">Filtre ekleme, TOP yan tümcesinde boş değilse, doğru değil üst yapmadan önce filtreleme anlamına gelir.</span><span class="sxs-lookup"><span data-stu-id="7c902-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>  
  
 <span data-ttu-id="7c902-193">Bunlar her zaman mevcut bir SqlSelectStatement bir parçası olarak dahil olduğu için bu DbConstantExpression veya aritmetik ifadeler gibi ilişkisel olmayan düğümleri için geçerli değildir.</span><span class="sxs-lookup"><span data-stu-id="7c902-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="7c902-194">Ayrıca, (bir birleşim üst öğesi yok bir birleşim düğümü) katılma ağacının kökü karşılaşıldığında, yeni SqlSelectStatement başlatılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="7c902-195">Tüm sol Sırt birleştirme alt o SqlSelectStatement toplanır.</span><span class="sxs-lookup"><span data-stu-id="7c902-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="7c902-196">Yeni SqlSelectStatement başlatıldığından ve geçerli bir giriş eklenen her geçerli SqlSelectStatement biri yoksa, projeksiyon sütunlar (bir SELECT yan tümcesi) ekleyerek tamamlanması gerekir.</span><span class="sxs-lookup"><span data-stu-id="7c902-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="7c902-197">Bu yöntem, SqlSelectStatement FromExtents arar ve tahmini sütunlar listesine kapsamdaki FromExtents tarafından temsil edilen uzantıların listesini getirir tüm sütunları ekleyen AddDefaultColumns gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="7c902-198">Bu noktada, hangi sütunların diğer düğümleri tarafından başvurulan bilinmeyen olduğundan bu, gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="7c902-199">Bu, daha sonra kullanılabilir sütunlar yalnızca projeye iyileştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-199">This can be optimized to only project the columns that can later be used.</span></span>  
  
### <a name="join-flattening"></a><span data-ttu-id="7c902-200">Düzleştirme katılma</span><span class="sxs-lookup"><span data-stu-id="7c902-200">Join Flattening</span></span>  
 <span data-ttu-id="7c902-201">IsParentAJoin özelliği, verilen bir birleştirme düzleştirilmiş olup olmadığını belirlemenize yardımcı olur.</span><span class="sxs-lookup"><span data-stu-id="7c902-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="7c902-202">Özellikle, IsParentAJoin döndürür `true` yalnızca bir birleştirme ve hemen her DbScanExpression için sol alt durumda bir birleştirme için o alt düğüm giriş için üst daha sonra kullanacağınız aynı SqlSelectStatement yeniden kullanır.</span><span class="sxs-lookup"><span data-stu-id="7c902-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="7c902-203">Daha fazla bilgi için "Katılma ifadeleri" konusuna bakın.</span><span class="sxs-lookup"><span data-stu-id="7c902-203">For more information, see "Join Expressions".</span></span>  
  
### <a name="input-alias-redirecting"></a><span data-ttu-id="7c902-204">Diğer ad yönlendirme giriş</span><span class="sxs-lookup"><span data-stu-id="7c902-204">Input Alias Redirecting</span></span>  
 <span data-ttu-id="7c902-205">Giriş diğer adı yeniden yönlendirme sembol tablosu gerçekleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-205">Input alias redirecting is accomplished with the symbol table.</span></span>  
  
 <span data-ttu-id="7c902-206">İlk örnekte başvurmak giriş diğer adı yeniden yönlendirme açıklamak için [komut ağaçlarını - en iyi uygulamaları oluşturma SQL'den](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="7c902-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="7c902-207">Yok "a" gerekli "b" projeksiyon yönlendirilmesi.</span><span class="sxs-lookup"><span data-stu-id="7c902-207">There "a" needed to be redirected to "b" in the projection.</span></span>  
  
 <span data-ttu-id="7c902-208">Bir SqlSelectStatement nesnesi oluşturulduğunda, giriş düğüme ölçüde SqlSelectStatement From özelliğinde yerleştirilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="7c902-209">Bir simge (< symbol_b >) o uzantı temsil etmek için giriş bağlaması adı ("b") ve "AS" temel alınarak oluşturulur + < symbol_b > From yan tümcesi için eklenir.</span><span class="sxs-lookup"><span data-stu-id="7c902-209">A Symbol (<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " +  <symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="7c902-210">Simgenin FromExtents özelliğine de eklenir.</span><span class="sxs-lookup"><span data-stu-id="7c902-210">The symbol is also added to the FromExtents property.</span></span>  
  
 <span data-ttu-id="7c902-211">Simgenin de giriş bağlaması adı ("b", < symbol_b >) bağlamak üzere sembol tablosuna eklenir.</span><span class="sxs-lookup"><span data-stu-id="7c902-211">The symbol is also added to the symbol table to link the input binding name to it ("b", <symbol_b>).</span></span>  
  
 <span data-ttu-id="7c902-212">Bir sonraki düğüme bu SqlSelectStatement yeniden kullanır, bir giriş için bu simgeyi giriş bağlaması adını bağlamak için Sembol tablosuna ekler.</span><span class="sxs-lookup"><span data-stu-id="7c902-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="7c902-213">Bizim örneğimizde, giriş bağlaması adı "a" ile DbProjectExpression SqlSelectStatement yeniden kullanmak ve Ekle ("a", \< symbol_b >) tablosu.</span><span class="sxs-lookup"><span data-stu-id="7c902-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>  
  
 <span data-ttu-id="7c902-214">İfadeleri SqlSelectStatement yeniden düğümünün giriş bağlaması adı başvurduğunuzda, bu başvuruyu doğru yeniden yönlendirilen simgesine sembol tablosunu kullanarak çözümlenir.</span><span class="sxs-lookup"><span data-stu-id="7c902-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="7c902-215">"A.x" den "a" DbVariableReferenceExpression temsil eden ziyaret ederken çözümlendiğinde "a" BT < symbol_b > simgenin çözümleyin.</span><span class="sxs-lookup"><span data-stu-id="7c902-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol <symbol_b>.</span></span>  
  
### <a name="join-alias-flattening"></a><span data-ttu-id="7c902-216">Diğer ad düzleştirme katılma</span><span class="sxs-lookup"><span data-stu-id="7c902-216">Join Alias Flattening</span></span>  
 <span data-ttu-id="7c902-217">DbPropertyExpression başlıklı bölümde açıklandığı gibi bir DbPropertyExpression ziyaret zaman diğer birleştirme düzleştirme elde edilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>  
  
### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="7c902-218">Sütun adı ve uzantı Alias yeniden adlandırma</span><span class="sxs-lookup"><span data-stu-id="7c902-218">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="7c902-219">İkinci aşama, SQL üretimi başlıklı bölümde açıklanan nesil ikinci aşamasında diğer adları ile yalnızca değiştirilen simgeleri kullanarak sütun adı ve diğer ad uzantısı yeniden adlandırma sorunu ele: dize komutu oluşturuluyor.</span><span class="sxs-lookup"><span data-stu-id="7c902-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>  
  
## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="7c902-220">Birinci aşama SQL oluşturma: ifade ağacına ziyaret edin</span><span class="sxs-lookup"><span data-stu-id="7c902-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="7c902-221">Bu bölümde SQL oluşturma, ne zaman ifade sorgu ziyaret edilen temsil eden ve Ara yapısı üretileceğini, ilk aşaması ya da bir SqlSelectStatement veya bir SqlBuilder açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7c902-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>  
  
 <span data-ttu-id="7c902-222">Bu bölümde, ziyaret farklı ifade düğümü kategorileri ilkeleri ve belirli ifade türleri ziyaret Ayrıntılar açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7c902-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>  
  
### <a name="relational-non-join-nodes"></a><span data-ttu-id="7c902-223">İlişkisel (birleştirme olmayan) düğümler</span><span class="sxs-lookup"><span data-stu-id="7c902-223">Relational (Non-Join) Nodes</span></span>  
 <span data-ttu-id="7c902-224">Aşağıdaki ifade türleri birleştirme olmayan düğümler destekler:</span><span class="sxs-lookup"><span data-stu-id="7c902-224">The following expression types support non-join nodes:</span></span>  
  
-   <span data-ttu-id="7c902-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-225">DbDistinctExpression</span></span>  
  
-   <span data-ttu-id="7c902-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-226">DbFilterExpression</span></span>  
  
-   <span data-ttu-id="7c902-227">Bir DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-227">DbGroupByExpression</span></span>  
  
-   <span data-ttu-id="7c902-228">DbLimitExpession</span><span class="sxs-lookup"><span data-stu-id="7c902-228">DbLimitExpession</span></span>  
  
-   <span data-ttu-id="7c902-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-229">DbProjectExpression</span></span>  
  
-   <span data-ttu-id="7c902-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-230">DbSkipExpression</span></span>  
  
-   <span data-ttu-id="7c902-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-231">DbSortExpression</span></span>  
  
 <span data-ttu-id="7c902-232">Bu düğümler ziyaret şu deseni izler:</span><span class="sxs-lookup"><span data-stu-id="7c902-232">Visiting these nodes follows the following pattern:</span></span>  
  
1.  <span data-ttu-id="7c902-233">İlişkisel giriş sayfasını ziyaret edin ve sonuçta elde edilen SqlSelectStatement alın.</span><span class="sxs-lookup"><span data-stu-id="7c902-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="7c902-234">İlişkisel bir düğüme giriş aşağıdakilerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="7c902-234">The input to a relational node could be one of the following:</span></span>  
  
    -   <span data-ttu-id="7c902-235">Bir uzantı (örneğin, bir DbScanExpression) dahil olmak üzere bir ilişkisel düğüm.</span><span class="sxs-lookup"><span data-stu-id="7c902-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="7c902-236">Bu tür bir düğüm ziyaret eden bir SqlSelectStatement döndürür.</span><span class="sxs-lookup"><span data-stu-id="7c902-236">Visiting such a node returns a SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="7c902-237">Küme işlemi ifadesi (UNION ALL, örneğin).</span><span class="sxs-lookup"><span data-stu-id="7c902-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="7c902-238">Parantez içine alınmış ve yeni SqlSelectStatement FROM yan tümcesinde put sonuç vardır.</span><span class="sxs-lookup"><span data-stu-id="7c902-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>  
  
2.  <span data-ttu-id="7c902-239">Geçerli düğüm giriş tarafından üretilen SqlSelectStatement eklenebilir olup olmadığını denetleyin.</span><span class="sxs-lookup"><span data-stu-id="7c902-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="7c902-240">SQL deyimleri gruplandırma ifadeleri başlıklı bölümde bu açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="7c902-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="7c902-241">Aksi durumda,</span><span class="sxs-lookup"><span data-stu-id="7c902-241">If not,</span></span>  
  
    -   <span data-ttu-id="7c902-242">Geçerli SqlSelectStatement nesne açılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-242">Pop the current SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="7c902-243">Yeni bir SqlSelectStatement nesnesi oluşturun ve yeni SqlSelectStatement nesnenin FROM popped SqlSelectStatement ekleyin.</span><span class="sxs-lookup"><span data-stu-id="7c902-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="7c902-244">Yeni nesne yığının en üstünde yerleştirin.</span><span class="sxs-lookup"><span data-stu-id="7c902-244">Put the new object on top of the stack.</span></span>  
  
3.  <span data-ttu-id="7c902-245">Giriş ifadesi bağlama doğru simge girdisinden yönlendirin.</span><span class="sxs-lookup"><span data-stu-id="7c902-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="7c902-246">Bu bilgiler SqlSelectStatement nesnesinde korunur.</span><span class="sxs-lookup"><span data-stu-id="7c902-246">This information is maintained in the SqlSelectStatement object.</span></span>  
  
4.  <span data-ttu-id="7c902-247">Yeni bir SymbolTable kapsamı ekleyin.</span><span class="sxs-lookup"><span data-stu-id="7c902-247">Add a new SymbolTable scope.</span></span>  
  
5.  <span data-ttu-id="7c902-248">İfade (örneğin, yansıtma ve koşulu) giriş olmayan parçası ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="7c902-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>  
  
6.  <span data-ttu-id="7c902-249">Genel yığınları eklenen tüm nesneler açılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-249">Pop all the objects added to the global stacks.</span></span>  
  
 <span data-ttu-id="7c902-250">DbSkipExpression SQL doğrudan bir eşdeğer yok.</span><span class="sxs-lookup"><span data-stu-id="7c902-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="7c902-251">Mantıksal olarak, veri dönüştürülür:</span><span class="sxs-lookup"><span data-stu-id="7c902-251">Logically, it is translated into:</span></span>  
  
```  
SELECT Y.x1, Y.x2, ..., Y.xn  
FROM (  
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]   
   FROM input as X   
   ) as Y  
WHERE Y.[row_number] > count   
ORDER BY sk1, sk2, ...  
```  
  
### <a name="join-expressions"></a><span data-ttu-id="7c902-252">İfadeler katılma</span><span class="sxs-lookup"><span data-stu-id="7c902-252">Join Expressions</span></span>  
 <span data-ttu-id="7c902-253">Aşağıdaki birleşim ifadeleri olarak kabul edilir ve ortak bir biçimde VisitJoinExpression yöntemi tarafından işlenir:</span><span class="sxs-lookup"><span data-stu-id="7c902-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>  
  
-   <span data-ttu-id="7c902-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-254">DbApplyExpression</span></span>  
  
-   <span data-ttu-id="7c902-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-255">DbJoinExpression</span></span>  
  
-   <span data-ttu-id="7c902-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-256">DbCrossJoinExpression</span></span>  
  
 <span data-ttu-id="7c902-257">Ziyaret adımları şunlardır:</span><span class="sxs-lookup"><span data-stu-id="7c902-257">The following are the visit steps:</span></span>  
  
 <span data-ttu-id="7c902-258">İlk olarak, alt öğelerini ziyaret önce IsParentAJoin birleştirme düğümü bir birleştirme sol Sırt boyunca alt olup olmadığını denetlemek için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="7c902-259">False değeri döndürülürse, yeni SqlSelectStatement başlatılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="7c902-260">(Birleştirme düğümü) üst SqlSelectStatement büyük olasılıkla kullanılacak çocuklar için oluştururken bu anlamda birleştirmeler farklı düğümlerin geri kalanından ziyaret edilen.</span><span class="sxs-lookup"><span data-stu-id="7c902-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>  
  
 <span data-ttu-id="7c902-261">İkinci olarak, bir girdi bir kerede işleme.</span><span class="sxs-lookup"><span data-stu-id="7c902-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="7c902-262">Her giriş için:</span><span class="sxs-lookup"><span data-stu-id="7c902-262">For each input:</span></span>  
  
1.  <span data-ttu-id="7c902-263">Giriş sayfasını ziyaret edin.</span><span class="sxs-lookup"><span data-stu-id="7c902-263">Visit the input.</span></span>  
  
2.  <span data-ttu-id="7c902-264">POST işlemi JOIN ifadesinin bir alt ziyaret ve büyük olasılıkla alt tarafından üretilen SqlSelectStatement bittikten sonra simge tablosunun bakımı için sorumlu olduğu ProcessJoinInputResult, çağırarak giriş ziyaret sonucu.</span><span class="sxs-lookup"><span data-stu-id="7c902-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="7c902-265">Çocuğunuzun sonucu aşağıdakilerden biri olabilir:</span><span class="sxs-lookup"><span data-stu-id="7c902-265">The child's result could be one of the following:</span></span>  
  
    -   <span data-ttu-id="7c902-266">Üst eklenecek sunucudan farklı bir SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="7c902-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="7c902-267">Böyle bir durumda, varsayılan sütunları ekleyerek tamamlanmış olması gerekebilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="7c902-268">Giriş bir birleştirme olduysa, yeni bir birleşim sembol oluşturmanız gerekir.</span><span class="sxs-lookup"><span data-stu-id="7c902-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="7c902-269">Aksi takdirde, normal bir simge oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7c902-269">Otherwise, create a normal symbol.</span></span>  
  
    -   <span data-ttu-id="7c902-270">Yalnızca üst girişleri listesine eklenen durum SqlSelectStatement kullanıcının bir uzantı (bir DbScanExpression, örneğin).</span><span class="sxs-lookup"><span data-stu-id="7c902-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="7c902-271">Servis talebi ile sarılır ayraçlar içinde olmayan bir SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="7c902-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>  
  
    -   <span data-ttu-id="7c902-272">Üst ekleneceği aynı SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="7c902-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="7c902-273">Böyle bir durumda FromExtents listesinde simgelerin tümünü temsil eden tek yeni bir JoinSymbol değiştirilmesi gerekir.</span><span class="sxs-lookup"><span data-stu-id="7c902-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>  
  
    -   <span data-ttu-id="7c902-274">İlk üç durumlarda, AddFromSymbol AS yan tümcesi ekleyin ve sembol tablosunu güncelleştirmek için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>  
  
 <span data-ttu-id="7c902-275">Üçüncü (varsa) birleştirme koşulunun ziyaret edilen.</span><span class="sxs-lookup"><span data-stu-id="7c902-275">Third, the join condition (if any) is visited.</span></span>  
  
### <a name="set-operations"></a><span data-ttu-id="7c902-276">Ayarlama İşlemleri</span><span class="sxs-lookup"><span data-stu-id="7c902-276">Set Operations</span></span>  
 <span data-ttu-id="7c902-277">Ayarlama işlemleri DbUnionAllExpression, DbExceptExpression ve DbIntersectExpression VisitSetOpExpression yöntemi tarafından işlenir.</span><span class="sxs-lookup"><span data-stu-id="7c902-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="7c902-278">Şeklin SqlBuilder oluşturur</span><span class="sxs-lookup"><span data-stu-id="7c902-278">It creates a SqlBuilder of the shape</span></span>  
  
```xml  
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>  
```  
  
 <span data-ttu-id="7c902-279">Burada \<leftSqlSelectStatement > ve \<rightSqlSelectStatement > olan her girdi ziyaret ederek elde SqlSelectStatements ve \<setOp > karşılık gelen (UNION ALL örneğin) bir işlemdir.</span><span class="sxs-lookup"><span data-stu-id="7c902-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>  
  
### <a name="dbscanexpression"></a><span data-ttu-id="7c902-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-280">DbScanExpression</span></span>  
 <span data-ttu-id="7c902-281">(Başka bir birleştirme sol alt bir birleştirme girdi) olarak bir birleşim bağlamında ziyaret ettiğinde DbScanExpression SqlBuilder tanımlayan bir sorgu, tablo veya Görünüm karşılık gelen hedef hedef SQL ile döndürür.</span><span class="sxs-lookup"><span data-stu-id="7c902-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="7c902-282">Aksi takdirde, yeni SqlSelectStatement Kimden alanı karşılık gelen hedef karşılık gelecek şekilde ayarlanmış oluşturulur.</span><span class="sxs-lookup"><span data-stu-id="7c902-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>  
  
### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="7c902-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-283">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="7c902-284">Bir DbVariableReferenceExpression ziyaret simgesi tablosundaki Ara temel Bu değişken başvuru ifade ile eşleşen simgesini döndürür.</span><span class="sxs-lookup"><span data-stu-id="7c902-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="7c902-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-285">DbPropertyExpression</span></span>  
 <span data-ttu-id="7c902-286">Diğer ad JOIN düzleştirme tanımlanmış ve bir DbPropertyExpression ziyaret eden işlenen.</span><span class="sxs-lookup"><span data-stu-id="7c902-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>  
  
 <span data-ttu-id="7c902-287">Örnek özelliği ilk kez ziyaret ve bir sembol, bir JoinSymbol ya da bir SymbolPair sonucudur.</span><span class="sxs-lookup"><span data-stu-id="7c902-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="7c902-288">Bu üç durumda işlenme aşağıda verilmiştir:</span><span class="sxs-lookup"><span data-stu-id="7c902-288">Here is how these three cases are handled:</span></span>  
  
-   <span data-ttu-id="7c902-289">Bir JoinSymbol döndürülürse, kendi NameToExtent özelliği gerekli bir özellik için bir simge içerir.</span><span class="sxs-lookup"><span data-stu-id="7c902-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="7c902-290">İç içe geçmiş bir birleşim birleştirme simgenin temsil ediyorsa, yeni bir simge çifti örneği diğer ad olarak kullanılan simge izlemek için birleştirme simgesi ile daha fazla çözümleme için gerçek özelliğini temsil eden simgesi ile döndürülür.</span><span class="sxs-lookup"><span data-stu-id="7c902-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>  
  
-   <span data-ttu-id="7c902-291">Bir SymbolPair döndürülür ve bir birleşim simge sütun parçası ise, bir birleşim simge tekrar döndürülür, ancak column özelliği için geçerli özellik ifade tarafından temsil edilen özelliği işaret edecek şekilde güncelleştirilmiştir.</span><span class="sxs-lookup"><span data-stu-id="7c902-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="7c902-292">Aksi takdirde bir SqlBuilder diğer adını ve sütun olarak geçerli bir özellik için simge olarak SymbolPair kaynağıyla döndürülür.</span><span class="sxs-lookup"><span data-stu-id="7c902-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>  
  
-   <span data-ttu-id="7c902-293">Bir simge döndürülürse, ziyaret yöntemi SqlBuilder yöntemi bu örneği diğer ad olarak ve sütun adı olarak özellik adını döndürür.</span><span class="sxs-lookup"><span data-stu-id="7c902-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>  
  
### <a name="dbnewinstanceexpression"></a><span data-ttu-id="7c902-294">Dbnewınstanceexpression</span><span class="sxs-lookup"><span data-stu-id="7c902-294">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="7c902-295">DbProjectExpression projeksiyon özelliği olarak kullanıldığında, Dbnewınstanceexpression tahmini sütunları temsil etmek için bağımsız değişkenlerin virgülle ayrılmış bir liste oluşturur.</span><span class="sxs-lookup"><span data-stu-id="7c902-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>  
  
 <span data-ttu-id="7c902-296">Dbnewınstanceexpression koleksiyonu dönüş türü olan ve yeni bir bağımsız değişken olarak sağlanan ifadeleri koleksiyonunu tanımlar, aşağıdaki üç durumda ayrı olarak ele alınmıştır:</span><span class="sxs-lookup"><span data-stu-id="7c902-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>  
  
-   <span data-ttu-id="7c902-297">Dbnewınstanceexpression tek bağımsız değişken olarak DbElementExpression varsa, aşağıdaki gibi çevrilir:</span><span class="sxs-lookup"><span data-stu-id="7c902-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>  
  
    ```  
    NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X  
    ```  
  
 <span data-ttu-id="7c902-298">Dbnewınstanceexpression bağımsız değişkenler varsa (boş bir tablo gösterir) Dbnewınstanceexpression çevrilir:</span><span class="sxs-lookup"><span data-stu-id="7c902-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>  
  
```  
SELECT CAST(NULL AS <primitiveType>) as X  
FROM (SELECT 1) AS Y WHERE 1=0  
```  
  
 <span data-ttu-id="7c902-299">Aksi takdirde Dbnewınstanceexpression UNION all basamaklardan bağımsız değişkenlerden biri oluşturur:</span><span class="sxs-lookup"><span data-stu-id="7c902-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>  
  
```  
SELECT <visit-result-arg1> as X  
UNION ALL SELECT <visit-result-arg2> as X  
UNION ALL …  
UNION ALL SELECT <visit-result-argN> as X  
```  
  
### <a name="dbfunctionexpression"></a><span data-ttu-id="7c902-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-300">DbFunctionExpression</span></span>  
 <span data-ttu-id="7c902-301">Kurallı ve yerleşik işlevler aynı şekilde işlenir: özel işleme (örneğin LTRIM(RTRIM(string) için TRIM(string)) ihtiyacınız varsa, uygun işleyiciyi çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="7c902-302">Aksi halde bunlar (arg1, arg2,..., argn) FunctionName çevrilir.</span><span class="sxs-lookup"><span data-stu-id="7c902-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>  
  
 <span data-ttu-id="7c902-303">Sözlük, hangi işlevleri özel işleme ve bunların uygun işleyicileri gereksinim izlemek için kullanılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>  
  
 <span data-ttu-id="7c902-304">Kullanıcı tanımlı işlevler (arg1, arg2,..., argn) NamespaceName.FunctionName tanslated içindedir.</span><span class="sxs-lookup"><span data-stu-id="7c902-304">User-defined functions are tanslated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>  
  
### <a name="dbelementexpression"></a><span data-ttu-id="7c902-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-305">DbElementExpression</span></span>  
 <span data-ttu-id="7c902-306">DbElementExpression ziyaret yöntemi yalnızca bir skaler alt sorgu temsil etmek üzere kullanıldığında DbElementExpression ziyaret için çağrılır.</span><span class="sxs-lookup"><span data-stu-id="7c902-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="7c902-307">Bu nedenle, DbElementExpression tam SqlSelectStatement dönüşür ve köşeli ayraç içine ekler.</span><span class="sxs-lookup"><span data-stu-id="7c902-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>  
  
### <a name="dbquantifierexpression"></a><span data-ttu-id="7c902-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-308">DbQuantifierExpression</span></span>  
 <span data-ttu-id="7c902-309">İfade türüne bağlı olarak (veya tamamını), DbQuantifierExpression çevrilir olarak:</span><span class="sxs-lookup"><span data-stu-id="7c902-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated it as:</span></span>  
  
```  
Any(input, x) => Exists(Filter(input,x))  
All(input, x) => Not Exists(Filter(input, not(x))  
```  
  
### <a name="dbnotexpression"></a><span data-ttu-id="7c902-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-310">DbNotExpression</span></span>  
 <span data-ttu-id="7c902-311">Bazı durumlarda DbNotExpression çeviri ile giriş ifadesi daraltmak mümkündür.</span><span class="sxs-lookup"><span data-stu-id="7c902-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="7c902-312">Örneğin:</span><span class="sxs-lookup"><span data-stu-id="7c902-312">For example:</span></span>  
  
```  
Not(IsNull(a)) =>  "a IS NOT NULL"  
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))  
```  
  
 <span data-ttu-id="7c902-313">İkinci Daralt gerçekleştirilen nedeni, DbQuantifierExpression çevirme yazdığınızda, tüm verimsiz sağlayıcı tarafından sunulan nedeni.</span><span class="sxs-lookup"><span data-stu-id="7c902-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="7c902-314">Bu nedenle Entity Framework basitleştirme yapmadıysanız.</span><span class="sxs-lookup"><span data-stu-id="7c902-314">Thus the Entity Framework could not have done the simplification.</span></span>  
  
### <a name="dbisemptyexpression"></a><span data-ttu-id="7c902-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="7c902-315">DbIsEmptyExpression</span></span>  
 <span data-ttu-id="7c902-316">DbIsEmptyExpression olarak çevrilir:</span><span class="sxs-lookup"><span data-stu-id="7c902-316">DbIsEmptyExpression is translated as:</span></span>  
  
```  
IsEmpty(inut) = Not Exists(input)  
```  
  
## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="7c902-317">SQL üretimi ikinci aşaması: dize komutu oluşturuluyor</span><span class="sxs-lookup"><span data-stu-id="7c902-317">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="7c902-318">Bir dize SQL komutu oluştururken SqlSelectStatement hangi sütun adı ve diğer ad uzantısı yeniden adlandırma sorunu giderir sembolleri için gerçek diğer adlar üretir.</span><span class="sxs-lookup"><span data-stu-id="7c902-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>  
  
 <span data-ttu-id="7c902-319">Diğer ad uzantısı yeniden adlandırma bir dizeye SqlSelectStatement nesne yazılırken oluşur.</span><span class="sxs-lookup"><span data-stu-id="7c902-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="7c902-320">İlk dış kapsam tarafından kullanılan tüm diğer adları listesini oluşturun.</span><span class="sxs-lookup"><span data-stu-id="7c902-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="7c902-321">Her simge FromExtents (veya null olmayan ise AllJoinExtents) herhangi bir dış kapsam ile çakışırsa adı.</span><span class="sxs-lookup"><span data-stu-id="7c902-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="7c902-322">Yeniden adlandırma gerekirse AllExtentNames içinde toplanan kapsam biriyle çakışmamasını.</span><span class="sxs-lookup"><span data-stu-id="7c902-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>  
  
 <span data-ttu-id="7c902-323">Sütun yeniden adlandırma, bir dizeyi bir sembol nesnesi yazılırken oluşur.</span><span class="sxs-lookup"><span data-stu-id="7c902-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="7c902-324">İlk aşamada AddDefaultColumns belirli bir sütun simge yeniden adlandırılacak olup olmadığını belirledi.</span><span class="sxs-lookup"><span data-stu-id="7c902-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="7c902-325">İkinci aşamasında, üretilen adı AllColumnNames içinde kullanılan herhangi bir ad ile çakışmadığından emin yalnızca yeniden adlandırma ortaya çıkar</span><span class="sxs-lookup"><span data-stu-id="7c902-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>  
  
 <span data-ttu-id="7c902-326">Uzantı diğer adlar ve sütunlar için benzersiz adlar oluşturmak için n henüz kullanılmamış küçük diğer adı olduğu < existing_name > _n kullanın.</span><span class="sxs-lookup"><span data-stu-id="7c902-326">To produce unique names both for extent aliases and for columns, use <existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="7c902-327">Tüm diğer adları genel listesini basamaklı yeniden adlandırır gereksinimini artırır.</span><span class="sxs-lookup"><span data-stu-id="7c902-327">The global list of all aliases increases the need for cascading renames.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c902-328">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="7c902-328">See Also</span></span>  
 [<span data-ttu-id="7c902-329">Örnek Sağlayıcısı'nda SQL oluşturma</span><span class="sxs-lookup"><span data-stu-id="7c902-329">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)