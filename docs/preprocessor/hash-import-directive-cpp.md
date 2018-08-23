---
title: '#インポート ディレクティブ (C++) |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#import'
dev_langs:
- C++
helpviewer_keywords:
- .tlh files
- '#import directive'
- import directive (#import)
- tlh files
- tlbid switch
- preprocessor, directives
- COM, type library header file
ms.assetid: 787d1112-e543-40d7-ab15-a63d43f4030a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30c1cd29a48b5a47f64e5a5148a157d5120d45e3
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/10/2018
ms.locfileid: "42538842"
---
# <a name="import-directive-c"></a>#import ディレクティブ (C++)
**C++ 固有の仕様**  
  
タイプ ライブラリからの情報を組み込むために使用します。 タイプ ライブラリの内容は、ほとんどが COM インターフェイスを記述した C++ クラスに変換されます。  
  
## <a name="syntax"></a>構文  
  
```  
#import "filename" [attributes]  
#import <filename> [attributes]  
```  
  
### <a name="parameters"></a>パラメーター  
*ファイル名*  
インポートするタイプ ライブラリ ファイルを指定します。 *ファイル名*次のいずれかを指定できます。  
  
- .olb、.tlb、.dll ファイルなど、タイプ ライブラリを含むファイルの名前。 キーワード、**ファイル:**、各ファイル名の前に記述できます。  
  
- タイプ ライブラリのコントロールの progid。 キーワード、 **progid:**、各 progid 名前に記述できます。 例えば:  
  
    ```  
    #import "progid:my.prog.id.1.5"  
    ```  
  
     詳細については、progid は、次を参照してください。[ローカリゼーション ID とバージョン番号を指定する](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)します。  
  
     64 ビット オペレーティング システム上でクロス コンパイラによりコンパイルを実行した場合、コンパイラは 32 ビット レジストリ ハイブのみ読み取り可能になることに注意してください。 ネイティブ 64 ビット コンパイラを使用して、64 ビットのタイプ ライブラリをビルドおよび登録した方がよい場合があります。  
  
- タイプ ライブラリのライブラリ ID。 キーワード、 **libid:**、各ライブラリ ID の前に記述できます 例えば:  
  
    ```  
    #import "libid:12341234-1234-1234-1234-123412341234" version("4.0") lcid("9")  
    ```  
  
     バージョンまたは lcid を指定しない場合、[ルール](#_predir_the_23import_directive_specifyingthelocalizationidandversionnumber)に適用される**progid:** にも適用されます**libid:** します。  
  
- 実行可能 (.exe) ファイル。  
  
- タイプ ライブラリのリソース (.ocx など) を含むライブラリ (.dll) ファイル。  
  
- タイプ ライブラリを保持する複合ドキュメント。  
  
- によって認識できるその他のファイル形式、 **LoadTypeLib** API。  
  
*属性*  
1 つまたは複数[#import 属性](#_predir_the_23import_directive_import_attributes)します。 複数の属性を指定するときは、空白またはコンマで区切ります。 例えば:  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace, raw_interfaces_only  
```  
  
- または -  
  
```  
#import "..\drawctl\drawctl.tlb" no_namespace raw_interfaces_only  
```  
  
## <a name="remarks"></a>Remarks  
  
##  <a name="_predir_the_23import_directive_searchorderforfilename"></a> ファイル名の検索順序  

*ファイル名*ディレクトリの指定の前に、必要に応じて。 そのファイル名は既存のファイルの名前であることが必要です。 2 つの構文形式間の違いは、パスの指定が不完全であるときに、プリプロセッサがタイプ ライブラリ ファイルを検索する順序です。  
  
|構文形式|アクション|  
|-----------------|------------|  
|引用符形式|最初に格納するファイルのディレクトリのタイプ ライブラリ ファイルを検索するプリプロセッサに指示、 **#import**ステートメント、し、次が含まれるすべてのファイルのディレクトリに (`#include`) ファイル。 プリプロセッサは次のパスに従って検索します。|  
|山かっこ形式|プリプロセッサに次のパスに従ってタイプ ライブラリ ファイルを検索するように指示します。<br /><br /> 1.`PATH`環境変数パス リスト<br />2.`LIB`環境変数パス リスト<br />3./I で指定されたパス (追加インクルード ディレクトリ) を持つ別のタイプ ライブラリから参照されたタイプ ライブラリ、コンパイラが検索ことを除けば、コンパイラ オプション、 [no_registry](../preprocessor/no-registry.md)属性。|  
  
##  <a name="_predir_the_23import_directive_specifyingthelocalizationidandversionnumber"></a> ローカリゼーション ID とバージョン番号を指定します。  

progid を指定するときに、progid のローカリゼーション ID とバージョン番号も指定できます。 例えば:  
  
```  
#import "progid:my.prog.id" lcid("0") version("4.0)  
```  
  
ローカリゼーション ID を指定しない場合、progid は、次の規則に従って選択されます。  
  
- ローカリゼーション ID が 1 つしかない場合、その ID が使用されます。  
  
- ローカリゼーション ID が複数ある場合、バージョン番号が 0、9、または 409 の最初の ID が使用されます。  
  
- ローカリゼーション ID が複数あり、それらのいずれも 0、9、または 409 ではない場合、最後の ID が使用されます。  
  
- バージョン番号を指定しない場合、最も新しいバージョンが使用されます。  
  
##  <a name="_predir_the_23import_directive_header_files_created_by_import"></a> インポートによって作成されたヘッダー ファイル  

**#import** C++ ソース コードでタイプ ライブラリの内容を再構築する 2 つのヘッダー ファイルを作成します。 プライマリ ヘッダー ファイルは、Microsoft インターフェイス定義言語 (MIDL) コンパイラによって生成されるものと似ていますが、より多くのコードとデータがコンパイラによって生成されます。 [プライマリ ヘッダー ファイル](#_predir_the_primary_type_library_header_file)タイプ ライブラリと同じ基本名を持つとします。TLH 拡張機能。 セカンダリ ヘッダー ファイルには、タイプ ライブラリと同じ基本名と .TLI 拡張子が付けられます。 このファイルは、コンパイラが生成したメンバー関数の実装を格納しており、プライマリ ヘッダー ファイルにインクルード (`#include`) されます。  
  
Byref パラメーターを使用するディスパッチ インターフェイスのプロパティをインポートするには、#import は生成されません _ _declspec ([プロパティ](../cpp/property-cpp.md)) 関数のステートメント。  
  
ヘッダー ファイルは両方とも、/Fo (オブジェクト ファイルを指定) オプションで指定された出力ディレクトリに保存されます。 それらのファイルは、プライマリ ヘッダー ファイルが `#include` ディレクティブで指定されているように、コンパイラによって読み取られてコンパイルされます。  
  
次のコンパイラの最適化が付属、 **#import**ディレクティブ。  
  
- ヘッダー ファイルは作成時にタイプ ライブラリと同じタイムスタンプが付けられます。  
  
- ときに **#import**が処理するには、コンパイラはまず、ヘッダーが存在し、最新の状態は、かどうか。 最新のヘッダーが存在する場合、再作成は不要です。  
  
**#Import**ディレクティブも最小リビルドに参加し、プリコンパイル済みヘッダー ファイルに配置することができます。 参照してください[プリコンパイル済みヘッダー ファイルの作成](../build/reference/creating-precompiled-header-files.md)詳細についてはします。  
  
###  <a name="_predir_the_primary_type_library_header_file"></a> プライマリ タイプ ライブラリ ヘッダー ファイル  
プライマリ タイプ ライブラリのヘッダー ファイルは、7 つのセクションで構成されます。  
  
- 見出しの定型句: コメント、COMDEF.H の `#include` ステートメント (ヘッダーで使用される標準マクロを定義)、およびその他のセットアップ情報で構成されます。  
  
- 前方参照と typedef: `struct IMyInterface` や typedef のような構造体の宣言で構成されます。  
  
- スマート ポインター宣言: テンプレート クラスは、`_com_ptr_t`インターフェイス ポインターをカプセル化しを呼び出す必要がなくなりますスマート ポインターの実装は、 `AddRef`、 `Release`、`QueryInterface`関数。 また、新しい COM オブジェクトの作成時に `CoCreateInstance` 呼び出しを隠します。 このセクションでは、マクロのステートメントを使用して`_COM_SMARTPTR_TYPEDEF`のテンプレート特殊化である COM インターフェイスの typedef を確立するために、 [_com_ptr_t](../cpp/com-ptr-t-class.md)テンプレート クラス。 たとえば、インターフェイス`IMyInterface`、します。TLH ファイルが含まれます。  
  
    ```  
    _COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
    ```  
  
     コンパイラが次のように展開します。  
  
    ```  
    typedef _com_ptr_t<_com_IIID<IMyInterface, __uuidof(IMyInterface)> > IMyInterfacePtr;  
    ```  
  
     `IMyInterfacePtr` 型は、未加工のインターフェイス ポインター `IMyInterface*` の代わりに使用できます。 その結果、さまざまなを呼び出す必要はありません`IUnknown`メンバー関数  
  
- Typeinfo 宣言: クラス定義とその他のアイテムによって返される個々 の typeinfo 項目を公開するは、主に`ITypeLib:GetTypeInfo`します。 このセクションでは、型ライブラリの各 typeinfo は、`TYPEKIND` 情報に応じてヘッダーに反映されます。  
  
- 旧形式の GUID 定義 (省略可能): 名前付き GUID 定数の初期化が含まれます。 これらは、フォーム名`CLSID_CoClass`と`IID_Interface`、MIDL コンパイラによって生成されたものと似ています。  
  
- セカンダリ タイプ ライブラリ ヘッダーの `#include` ステートメント。  
  
- フッターの定型: 現在 `#pragma pack(pop)` が含まれます。  
  
見出し定型句およびフッターの定型コード」セクションを除く、すべてのセクションは、名前空間内で指定された名前で囲まれた、`library`元の IDL ファイル内のステートメント。 名前空間名による明示的な修飾、または次のステートメントを含めることによって、タイプ ライブラリ ヘッダーの名前を使用できます。  
  
```  
using namespace MyLib;  
```  
  
直後に、 **#import**ソース コード内のステートメント。  
  
使用して、名前空間を抑制することができます、 [no_namespace](#_predir_no_namespace)の属性、 **#import**ディレクティブ。 ただし、名前空間を抑制すると、名前の競合が発生する場合があります。 名前空間を変更することも、 [rename_namespace](#_predir_rename_namespace)属性。  
  
コンパイラは、現在処理しているタイプ ライブラリに必要で依存関係のあるタイプ ライブラリへの完全なパスを提供します。 パスは、処理されたタイプ ライブラリごとにコンパイラが生成するタイプ ライブラリ ヘッダー (.TLH) に、コメントの形式で記述されます。  
  
タイプ ライブラリに他のタイプ ライブラリで定義された型への参照が含まれている場合は、.TLH ファイルに次の種類のコメントが含まれます。  
  
```  
//  
// Cross-referenced type libraries:  
//  
//  #import "c:\path\typelib0.tlb"  
//  
```  
  
実際のファイル名で、 **#import**レジストリに格納されている、コメントは、相互参照されるタイプ ライブラリの完全パス。 不明な型定義が原因のエラーが発生した場合は、.TLH の先頭のコメントを調べて、依存関係のあるどのタイプ ライブラリを最初にインポートする必要があるかを確認します。 .TLI ファイルのコンパイル中に考えられるエラーは、構文エラー (C2143、C2146、C2321 など)、C2501 (decl-specifier の欠落)、または C2433 (データ宣言子内でのインライン禁止) です。  
  
必要がありますを決定する依存関係のコメントが定義されていないのでは、システム ヘッダーと提供し、 **#import**ディレクティブより前に、の時点で、 **#import**依存のディレクティブエラーを解決するタイプ ライブラリ。  
  
詳細については、サポート技術情報の「#import Wrapper Methods May Cause Access Violation (Q242527)」または「Compiler Errors When You Use #import with XML (Q269194)」を参照してください。 MSDN ライブラリ メディアまたはサポート情報記事を見つけることができます[Microsoft サポート](https://support.microsoft.com/)します。  
  
##  <a name="_predir_the_23import_directive_import_attributes"></a> #import の属性  
 
**#import**必要に応じて、1 つまたは複数の属性を含めることができます。 これらの属性は、コンパイラにタイプ ライブラリ ヘッダーの内容を変更するように指示します。 円記号 (**\\**) を 1 つの追加の行を含めるシンボルを使用することができます **#import**ステートメント。 例えば:  
  
```  
#import "test.lib" no_namespace \  
   rename("OldName", "NewName")  
```  
  
詳細については、次を参照してください。 [#import 属性](../preprocessor/hash-import-attributes-cpp.md)します。  
  
**END C 固有の仕様**  
  
## <a name="see-also"></a>関連項目  

[プリプロセッサ ディレクティブ](../preprocessor/preprocessor-directives.md)   
[コンパイラ COM サポート](../cpp/compiler-com-support.md)