---
title: '#import ディレクティブ (C++)'
ms.date: 08/29/2019
f1_keywords:
- '#import'
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
ms.openlocfilehash: 9cdfef091b659151f427c381e386f0e83396e741
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332068"
---
# <a name="import-directive-c"></a>#import ディレクティブ (C++)

**C++ 固有の仕様**

タイプ ライブラリからの情報を組み込むために使用します。 タイプ ライブラリの内容は、ほとんどが COM インターフェイスを記述した C++ クラスに変換されます。

## <a name="syntax"></a>構文

> **#import**"*ファイル名*" \[*属性*]\
> > ファイル\[*名***属性] を#import**\<します。*attributes*

### <a name="parameters"></a>パラメーター

*Filename*\
インポートするタイプ ライブラリ ファイルを指定します。 *ファイル名*は、次のいずれかの種類です。

- .olb、.tlb、.dll ファイルなど、タイプ ライブラリを含むファイルの名前。 キーワード 、`file:`は、各ファイル名の前に置くことができます。

- タイプ ライブラリのコントロールの progid。 キーワード は`progid:`、各宣言の前に置くことができます。 次に例を示します。

    ```cpp
    #import "progid:my.prog.id.1.5"
    ```

   progid の詳細については、[ローカリゼーション ID とバージョン番号の指定を](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)参照してください。

   64 ビット オペレーティング システムで 32 ビット クロス コンパイラを使用する場合、コンパイラは 32 ビット レジストリ ハイブのみを読み取ることができます。 ネイティブ 64 ビット コンパイラを使用して、64 ビットのタイプ ライブラリをビルドおよび登録した方がよい場合があります。

- タイプ ライブラリのライブラリ ID。 キーワード は`libid:`、各ライブラリー ID の前に置くことができます。 次に例を示します。

    ```cpp
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")
    ```

   または`version``lcid`を指定しない場合、適用`progid:`される[規則](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)も に`libid:`適用されます。

- 実行可能 (.exe) ファイル。

- タイプ ライブラリ リソース (.ocx など) を含むライブラリ (.dll) ファイル。

- タイプ ライブラリを保持する複合ドキュメント。

- **読み込みタイプライブラリ**API で理解できるその他のファイル形式。

*属性*\
1 つまたは複数の[#import属性](#_predir_the_23import_directive_import_attributes)。 複数の属性を指定するときは、空白またはコンマで区切ります。 次に例を示します。

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only
```

\- または -

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only
```

## <a name="remarks"></a>解説

### <a name="search-order-for-filename"></a><a name="_predir_the_23import_directive_searchorderforfilename"></a>ファイル名の検索順序

*filename*は、オプションでディレクトリ指定の前に置かれます。 そのファイル名は既存のファイルの名前であることが必要です。 2 つの構文形式間の違いは、パスの指定が不完全であるときに、プリプロセッサがタイプ ライブラリ ファイルを検索する順序です。

|構文形式|アクション|
|-----------------|------------|
|引用符形式|#import**ステートメントを**含むファイルのディレクトリで、最初にタイプ ライブラリ ファイルを検索し、次にそのファイルを含むファイル (`#include`) のディレクトリで、タイプ ライブラリ ファイルを検索するようにプリプロセッサに指示します。 プリプロセッサは次のパスに従って検索します。|
|山かっこ形式|プリプロセッサに次のパスに従ってタイプ ライブラリ ファイルを検索するように指示します。<br /><br /> 1.`PATH`環境変数パスリスト<br />2.`LIB`環境変数パスリスト<br />3. [/I](../build/reference/i-additional-include-directories.md)コンパイラ オプションで指定されたパスは、コンパイラが[no_registry](../preprocessor/no-registry.md)属性を持つ別のタイプ ライブラリから参照されたタイプ ライブラリを検索している場合を除く。|

### <a name="specify-the-localization-id-and-version-number"></a><a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a>ローカリゼーション ID とバージョン番号を指定する

progid を指定するときに、progid のローカリゼーション ID とバージョン番号も指定できます。 次に例を示します。

```cpp
#import "progid:my.prog.id" lcid("0") version("4.0)
```

ローカリゼーション ID を指定しない場合、progid は次の規則に従って選択されます。

- ローカリゼーション ID が 1 つしかない場合は、その ID が使用されます。

- 複数のローカリゼーション ID がある場合は、バージョン番号 0、9、または 409 の最初の ID が使用されます。

- 複数のローカリゼーション ID があり、0、9、または 409 のいずれの場合も、最後の 1 つが使用されます。

- バージョン番号を指定しない場合は、最新バージョンが使用されます。

### <a name="header-files-created-by-import"></a><a name="_predir_the_23import_directive_header_files_created_by_import"></a>インポートによって作成されたヘッダー ファイル

**#import** C++ ソース コードでタイプ ライブラリの内容を再構築する 2 つのヘッダー ファイルを作成します。 プライマリ ヘッダー ファイルは、Microsoft インターフェイス定義言語 (MIDL) コンパイラによって生成されるものと似ていますが、コンパイラによって生成されたコードとデータが追加されています。 [プライマリ ヘッダー ファイル](#_predir_the_primary_type_library_header_file)は、タイプ ライブラリと同じベース名に加えて、 .TLH 拡張。 セカンダリ ヘッダー ファイルには、タイプ ライブラリと同じ基本名と .TLI 拡張子が付けられます。 このファイルは、コンパイラが生成したメンバー関数の実装を格納しており、プライマリ ヘッダー ファイルにインクルード (`#include`) されます。

パラメーターを使用`byref`する dispinterface プロパティをインポートする場合 **、#import**関数の[__declspec(プロパティ)](../cpp/property-cpp.md)ステートメントは生成されません。

両方のヘッダー ファイルは[、/Fo (オブジェクト ファイル名)](../build/reference/fo-object-file-name.md)オプションで指定された出力ディレクトリに配置されます。 その後、プライマリ ヘッダー ファイルがディレクティブによって名前が付けられたかのように、コンパイラによって読み`#include`取られ、コンパイルされます。

次のコンパイラの最適化には **、#import**ディレクティブが付属しています。

- ヘッダー ファイルは作成時にタイプ ライブラリと同じタイムスタンプが付けられます。

- **#import**処理されると、コンパイラはまずヘッダーが存在し、最新の状態であるかどうかをチェックします。 「はい」の場合は、再作成する必要はありません。

**#import**ディレクティブは、最小限の再構築にも関与し、プリコンパイル済みヘッダー ファイルに配置できます。  詳細については、「[プリコンパイル済みヘッダー ファイルの作成](../build/creating-precompiled-header-files.md)」を参照してください。

### <a name="primary-type-library-header-file"></a><a name="_predir_the_primary_type_library_header_file"></a>プライマリ タイプ ライブラリ ヘッダー ファイル

プライマリ タイプ ライブラリのヘッダー ファイルは、7 つのセクションで構成されます。

- 見出しの定型句: コメント、COMDEF.H の `#include` ステートメント (ヘッダーで使用される標準マクロを定義)、およびその他のセットアップ情報で構成されます。

- 前方参照と typedef: `struct IMyInterface` や typedef のような構造体の宣言で構成されます。

- スマート ポインター宣言: テンプレート`_com_ptr_t`クラスはスマート ポインターです。 インターフェイス ポインターをカプセル化し、 、`AddRef``Release`および`QueryInterface`関数を呼び出す必要がなくなります。 また、新しい`CoCreateInstance`COM オブジェクトを作成するときに呼び出しを非表示にします。 このセクションでは、マクロ`_COM_SMARTPTR_TYPEDEF`ステートメントを使用して[、_com_ptr_t](../cpp/com-ptr-t-class.md)テンプレート クラスのテンプレート特殊化として COM インターフェイスの typedef を確立します。 たとえば、インターフェイス`IMyInterface`の場合は、 .TLH ファイルには次の内容が含まれます。

    ```TLH
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
    ```

   コンパイラが次のように展開します。

    ```cpp
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;
    ```

   `IMyInterfacePtr` 型は、未加工のインターフェイス ポインター `IMyInterface*` の代わりに使用できます。 したがって、さまざまな`IUnknown`メンバー関数を呼び出す必要はありません。

- Typeinfo 宣言: 主にクラス定義と、によって返される個々の typeinfo 項目`ITypeLib:GetTypeInfo`を公開するその他の項目で構成されます。 このセクションでは、型ライブラリの各 typeinfo は、`TYPEKIND` 情報に応じてヘッダーに反映されます。

- 旧形式の GUID 定義 (省略可能): 名前付き GUID 定数の初期化が含まれます。 これらの名前には、MIDL コンパイラによって生成される名前と同様の形式`CLSID_CoClass`と`IID_Interface`が付きます。

- セカンダリ タイプ ライブラリ ヘッダーの `#include` ステートメント。

- フッターの定型: 現在 `#pragma pack(pop)` が含まれます。

見出しの定型句とフッターの定型セクションを除くすべてのセクションは、元の IDL ファイル`library`内のステートメントで指定された名前を持つ名前空間で囲まれます。 名前空間名を使用して明示的な修飾によって、タイプ ライブラリ ヘッダーの名前を使用できます。 または、次のステートメントを含めることができます。

```cpp
using namespace MyLib;
```

ソース コードの **#import**ステートメントの直後。

**名前空間は、#import**ディレクティブの[no_namespace](no-namespace.md)) 属性を使用して抑制できます。 ただし、名前空間を抑制すると、名前の競合が発生する場合があります。 名前空間は[、rename_namespace](rename-namespace.md)属性によって名前を変更することもできます。

コンパイラは、現在処理しているタイプ ライブラリに必要なタイプ ライブラリの依存関係への完全パスを提供します。 パスは、処理されたタイプ ライブラリごとにコンパイラが生成するタイプ ライブラリ ヘッダー (.TLH) に、コメントの形式で記述されます。

タイプ ライブラリに他のタイプ ライブラリで定義された型への参照が含まれている場合は、.TLH ファイルに次の種類のコメントが含まれます。

```TLH
//
// Cross-referenced type libraries:
//
//  #import "c:\path\typelib0.tlb"
//
```

**#import**コメントの実際のファイル名は、レジストリに格納されている相互参照型ライブラリの完全パスです。 型定義の欠落によってエラーが発生した場合は、 の先頭にあるコメントを確認してください。TLH を使用して、最初にインポートする必要がある依存タイプ ライブラリを確認します。 .TLI ファイルのコンパイル中に考えられるエラーは、構文エラー (C2143、C2146、C2321 など)、C2501 (decl-specifier の欠落)、または C2433 (データ宣言子内でのインライン禁止) です。

依存関係エラーを解決するには、システム ヘッダーで提供されていない依存関係コメントを特定し、依存タイプ ライブラリの **#import**ディレクティブの前に、ある時点で **#import**ディレクティブを指定します。

### <a name="import-attributes"></a><a name="_predir_the_23import_directive_import_attributes"></a>#import属性

**#import**には、オプションで 1 つ以上の属性を含めることができます。 これらの属性は、コンパイラにタイプ ライブラリ ヘッダーの内容を変更するように指示します。 円記号 (**\\**) を使用すると、1 つの **#import**ステートメントに追加の行を含めることができます。 次に例を示します。

```cpp
#import "test.lib" no_namespace \
   rename("OldName", "NewName")
```

詳細については、「[属性の#import」](../preprocessor/hash-import-attributes-cpp.md)を参照してください。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)\
[コンパイラ COM のサポート](../cpp/compiler-com-support.md)
