---
description: '詳細情報: #import ディレクティブ (C++)'
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
ms.openlocfilehash: 73768071dd0ee300ad7b2fd2706fda0ed76067ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269277"
---
# <a name="import-directive-c"></a>#import ディレクティブ (C++)

**C++ 固有の仕様**

タイプ ライブラリからの情報を組み込むために使用します。 タイプ ライブラリの内容は、ほとんどが COM インターフェイスを記述した C++ クラスに変換されます。

## <a name="syntax"></a>構文

> **#import**"*filename*" \[ *属性*] \
> **#import** \<*filename*>\[*属性*]

### <a name="parameters"></a>パラメーター

*/db*\
インポートするタイプ ライブラリ ファイルを指定します。 *ファイル名* は、次のいずれかの種類にすることができます。

- .olb、.tlb、.dll ファイルなど、タイプ ライブラリを含むファイルの名前。 キーワードは、 `file:` 各ファイル名の前に置くことができます。

- タイプ ライブラリのコントロールの progid。 キーワードは、 `progid:` 各 progid の前に置くことができます。 次に例を示します。

    ```cpp
    #import "progid:my.prog.id.1.5"
    ```

   Progid の詳細については、「 [ローカライズ ID とバージョン番号の指定](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)」を参照してください。

   64ビットオペレーティングシステムで32ビットクロスコンパイラを使用する場合、コンパイラは32ビットレジストリハイブのみを読み取ることができます。 ネイティブ 64 ビット コンパイラを使用して、64 ビットのタイプ ライブラリをビルドおよび登録した方がよい場合があります。

- タイプ ライブラリのライブラリ ID。 キーワードは、 `libid:` 各ライブラリ ID の前に置くことができます。 次に例を示します。

    ```cpp
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")
    ```

   またはを指定しない場合は `version` `lcid` 、に適用される [規則](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber) `progid:` がにも適用され `libid:` ます。

- 実行可能 (.exe) ファイル。

- タイプライブラリリソース (.ocx など) を含むライブラリ (.dll) ファイル。

- タイプ ライブラリを保持する複合ドキュメント。

- **Loadtypelib** API で認識できるその他のファイル形式。

*アトリビュート*\
1つまたは複数の [#import 属性](#_predir_the_23import_directive_import_attributes)。 複数の属性を指定するときは、空白またはコンマで区切ります。 次に例を示します。

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only
```

\- または -

```cpp
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only
```

## <a name="remarks"></a>解説

### <a name="search-order-for-filename"></a><a name="_predir_the_23import_directive_searchorderforfilename"></a> ファイル名の検索順序

*ファイル名* の前にディレクトリ指定が必要です。 そのファイル名は既存のファイルの名前であることが必要です。 2 つの構文形式間の違いは、パスの指定が不完全であるときに、プリプロセッサがタイプ ライブラリ ファイルを検索する順序です。

|構文形式|アクション|
|-----------------|------------|
|引用符形式|プリプロセッサに対して、 **#import** ステートメントを含むファイルのディレクトリにあるタイプライブラリファイルを検索するように指示します。次に、そのファイルが含まれているファイル () のディレクトリで、そのファイルを検索し `#include` ます。 プリプロセッサは次のパスに従って検索します。|
|山かっこ形式|プリプロセッサに次のパスに従ってタイプ ライブラリ ファイルを検索するように指示します。<br /><br /> 1. `PATH` 環境変数のパスリスト<br />2. `LIB` 環境変数のパスリスト<br />3. [/i](../build/reference/i-additional-include-directories.md) コンパイラオプションで指定されたパス。ただし、コンパイラは、 [no_registry](../preprocessor/no-registry.md) 属性を使用して別のタイプライブラリから参照されたタイプライブラリを検索します。|

### <a name="specify-the-localization-id-and-version-number"></a><a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> ローカライズ ID とバージョン番号を指定します

progid を指定するときに、progid のローカリゼーション ID とバージョン番号も指定できます。 次に例を示します。

```cpp
#import "progid:my.prog.id" lcid("0") version("4.0)
```

ローカライズ ID を指定しない場合、progid は次の規則に従って選択されます。

- ローカライズ ID が1つしかない場合は、その ID が使用されます。

- 複数のローカライズ ID がある場合は、バージョン番号が0、9、または409の最初の ID が使用されます。

- ローカライズ ID が複数あり、そのいずれも0、9、または409ではない場合は、最後の ID が使用されます。

- バージョン番号を指定しない場合は、最新のバージョンが使用されます。

### <a name="header-files-created-by-import"></a><a name="_predir_the_23import_directive_header_files_created_by_import"></a> インポートによって作成されるヘッダーファイル

**#import** は、C++ ソースコードでタイプライブラリの内容を再構築する2つのヘッダーファイルを作成します。 プライマリヘッダーファイルは、Microsoft インターフェイス定義言語 (MIDL) コンパイラによって生成されるものと似ていますが、コンパイラによって生成されるコードとデータが追加されています。 [プライマリヘッダーファイル](#_predir_the_primary_type_library_header_file)には、タイプライブラリと同じ基本名とが含まれています。TLH 拡張。 セカンダリ ヘッダー ファイルには、タイプ ライブラリと同じ基本名と .TLI 拡張子が付けられます。 このファイルは、コンパイラが生成したメンバー関数の実装を格納しており、プライマリ ヘッダー ファイルにインクルード (`#include`) されます。

パラメーターを使用するディスパッチインターフェイスプロパティをインポートする場合 `byref` 、 **#import** は関数の [__declspec (プロパティ)](../cpp/property-cpp.md) ステートメントを生成しません。

両方のヘッダーファイルは、 [/fo (name object file)](../build/reference/fo-object-file-name.md) オプションで指定された出力ディレクトリに配置されます。 次に、プライマリヘッダーファイルにディレクティブで名前が付けられているかのように、コンパイラによって読み取られ、コンパイルされ `#include` ます。

次のコンパイラの最適化には、 **#import** ディレクティブが付属しています。

- ヘッダー ファイルは作成時にタイプ ライブラリと同じタイムスタンプが付けられます。

- **#Import** が処理されると、コンパイラはまずヘッダーが存在し、最新の状態であるかどうかを確認します。 そうであれば、再作成する必要はありません。

**#Import** ディレクティブも最小リビルドに関与し、プリコンパイル済みヘッダーファイルに配置できます。  詳細については、「 [プリコンパイル済みヘッダーファイルの作成](../build/creating-precompiled-header-files.md)」を参照してください。

### <a name="primary-type-library-header-file"></a><a name="_predir_the_primary_type_library_header_file"></a> プライマリタイプライブラリのヘッダーファイル

プライマリ タイプ ライブラリのヘッダー ファイルは、7 つのセクションで構成されます。

- 見出しの定型句: コメント、COMDEF.H の `#include` ステートメント (ヘッダーで使用される標準マクロを定義)、およびその他のセットアップ情報で構成されます。

- 前方参照と typedef: `struct IMyInterface` や typedef のような構造体の宣言で構成されます。

- スマートポインター宣言: テンプレートクラス `_com_ptr_t` はスマートポインターです。 インターフェイスポインターをカプセル化することで、、、およびの各関数を呼び出す必要がなくなり `AddRef` `Release` `QueryInterface` ます。 また、 `CoCreateInstance` 新しい COM オブジェクトを作成するときに呼び出しを非表示にします。 このセクションでは、マクロステートメントを使用し `_COM_SMARTPTR_TYPEDEF` て、 [_com_ptr_t](../cpp/com-ptr-t-class.md) テンプレートクラスのテンプレートの特殊化として COM インターフェイスの typedef を確立します。 たとえば、インターフェイスの場合は、のように `IMyInterface` なります。TLH ファイルには次のものが含まれます。

    ```TLH
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));
    ```

   コンパイラが次のように展開します。

    ```cpp
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;
    ```

   `IMyInterfacePtr` 型は、未加工のインターフェイス ポインター `IMyInterface*` の代わりに使用できます。 そのため、さまざまなメンバー関数を呼び出す必要はありません。 `IUnknown`

- Typeinfo 宣言: は、主にによって返される個々の Typeinfo 項目を公開するクラス定義およびその他の項目で構成されます `ITypeLib:GetTypeInfo` 。 このセクションでは、型ライブラリの各 typeinfo は、`TYPEKIND` 情報に応じてヘッダーに反映されます。

- 旧形式の GUID 定義 (省略可能): 名前付き GUID 定数の初期化が含まれます。 これらの名前の形式は、 `CLSID_CoClass` `IID_Interface` MIDL コンパイラによって生成されるものと同様です。

- セカンダリ タイプ ライブラリ ヘッダーの `#include` ステートメント。

- フッターの定型: 現在 `#pragma pack(pop)` が含まれます。

見出しの定型句とフッターの定型句を除くすべてのセクションは、元の IDL ファイルのステートメントで指定された名前を持つ名前空間で囲まれてい `library` ます。 タイプライブラリヘッダーの名前は、名前空間名を使用した明示的な修飾によって使用できます。 または、次のステートメントを含めることができます。

```cpp
using namespace MyLib;
```

ソースコード内の **#import** ステートメントの直後。

名前空間は、 **#import** ディレクティブの [no_namespace](no-namespace.md)) 属性を使用して抑制できます。 ただし、名前空間を抑制すると、名前の競合が発生する場合があります。 名前空間は、 [rename_namespace](rename-namespace.md) 属性で名前を変更することもできます。

コンパイラは、現在処理しているタイプライブラリに必要なタイプライブラリの依存関係への完全なパスを提供します。 パスは、処理されたタイプ ライブラリごとにコンパイラが生成するタイプ ライブラリ ヘッダー (.TLH) に、コメントの形式で記述されます。

タイプ ライブラリに他のタイプ ライブラリで定義された型への参照が含まれている場合は、.TLH ファイルに次の種類のコメントが含まれます。

```TLH
//
// Cross-referenced type libraries:
//
//  #import "c:\path\typelib0.tlb"
//
```

**#Import** コメント内の実際のファイル名は、レジストリに格納されている、相互参照されるタイプライブラリの完全なパスです。 型定義が存在しないことが原因でエラーが発生した場合は、の先頭にあるコメントを確認してください。TLH を使用すると、最初にインポートする必要がある依存タイプライブラリを確認できます。 .TLI ファイルのコンパイル中に考えられるエラーは、構文エラー (C2143、C2146、C2321 など)、C2501 (decl-specifier の欠落)、または C2433 (データ宣言子内でのインライン禁止) です。

依存関係エラーを解決するには、システムヘッダーによって提供されない依存関係コメントを確認し、依存タイプライブラリの **#import** ディレクティブの前にある時点で **#import** ディレクティブを指定します。

### <a name="import-attributes"></a><a name="_predir_the_23import_directive_import_attributes"></a> #import 属性

**#import** には、必要に応じて1つ以上の属性を含めることができます。 これらの属性は、コンパイラにタイプ ライブラリ ヘッダーの内容を変更するように指示します。 円記号 () を使用すると、 **\\** 1 つの **#import** ステートメントに追加の行を含めることができます。 次に例を示します。

```cpp
#import "test.lib" no_namespace \
   rename("OldName", "NewName")
```

詳細については、「 [属性の #import](../preprocessor/hash-import-attributes-cpp.md)」を参照してください。

**END C++ 固有の仕様**

## <a name="see-also"></a>関連項目

[プリプロセッサディレクティブ](../preprocessor/preprocessor-directives.md)\
[コンパイラの COM サポート](../cpp/compiler-com-support.md)
