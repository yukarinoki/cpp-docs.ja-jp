---
title: ヒント ファイル
ms.date: 11/04/2016
f1_keywords:
- cpp.hint
- vc.hint.file
helpviewer_keywords:
- stop file
- cpp.hint
- hint file
- cpp.stop
- Class View, hint file
ms.assetid: 17194f66-cf62-4523-abec-77db0675ab65
ms.openlocfilehash: 44566408a3afcfee7a15299a5845b5af385aeef8
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320693"
---
# <a name="hint-files"></a>ヒント ファイル

*ヒント ファイル*は、Visual Studio 統合開発環境 (IDE) で、関数やマクロの名前など、Visual C++ の識別子を解釈するのに役立ちます。 Visual C++ プロジェクトを開くと、IDE の*解析システム*によってプロジェクト内の各ソース ファイル内のコードが分析され、すべての識別子に関する情報が収集されます。 その後、それらの情報は**クラス ビュー** ブラウザーや**ナビゲーション バー**などの機能をサポートするために、IDE によって使用されます。

Visual C++ 2010 で導入された解析システムは、C/C++ 構文を理解しますが、マクロを含むステートメントを誤って解釈する場合があります。 記述時にマクロによりソース コードが構文的に不正確になる場合、ステートメントが誤って解釈される場合があります。 ソース コードがコンパイルされ、プリプロセッサにより[マクロ識別子](../preprocessor/hash-define-directive-c-cpp.md)がその定義で置き換えられるときに、ステートメントを構文的に正しくすることができます。 解析システムは、ヒント ファイルを使用してマクロを解釈するため、プロジェクトをビルドしなくても機能します。 そのため、**クラス ビュー**などの参照機能がすぐに使用できます。

ヒント ファイルには、C/C++ マクロ定義と同じ構文を持つ、ユーザーがカスタマイズ可能な*ヒント*が含まれています。 Visual C++ には、ほとんどのプロジェクトにとって十分な組み込みのヒント ファイルが含まれていますが、独自のヒント ファイルを作成することで、Visual Studio の識別子の処理方法を向上させることができます。

> [!IMPORTANT]
> ヒント ファイルを変更または追加する場合は、変更を有効にするため、ソリューション内の .sdf ファイルと VC.db ファイルの両方またはいずれかを削除する必要があります。

## <a name="scenario"></a>シナリオ

**クラス ビュー** ブラウザーで確認するソース ファイルに、次のコードが含まれているとします。 `STDMETHOD` マクロは、1 つのパラメーターを受け取ってポインターを **HRESULT** に返す、`myMethod` という名前のメソッドを宣言します。

```cpp
// Source code file.
STDMETHOD(myMethod)(int parameter1);
```

次のマクロ定義は、別のヘッダー ファイルにあります。

```cpp
// Header file.
#define STDMETHOD(method) HRESULT (STDMETHODCALLTYPE * method)
#define STDMETHODCALLTYPE __stdcall
#define HRESULT void*
```

解析システムは、ソース コードを解釈できません。その理由は、`STDMETHOD` という名前の関数が宣言されているように見え、またその宣言には 2 つのパラメーター リストがあるため構文的に正しくないからです。 解析システムでは、`STDMETHOD`、`STDMETHODCALLTYPE`、および `HRESULT` のマクロの定義を検出するためのヘッダー ファイルが開かれません。 解析システムは `STDMETHOD` マクロを解釈できないため、ステートメント全体を無視して解析を継続します。

プロジェクトが 1 つ以上の重要なヘッダー ファイルに依存している可能性があるため、解析システムではヘッダー ファイルは使用されません。 いずれかのヘッダー ファイルが変更されると、解析システムがプロジェクト内のすべてのヘッダー ファイルを再確認する必要があり、これにより IDE のパフォーマンスが低下する場合があります。 代わりに、解析システムは `STDMETHOD`、`STDMETHODCALLTYPE`、および `HRESULT` のマクロの処理方法を指定するヒントを使用します。

ヒントが必要なことがどうすればわかるでしょうか。 ヒントが必要な場合に、どのようなヒントを作成すればよいでしょうか。 **クラス ビュー**の識別子のビューが**エディター**のビューと一致していない場合は、ヒントが必要であることを示す 1 つのサインです。 たとえば、**クラス ビュー**に存在しているはずのクラス メンバーが表示されない場合、またはメンバーの名前が正しくない場合です。 一般的な問題を解決するヒントの種類の詳細については、このトピックで後述する「ヒントに必要なマクロの種類」のセクションを参照してください。

## <a name="architecture"></a>アーキテクチャ

論理ディレクトリではなく物理ディレクトリに関連するヒント ファイルが、**ソリューション エクスプローラー**に示されます。 ヒント ファイルを有効にするためにヒント ファイルをプロジェクトに追加する必要はありません。 解析システムは、ソース ファイルを解析する場合にのみ、ヒント ファイルを使用します。

すべてのヒント ファイルには **cpp.hint** という名前が付けられます。 そのため、多くのディレクトリにヒント ファイルを含めることができますが、特定のディレクトリには 1 つのヒント ファイルしか含めることはできません。

プロジェクトは、0 個以上のヒント ファイルの影響を受けることがあります。 ヒント ファイルが存在しない場合、解析システムはエラー回復手法を使用して解読できないソース コードを無視します。 それ以外の場合は、解析システムは次の方法を使用してヒントを検索して収集します。

### <a name="search-order"></a>検索順序

解析システムでは、次の順序でヒント ファイルのディレクトリが検索されます。

- Visual C++ のインストール パッケージが格納されているディレクトリ (**vcpackages**)。 このディレクトリには、頻繁に使用されるシステム ファイル (**windows.h** など) のシンボルを説明する組み込みのヒント ファイルが含まれます。 そのため、必要なヒントのほとんどがプロジェクトに自動的に継承されます。

- ソース ファイルのルート ディレクトリからソース ファイル自体を含むディレクトリへのパス。 一般的な Visual C++ プロジェクトでは、ルート ディレクトリには、ソリューションまたはプロジェクト ファイルが含まれます。

   この規則の例外は、*ストップ ファイル*がソース ファイルへのパスにある場合です。 ストップ ファイルは、**cpp.stop** という名前の任意のファイルで、検索順序のより詳細な制御を提供します。 解析システムは、ルート ディレクトリから開始するのではなく、ストップ ファイルを含むディレクトリからソース ファイルを含むディレクトリに検索します。 一般的なプロジェクトでは、ストップ ファイルは必要ありません。

### <a name="hint-gathering"></a>ヒントの収集

ヒント ファイルには、0 個以上の*ヒント*が含まれています。 ヒントは、C/C++ マクロと同じように定義または削除されます。 つまり、`#define` プリプロセッサ ディレクティブはヒントを作成または再定義し、`#undef` ディレクティブはヒントを削除します。

解析システムは、前述した検索順序で各ヒント ファイルを開き、各ファイルのヒントを*エフェクティブ ヒント*に蓄積し、エフェクティブ ヒントを使用してコード内の識別子を解釈します。

解析システムは、次の規則を使用してヒントを蓄積します。

- 新しいヒントでまだ定義されていない名前が指定されている場合、新しいヒントによってその名前がエフェクティブ ヒントに追加されます。

- 新しいヒントで既に定義されている名前が指定されている場合、新しいヒントによって既存のヒントが再定義されます。

- 新しいヒントが既存のエフェクティブ ヒントを指定する `#undef` ディレクティブの場合、新しいヒントによって既存のヒントが削除されます。

最初の規則は、エフェクティブ ヒントが以前に開かれたヒント ファイルから継承されたことを意味します。 最後の 2 つの規則は、検索の順序の後に発生するヒントが以前に発生したヒントをオーバーライドできることを意味します。 たとえば、ソース ファイルが格納されているディレクトリにヒント ファイルを作成すると、前のヒントをオーバーライドできます。

ヒントの収集方法については、このトピックで後述する「`Example`」のセクションを参照してください。

### <a name="syntax"></a>構文

ヒントは、マクロを作成および削除するプリプロセッサ ディレクティブと同じ構文を使用して作成および削除されます。 実際、解析システムは C/C++ プリプロセッサを使用してヒントを評価します。 プリプロセッサ ディレクティブの詳細については、「[#define ディレクティブ (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)」と「[#undef ディレクティブ (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)」を参照してください。

特殊な構文要素は、`@<`、`@=`、および `@>` の置換文字列だけです。 これらはヒント ファイル固有の置換文字列で、*マップ* マクロでのみ使用されます。 マップとは、データ、関数、またはイベントを他のデータ、関数、またはイベント ハンドラーに関連付ける一連のマクロです。 たとえば、`MFC` はマップを使用して[メッセージ マップ](../mfc/reference/message-maps-mfc.md)を作成し、`ATL` はマップを使用して[オブジェクト マップ](../atl/reference/object-map-macros.md)を作成します。 ヒント ファイル固有の置換文字列は、マップの開始要素、中間要素、および終了要素を示します。 重要なのはマップ マクロの名前だけです。 そのため、各置換文字列は、マクロの実装を意図的に非表示にします。

ヒントでは、次の構文を使用します。

|構文|説明|
|------------|-------------|
|`#define` *hint-name* *replacement-string*<br /><br /> `#define` *hint-name* `(` *parameter*, ...`)`*replacement-string*|新しいヒントを定義または既存のヒントを再定義するプリプロセッサ ディレクティブ。 このディレクティブの後に、プリプロセッサはソース コード内で *hint-name* が出現するたび *replacement-string* と置き換えます。<br /><br /> 2 番目の構文形式は、関数に似たヒントを定義します。 関数に似たヒントがソース コード内に出現すると、プリプロセッサは最初に *replacement-string* 内に *parameter* が出現するたびにソース コード内の対応する引数と置き換えてから、*hint-name* を *replacement-string* と置き換えます。|
|`@<`|一連のマップ要素の開始を示すヒント ファイル固有の *replacement-string*。|
|`@=`|一連のマップ要素の開始を示すヒント ファイル固有の *replacement-string*。 1 つのマップで複数のマップ要素を持つことができます。|
|`@>`|一連のマップ要素の終了を示すヒント ファイル固有の *replacement-string*。|
|`#undef` *hint-name*|既存のヒントを削除するプリプロセッサ ディレクティブ。 ヒントの名前は、*hint-name* 識別子によって提供されます。|
|`//` *comment*|単一行コメント。|
|`/*` *comment* `*/`|複数行コメント。|

## <a name="what-macros-require-a-hint"></a>ヒントに必要なマクロの種類

特定の種類のマクロは、解析システムを妨げる場合があります。 このセクションでは、問題を引き起こす可能性のあるマクロの種類とその問題を解決するために作成できるヒントの種類について説明します。

### <a name="disruptive-macros"></a>中断を伴うマクロ

マクロの中には、解析システムにソース コードを誤解釈させるものもありますが、参照エクスペリンスを損うことなく無視することができます。 たとえば、ソース コード注釈言語 ([SAL](../c-runtime-library/sal-annotations.md)) マクロは、プログラミングのバグを検出するのに役立つ C++ 属性に解決されます。 コードの参照時に SAL 注釈を無視する場合は、注釈を非表示にするヒント ファイルを作成することができます。

次のソース コードでは、`FormatWindowClassName()` 関数のパラメーターの型は `PXSTR` で、パラメーター名は `szBuffer` です。 ただし、解析システムはパラメーターの型またはパラメーター名のいずれかの `_Pre_notnull_` と `_Post_z_` の SAL 注釈を誤解します。

**ソース コード:**

```cpp
static void FormatWindowClassName(_Pre_notnull__Post_z_ PXSTR szBuffer)
```

**方法:** Null 定義

このような状況に対応する方法は、SAL 注釈を存在しないかのように処理することです。 これを行うには、置換文字列が null のヒントを指定します。 その結果、解析システムで注釈が無視され、**クラス ビュー** ブラウザーにそれらが表示されなくなります  (Visual C++ には、SAL 注釈を非表示にする組み込みのヒント ファイルが含まれています)。

**ヒント ファイル:**

```cpp.hint
#define _Pre_notnull_
```

### <a name="concealed-cc-language-elements"></a>非表示の C/C++ 言語要素

解析システムでソース コードが誤って解釈される一般的な理由は、マクロが C/C++ [区切り記号](../cpp/punctuators-cpp.md)または[キーワード](../cpp/keywords-cpp.md) トークンを非表示にするからです。 つまり、マクロには、`<>`、`[]`、`{}`、`()` など、区切り記号のペアの片方が含まれる場合があります。

次のソース コードでは、`START_NAMESPACE` マクロは、対になっていない左中かっこ (`{`) を非表示にします。

**ソース コード:**

```cpp
#define START_NAMESPACE namespace MyProject {
```

**方法:** 直接コピー

マクロのセマンティクスが参照エクスペリエンスにとって重要な場合は、マクロと同一のヒントを作成します。 解析システムによって、マクロがヒント ファイル内の定義に解決されます。

ソース ファイル内のマクロに他のマクロが含まれている場合、これらのマクロは、一連のエフェクティブ ヒント内に既にある場合にのみ解釈されることに注意してください。

**ヒント ファイル:**

```cpp.hint
#define START_NAMESPACE namespace MyProject {
```

### <a name="maps"></a>マップ

マップは、開始要素、終了要素、および 0 個以上の中間要素を指定するマクロで構成されます。 各マップ マクロは C/C++ 言語要素を非表示にし、完全な C/C++ ステートメントの構文は多くの別々のマクロに分散されているため、解析システムではマップが誤って解釈されます。

次のソース コードは、`BEGIN_CATEGORY_MAP`、`IMPLEMENTED_CATEGORY`、および `END_CATEGORY_MAP` のマクロを定義します。

**ソース コード:**

```cpp
#define BEGIN_CATEGORY_MAP(x)\
static const struct ATL::_ATL_CATMAP_ENTRY* GetCategoryMap() throw() {\
static const struct ATL::_ATL_CATMAP_ENTRY pMap[] = {
#define IMPLEMENTED_CATEGORY( catid ) { _ATL_CATMAP_ENTRY_IMPLEMENTED, &catid },
#define END_CATEGORY_MAP()\
   { _ATL_CATMAP_ENTRY_END, NULL } };\
   return( pMap ); }
```

**方法:** マップ要素の識別

マップの開始要素、中間要素 (ある場合)、および終了要素のヒントを指定します。 特殊なマップ置換文字列 `@<`、`@=`、および `@>` を使用します。 詳細については、このトピックの「`Syntax`」セクションをご覧ください。

**ヒント ファイル:**

```cpp.hint
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

複合マクロには、解析システムを混乱させる 1 つ以上のマクロの種類が含まれています。

次のソース コードには、名前空間スコープの開始を指定する `START_NAMESPACE` マクロと、マップの開始を指定する `BEGIN_CATEGORY_MAP` マクロが含まれています。

**ソース コード:**

```cpp
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP
```

**方法:** 直接コピー

`START_NAMESPACE` マクロと `BEGIN_CATEGORY_MAP` マクロのヒントを作成してから、ソース コードに対して以前に示したのと同じ `NSandMAP` マクロを作成します。 または、複合マクロが中断を伴うマクロと空白のみで構成されている場合、置換文字列が null 定義のヒントを定義できます。

この例では、`START_NAMESPACE` には「`Concealed C/C++ Language Elements`」の小見出しのこのトピックで説明されているように、既にヒントがあることを前提としています。 また、`BEGIN_CATEGORY_MAP` には前述の `Maps` で説明されているようにヒントがあることを前提としています。

**ヒント ファイル:**

```cpp.hint
#define NSandMAP START_NAMESPACE BEGIN_CATEGORY_MAP
```

### <a name="inconvenient-macros"></a>不便なマクロ

マクロの中には、解析システムで解釈できるものの、マクロが長かったり複雑だったりして、ソース コードの読み取りが困難なものがあります。 読みやすくするため、マクロの表示を簡略化するヒントを提供できます。

**ソース コード:**

```cpp
#define STDMETHOD(methodName) HRESULT (STDMETHODCALLTYPE * methodName)
```

**方法:** 簡略化

より簡略化したマクロ定義を表示するヒントを作成します。

**ヒント ファイル:**

```cpp.hint
#define STDMETHOD(methodName) void* methodName
```

## <a name="example"></a>例

次の例では、ヒント ファイルからヒントが蓄積される方法を示しています。 ストップ ファイルは、この例では使用されません。

次の図は、Visual C++ プロジェクト内の物理ディレクトリの一部を示しています。 ヒント ファイルは、`vcpackages`、`Debug`、`A1`、および `A2` のディレクトリにあります。

### <a name="hint-file-directories"></a>ヒント ファイルのディレクトリ

![共通およびプロジェクト固有のヒント ファイルのディレクトリ。](../ide/media/hintfile.png "HintFile")

### <a name="directories-and-hint-file-contents"></a>ディレクトリとヒント ファイルのコンテンツ

次のリストでは、ヒント ファイルを含むこのプロジェクト内のディレクトリと、これらのヒント ファイルのコンテンツを示しています。 リストに表示されているのは、`vcpackages` ディレクトリ ヒント ファイル内の多くのヒントの一部だけです。

- vcpackages

    ```cpp.hint
    // vcpackages (partial list)
    #define _In_
    #define _In_opt_
    #define _In_z_
    #define _In_opt_z_
    #define _In_count_(size)
    ```

- デバッグ

    ```cpp.hint
    // Debug
    #undef _In_
    #define OBRACE {
    #define CBRACE }
    #define RAISE_EXCEPTION(x) throw (x)
    #define START_NAMESPACE namespace MyProject {
    #define END_NAMESPACE }
    ```

- A1

    ```cpp.hint
    // A1
    #define START_NAMESPACE namespace A1Namespace {
    ```

- A2

    ```cpp.hint
    // A2
    #undef OBRACE
    #undef CBRACE
    ```

### <a name="effective-hints"></a>エフェクティブ ヒント

次の表は、このプロジェクト内のソース ファイルのエフェクティブ ヒントを示しています。

- ソース ファイル:A1_A2_B.cpp

- エフェクティブ ヒント:

    ```cpp.hint
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

- エフェクティブ ヒントは、`vcpackages`、`Debug`、`A1`、および `A2` ディレクトリに格納されています。

- `Debug` ヒント ファイル内の **#undef** ディレクティブにより、`vcpackages` ディレクトリ ヒント ファイル内の `#define _In_` ヒントが削除されました。

- `A1` ディレクトリ内のヒント ファイルは `START_NAMESPACE` を再定義します。

- `A2` ディレクトリ内の `#undef` ヒントにより、`Debug` ディレクトリ ヒント ファイル内の `OBRACE` と `CBRACE` のヒントが削除されました。

## <a name="see-also"></a>参照

[Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[#define ディレクティブ (C/C++)](../preprocessor/hash-define-directive-c-cpp.md)<br>
[#undef ディレクティブ (C/C++)](../preprocessor/hash-undef-directive-c-cpp.md)<br>
[SAL 注釈](../c-runtime-library/sal-annotations.md)<br>
[メッセージ マップ](../mfc/reference/message-maps-mfc.md)<br>
[メッセージ マップ マクロ](../atl/reference/message-map-macros-atl.md)<br>
[オブジェクト マップに関するマクロ](../atl/reference/object-map-macros.md)
