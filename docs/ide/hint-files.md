---
title: ファイルのヒント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- cpp.hint
- vc.hint.file
dev_langs:
- C++
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 687e5cba94693a752f934d7816e6a7c36e318354
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="hint-files"></a>ヒント ファイル
A*ヒント ファイル*により、Visual Studio 統合開発環境 (IDE) は、関数とマクロの名前など、Visual C の識別子を解釈します。 Visual C プロジェクト、IDE の開く*解析システム*プロジェクト内の各ソース ファイル内のコードを分析し、すべての識別子に関する情報を収集します。 IDE では、その情報を使用してなどの機能のサポート、**クラス ビュー**ブラウザーと**ナビゲーション バー**です。  
  
 Visual C 2010 で導入された、解析のシステムでは、C と C++ 構文を認識するが、マクロを含むステートメントを誤って解釈できます。 ステートメントは、マクロに書き込まれると、構文的に正しいするソース コードが発生した場合、誤って解釈されることができます。 ステートメントがなる構文的に正しい場合、ソース コードがコンパイルされ、プリプロセッサが置き換えられます、[マクロ識別子](../preprocessor/hash-define-directive-c-cpp.md)その定義を使用します。 解析のシステムは、マクロを解釈するヒント ファイルを使用しているために、プロジェクトをビルドすることがなく動作します。 そのため、参照、機能のなど**クラス ビュー**はすぐに使用できます。  
  
 ヒント ファイルを含むユーザーがカスタマイズできる*ヒント*C と C++ のマクロ定義と同じ構文であります。 Visual C には、ほとんどのプロジェクトでは、十分な組み込みのヒント ファイルが含まれていますが、Visual Studio の識別子の処理方法を向上させるために、自分のヒント ファイルを作成することができます。  
  
> [!IMPORTANT]
>  変更、ヒント ファイルを追加するか、.sdf ファイルや変更を有効にするためのソリューションで VC.db ファイルを削除する必要があります。  
  
## <a name="scenario"></a>シナリオ  
 ソース ファイルで確認するには、次のコードで、**クラス ビュー**ブラウザー。 `STDMETHOD`マクロという名前のメソッドを宣言して`myMethod`を 1 つのパラメーターを受け取るしてへのポインターを返す、 **HRESULT**です。  
  
```  
// Source code file.  
STDMETHOD(myMethod)(int parameter1);  
```  
  
 次のマクロ定義では、別のヘッダー ファイルにします。  
  
```  
// Header file.  
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)  
#define STDMETHODCALLTYPE __stdcall  
#define HRESULT void*  
```  
  
 STDMETHOD をという名前の関数が宣言するのには、表示されるため、解析を行って、システムは、ソース コードを解釈できないし、その宣言構文が正しくない 2 つのパラメーター リストがあるためです。 解析のシステムがの定義を検出するヘッダー ファイルを開けません、 `STDMETHOD`、 `STDMETHODCALLTYPE`、および`HRESULT`マクロです。 解析のシステムが解釈できないため、`STDMETHOD`マクロ、ステートメント全体を無視し、解析を継続します。  
  
 解析のシステムでは、プロジェクトは、1 つまたは複数の重要なヘッダー ファイルに依存しているために、ヘッダー ファイルは使用しません。 任意のヘッダー ファイルが変更された場合は、解析システムをすべてのプロジェクトで、IDE のパフォーマンスが遅くなるヘッダー ファイルを再確認する必要があります。 解析のシステムで処理する方法を指定するヒントを使用する代わりに、 `STDMETHOD`、 `STDMETHODCALLTYPE`、および`HRESULT`マクロです。  
  
 すれば、ヒントをする必要がありますか。 ヒントを必要がある場合どのような種類を作成しますか。 ヒントが必要である 1 つの符号は場合、ビュー内の識別子の**クラス ビュー**のビューと整合性がありません、**エディター**です。 たとえば、**クラス ビュー**を表示しない がわかっているクラスのメンバーが存在する可能性がありますか、メンバーの名前が正しくありません。 一般的な問題を解決するヒントの種類の詳細については、どのようなマクロを必要とするヒントを参照してくださいしますか。このトピックで後述する「します。  
  
## <a name="architecture"></a>アーキテクチャ  
 ヒント ファイルが物理ディレクトリに関連付けで使用される、論理ディレクトリではなく**ソリューション エクスプ ローラー**です。 ヒント ファイルに影響を与えるヒント ファイルには、プロジェクトを追加する必要はありません。 解析のシステムは、ソース ファイルを解析する場合にのみ、ヒント ファイルを使用します。  
  
 ヒントのすべてのファイルの名前は**cpp.hint**です。 そのため、多くのディレクトリは、ヒント ファイルを含めることができますが、1 つだけのヒント ファイルは、特定のディレクトリで発生します。  
  
 プロジェクトは、0 個以上のヒント ファイルによって影響を受けることができます。 ヒント ファイルが存在しない場合、解析を行って、システムを解読できないソース コードを無視するエラー回復手法を使用します。 それ以外の場合、解析を行って、システムでは、次の戦略を使用して検索し、ヒントを収集します。  
  
### <a name="search-order"></a>検索順序  
 解析のシステムでは、次の順序でのヒント ファイルのディレクトリを検索します。  
  
-   Visual C のインストール パッケージを格納するディレクトリ (**vcpackages**)。 このディレクトリには、組み込みのヒント ファイルなど、頻繁に使用されるシステムのファイル内のシンボルを表す**windows.h**です。 そのため、プロジェクトに必要なヒントのほとんどが自動的に継承します。  
  
-   ソース ファイルのルート ディレクトリから、ソース ファイル自体を含むディレクトリへのパス。 一般的な Visual C プロジェクトでは、ルート ディレクトリには、ソリューションまたはプロジェクト ファイルが含まれています。  
  
     このルールの例外は場合、*ストップ ファイル*ソース ファイルへのパスにします。 ストップ ファイルが検索順序の詳細に制御を提供し、名前は任意のファイルは、 **cpp.stop**です。 ルート ディレクトリから開始するのではなく解析システムは、ソース ファイルが格納されているディレクトリに停止ファイルを含むディレクトリから検索します。 一般的なプロジェクトでストップ ファイルは必要ありません。  
  
### <a name="hint-gathering"></a>ヒントの収集  
 ヒント ファイルは、0 個以上含まれています。*ヒント*です。 ヒントが定義されているか、C と C++ マクロと同じように削除します。 つまり、`#define`プリプロセッサ ディレクティブを作成するか、ヒントを再定義し、`#undef`ディレクティブは、ヒントを削除します。  
  
 解析のシステムが前に説明した検索の順序で各ヒント ファイルを開きのセットに各ファイルのヒントを蓄積*有効ヒント*、し、効果的なヒントを使用して、コード内の識別子を解釈します。  
  
 解析のシステムでは、ヒントを蓄積するのに次の規則を使用します。  
  
-   新しいヒントは、既に定義されていない名前を指定する場合、新しいヒントは、効果的なヒントに名前を追加します。  
  
-   新しいヒントは、既に定義されている名前を指定する場合、新しいヒントには、既存のヒントが再定義します。  
  
-   新しいヒントがある場合、`#undef`ディレクティブを指定する有効な既存のヒント、新しいヒントは、既存のヒントを削除します。  
  
 最初の規則は、有効なヒントがヒントの前に開かれたファイルから継承されたことを意味します。 最後の 2 つのルールは、検索の順序で後で発生するヒントが以前に発生したヒントをオーバーライドできることを意味します。 たとえば、ソース ファイルが格納されているディレクトリにヒント ファイルを作成する場合に、前のヒントをオーバーライドできます。  
  
 ヒントの収集方法を示してを参照してください、`Example`このトピックで後述します。  
  
### <a name="syntax"></a>構文  
 ヒントが作成され、プリプロセッサ ディレクティブを作成し、マクロを削除すると同じ構文を使用して削除します。 実際には、解析システムは、C/C++ プリプロセッサを使用して、ヒントを評価します。 プリプロセッサ ディレクティブの詳細については、次を参照してください。 [#define ディレクティブ (c/c++)](../preprocessor/hash-define-directive-c-cpp.md)と[#undef ディレクティブ (c/c++)](../preprocessor/hash-undef-directive-c-cpp.md)です。  
  
 だけに特殊な構文要素は、 `@<`、 `@=`、および`@>`置換文字列。 これらでのみ使用されるヒント ファイル固有の置換文字列*マップ*マクロです。 マップとは、一連のデータ、関数、またはイベントを他のデータ、関数、またはイベント ハンドラーに関連するマクロです。 たとえば、`MFC`マップを使用して作成する[メッセージ マップ](../mfc/reference/message-maps-mfc.md)、および`ATL`マップを使用して作成する[オブジェクトのマップ](../atl/reference/object-map-macros.md)です。 ヒント ファイル固有の置換文字列は、マップの開始、中間、および終了要素を示します。 マップ マクロの名前だけでは重要です。 各置換文字列、マクロの実装を意図的にそのため、非表示にします。  
  
 ヒントは、次の構文を使用します。  
  
|構文|説明|  
|------------|-------------|  
|`#define` *ヒント名前**置換文字列*<br /><br /> `#define` *ヒント名前* `(` *パラメーター*、.`)`*置換文字列*|新しいヒントを定義または既存のヒントを再定義するプリプロセッサ ディレクティブです。 プリプロセッサは、ディレクティブの後に一致する各を置き換えます*ヒント名前*ソース コードで*置換文字列*です。<br /><br /> 2 番目の構文形式では、関数のようなヒントを定義します。 関数のようなヒントは、ソース コードで発生する場合、プリプロセッサ最初をすべて置き換えますの*パラメーター*で*置換文字列*ソース コード、および置換の対応する引数を持つ*ヒント名前*で*置換文字列*です。|  
|`@<`|特定のヒント ファイル*置換文字列*最初のマップ要素のセットを示すです。|  
|`@=`|特定のヒント ファイル*置換文字列*中級者向けのマップ要素を示すです。 マップには、複数のマップ要素をことができます。|  
|`@>`|特定のヒント ファイル*置換文字列*マップ要素のセットの末尾を示すです。|  
|`#undef` *ヒント名前*|既存のヒントを削除するプリプロセッサ ディレクティブです。 によって、ヒントの名前が提供される、*ヒント名前*識別子。|  
|`//` *コメント*|単一行コメント。|  
|`/*` *comment* `*/`|複数行のコメント。|  
  
## <a name="what-macros-require-a-hint"></a>どのようなマクロのヒントを必要としますか?  
 マクロの特定の種類は、解析システムに妨げられることができます。 このセクションでは、問題を引き起こす可能性のあるマクロの種類とその問題を解決することができますを作成ヒントの種類について説明します。  
  
### <a name="disruptive-macros"></a>中断を伴うマクロ  
 ソース コードを誤って解釈する解析を行って、システムがブラウザーを損なわずに無視できるいくつかのマクロします。 たとえば、ソース コード注釈言語 ([SAL](../c-runtime-library/sal-annotations.md)) プログラミングのバグを検出するのに役立つ C++ 属性に解決されるマクロです。 SAL 注釈を無視するようにコードを参照する場合は、注釈を非表示にするヒント ファイルを作成することができます。  
  
 次のソース コードで、パラメーターの型の`FormatWindowClassName()`関数は`PXSTR`、パラメーター名と`szBuffer`です。 ただし、解析中のシステムの誤り、`_Pre_notnull_`と`_Post_z_`パラメーターの型またはパラメーター名のいずれかの SAL 注釈。  
  
 **ソース コード:**  
  
```  
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)  
```  
  
 **方法:** 定義は Null  
  
 このような状況に対応する方法が存在しないかのように SAL 注釈を処理します。 これを行うには、置換文字列が null のヒントを指定します。 その結果、解析を行って、システムが、注釈は無視されますと**クラス ビュー**ブラウザーは表示されません。 (Visual C には、SAL 注釈を非表示にする組み込みのヒント ファイルが含まれています)。  
  
 **ヒント ファイル:**  
  
```  
#define _Pre_notnull_  
```  
  
### <a name="concealed-cc-language-elements"></a>非表示の C と C++ の言語要素  
 解析のシステムがソース コードを誤って解釈され、一般的な理由は、マクロが C と C++ を非表示にかどうか[区切り](../cpp/punctuators-cpp.md)または[キーワード](../cpp/keywords-cpp.md)トークンです。 つまり、マクロが含まれます、区切り記号のペアの片方など`<>`、 `[]`、 `{}`、および`()`です。  
  
 次のソース コードで、`START_NAMESPACE`マクロには、対になっていない左中かっこが非表示に (`{`)。  
  
 **ソース コード:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
 **方法:** コピーを直接  
  
 マクロのセマンティクスが閲覧時に重要な場合は、マクロと同じであるヒントを作成します。 解析のシステムでは、ヒント ファイル内の定義に、マクロが解決されます。  
  
 ソース ファイル内のマクロにその他のマクロが含まれている場合、マクロ解釈されるように有効ヒントのセットに既に存在する場合にのみに注意してください。  
  
 **ヒント ファイル:**  
  
```  
#define START_NAMESPACE namespace MyProject {  
```  
  
### <a name="maps"></a>マップ  
 マップは、開始要素、終了要素、および 0 個以上の中間要素を指定するマクロで構成されます。 解析のシステムでは、各マップ マクロは、C と C++ の言語要素を非表示にし、完全な C と C++ ステートメントの構文に多くの別々 のマクロが分散されているために、マップが間違って解釈します。  
  
 次のソース コードを定義、 `BEGIN_CATEGORY_MAP`、 `IMPLEMENTED_CATEGORY`、および`END_CATEGORY_MAP`マクロです。  
  
 **ソース コード:**  
  
```  
#define BEGIN_CATEGORY_MAP(x)\  
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\  
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {  
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },  
#define END_CATEGORY_MAP()\  
   { _ATL_CATMAP_ENTRY_END, NULL } };\  
   return( pMap ); }  
```  
  
 **方法:** マップ要素の識別  
  
 開始、中間 (存在する場合)、および終了のヒントを指定、マップの要素。 特別なマップ置換文字列を使用して`@<`、 `@=`、および`@>`です。 詳細については、次を参照してください。、 `Syntax` 」セクションを参照します。  
  
 **ヒント ファイル:**  
  
```  
// Start of the map.  
#define BEGIN_CATEGORY_MAP(x) @<  
// Intermediate map element.  
#define IMPLEMENTED_CATEGORY( catid ) @=  
// Intermediate map element.  
#define REQUIRED_CATEGORY( catid ) @=  
// End of the map.  
#define END_CATEGORY_MAP() @>  
```  
  
### <a name="composite-macros"></a>複合マクロ  
 複合のマクロには、1 つ以上の解析を行って、システムを混乱させるマクロの種類が含まれています。  
  
 次のソース コードが含まれています、`START_NAMESPACE`マクロで、名前空間スコープの開始を指定するには、および`BEGIN_CATEGORY_MAP`マクロで、マップの開始を指定します。  
  
 **ソース コード:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
 **方法:** コピーを直接  
  
 ヒントを作成、`START_NAMESPACE`と`BEGIN_CATEGORY_MAP`、マクロのヒントを作成し、`NSandMAP`マクロは、ソース コードの前に示したのと同じです。 また、複合マクロは、中断を伴うマクロと空白のみで構成され場合、は、置換文字列が null の定義は、ヒントを定義できます。  
  
 この例では、`START_NAMESPACE`でこのトピックの説明に従って、ヒントは既に、 `Concealed C/C++ Language Elements` subheading です。 見なす`BEGIN_CATEGORY_MAP`前述のヒントを持つ`Maps`します。  
  
 **ヒント ファイル:**  
  
```  
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP  
```  
  
### <a name="inconvenient-macros"></a>不便なマクロ  
 いくつかのマクロは解析のシステムで解釈できるが、ソース コードは、マクロが長か複雑なために、読み取ることが困難です。 ここでは、読みやすさは、マクロの表示を簡略化するヒントを提供できます。  
  
 **ソース コード:**  
  
```  
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)  
```  
  
 **方法:** 単純化  
  
 単純なマクロ定義を表示するヒントを作成します。  
  
 **ヒント ファイル:**  
  
```  
#define STDMETHOD(methodName) void* methodName  
```  
  
## <a name="example"></a>例  
 次の例では、ヒント ファイルからヒントを蓄積する方法を示しています。 ストップ ファイルは、この例では使用されません。  
  
 次の図は、Visual C プロジェクト内の物理ディレクトリの一部を示しています。 ヒント ファイルは、 `vcpackages`、 `Debug`、 `A1`、および`A2`ディレクトリ。  
  
### <a name="hint-file-directories"></a>ヒント ファイルのディレクトリ  
 ![共通およびプロジェクト&#45;特定ヒント ファイルのディレクトリ。] (../ide/media/hintfile.png "HintFile")  
  
### <a name="directories-and-hint-file-contents"></a>ディレクトリとヒント ファイルの内容  
 ヒント ファイル、およびそれらのヒント ファイルの内容を含むこのプロジェクト内のディレクトリを次に示します。 多くのヒントの一部のみ、`vcpackages`ヒント ファイルのディレクトリの一覧が表示されます。  
  
-   vcpackages  
  
    ```  
    // vcpackages (partial list)  
    #define _In_  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    ```  
  
-   デバッグ  
  
    ```  
    // Debug  
    #undef _In_  
    #define OBRACE {  
    #define CBRACE }  
    #define RAISE_EXCEPTION(x) throw (x)  
    #define START_NAMESPACE namespace MyProject {  
    #define END_NAMESPACE }  
    ```  
  
-   A1  
  
    ```  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {  
    ```  
  
-   A2  
  
    ```  
    // A2  
    #undef OBRACE  
    #undef CBRACE  
    ```  
  
### <a name="effective-hints"></a>有効なヒント  
 次の表は、このプロジェクト内のソース ファイルの有効なヒントを示します。  
  
-   ソース ファイル: A1_A2_B.cpp  
  
-   有効なヒント:  
  
    ```  
    // vcpackages (partial list)  
    #define _In_opt_  
    #define _In_z_  
    #define _In_opt_z_  
    #define _In_count_(size)  
    // Debug...  
    #define RAISE_EXCEPTION(x) throw (x)  
    // A1  
    #define START_NAMESPACE namespace A1Namespace {   
    // ...Debug  
    #define END_NAMESPACE }  
    ```  
  
 次の注意事項は、上記のリストに適用されます。  
  
-   有効なヒント、 `vcpackages`、 `Debug`、 `A1`、および`A2`ディレクトリ。  
  
-   **#Undef**ディレクティブで、`Debug`ヒント ファイルが削除されて、`#define _In_`でヒント、`vcpackages`ディレクトリ ヒント ファイル。  
  
-   ヒント ファイルで、`A1`ディレクトリを再定義`START_NAMESPACE`です。  
  
-   `#undef`でヒント、`A2`ディレクトリのヒントを削除する`OBRACE`と`CBRACE`で、`Debug`ディレクトリ ヒント ファイル。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)    
 [#define ディレクティブ (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)   
 [#undef ディレクティブ (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)   
 [SAL 注釈](../c-runtime-library/sal-annotations.md)   
 [メッセージ マップ](../mfc/reference/message-maps-mfc.md)   
 [メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)   
 [オブジェクト マップに関するマクロ](../atl/reference/object-map-macros.md)