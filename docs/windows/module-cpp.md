---
title: モジュール (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.module
dev_langs:
- C++
helpviewer_keywords:
- module attributes
ms.assetid: 02223b2a-62b5-4262-832f-564b1e11e58e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce7925fd15a7a332dbfb18e2a22dc104783300b7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="module-c"></a>module (C++)
.idl ファイルのライブラリ ブロックを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
  
      [ module (  
   type=dll,  
   name=string,  
   version=1.0,  
   uuid=uuid,  
   lcid=integer,  
   control=boolean,  
   helpstring=string,  
   helpstringdll=string,  
   helpfile=string,  
   helpcontext=integer,  
   helpstringcontext=integer,  
   hidden=boolean,  
   restricted=boolean,  
   custom=string,  
   resource_name=string,  
) ];  
```  
  
#### <a name="parameters"></a>パラメーター  
 ***type***  (省略可能)  
 次のいずれかの値を指定します。  
  
-   **dll** 結果の DLL がインプロセス COM サーバーとして機能することを許可する関数およびクラスを追加します。 これが既定値です。  
  
-   **exe** 結果の実行可能ファイルがアウトプロセス COM サーバーとして機能することを許可する関数およびクラスを追加します。  
  
-   **service** 結果の実行可能ファイルが NT サービスとして機能することを許可する関数およびクラスを追加します。  
  
-   **unspecified** モジュール属性と関連する ATL コードの挿入 (ATL モジュール クラス、グローバル インスタンス _AtlModule およびエントリ ポイント関数の挿入) を無効にします。  プロジェクト内のその他の属性による ATL コードの挿入は無効になりせん。  
  
 ***name***  (省略可能)  
 ライブラリ ブロックの名前です。  
  
 ***version***  (省略可能)  
 ライブラリ ブロックに割り当てるバージョン番号です。 既定値は 1.0 です。  
  
 `uuid`  
 ライブラリの一意の ID です。 このパラメーターを省略した場合、ライブラリの ID は自動的に生成されます。 取得する必要があります、 *uuid* 、識別子を使用して行うことができます、ライブラリ ブロックの **_ _uuidof (***libraryname***)** です。  
  
 **lcid**  
 ローカリゼーション パラメーターです。 詳細については、「 [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) 」を参照してください。  
  
 **control** (省略可能)  
 ライブラリ内のすべてのコクラスがコントロールであることを指定します。  
  
 **helpstring**  
 タイプ ライブラリを指定します。  
  
 ***helpstringdll***  (省略可能)  
 ドキュメントの文字列を検索する .dll ファイルの名前を設定します。 詳細については、「 [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) 」を参照してください。  
  
 **helpfile** (省略可能)  
 タイプ ライブラリのヘルプ ファイルの名前です。  
  
 **helpcontext** (省略可能)  
 このタイプ ライブラリのヘルプ ID です。  
  
 **helpstringcontext** (省略可能)  
 詳細については、「 [helpstringcontext](../windows/helpstringcontext.md) 」を参照してください。  
  
 **hidden** (省略可能)  
 ライブラリ全体が表示されないようにします。 これは、コントロールと共に使用します。 ホストは、拡張プロパティを使用し、コントロールをラップする新しいタイプ ライブラリを作成する必要があります。 詳細については、「 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) 」の MIDL 属性に関する説明を参照してください。  
  
 **restricted** (省略可能)  
 ライブラリのメンバーは、任意に呼び出すことはできません。 詳細については、「 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) 」の MIDL 属性に関する説明を参照してください。  
  
 ***custom***  (省略可能)  
 1 つ以上の属性です。これは、 [custom](../windows/custom-cpp.md) 属性と似ています。 `custom` の最初のパラメーターがこの属性の GUID です。 例えば:  
  
```  
[module(custom={guid,1}, custom={guid1,2})]  
```  
  
 **resource_name**  
 DLL、実行可能ファイルまたはサービスの登録に使用される .rgs ファイルの文字列リソース ID です。 モジュールがタイプ サービスである場合、この引数はサービス名を含む文字列の ID の取得にも使用されます。  
  
> [!NOTE]
>  .rgs ファイルとサービス名を含む文字列の両方に、同じ数値が必要です。  
  
## <a name="remarks"></a>コメント  
 **restricted** パラメーターを [emitidl](../windows/emitidl.md)に指定した場合を除き、C++ 属性を使用するすべてのプログラムで **module** が必要です。  
  
 ライブラリ ブロックは、ソース コードで、 **module** 属性に加え、 [dispinterface](../windows/dispinterface.md)、 [dual](../windows/dual.md)、 [object](../windows/object-cpp.md)、または [coclass](../windows/coclass.md)を意味する属性も使用されている場合に作成されます。  
  
 .idl ファイルでは、1 つのライブラリ ブロックが許可されています。 ソース コードに複数のモジュールのエントリがある場合、実装されている最新のパラメーター値と結合されます。  
  
 この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 上記の動作に加え、属性により、正しい種類のグローバル オブジェクト ( **_AtlModule**と呼ばれる) と追加のサポート コードも挿入されます。 属性がスタンドアロンの場合、正しいモジュールの種類から派生したクラスが挿入されます。 属性がクラスに適用された場合、正しいモジュールの種類の基本クラスが追加されます。 正しい種類は、 `type` パラメーターの値によって決まります。  
  
-   `type` = **dll**  
  
     [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) は COM サーバーに必要な基本クラスと標準の DLL エントリ ポイントとして使用されます。 これらのエントリ ポイントは、 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)、 [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162)、 [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457)、 [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368)、および [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891)です。  
  
-   `type` = **exe**  
  
     [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) は、基本クラスおよび標準の実行可能ファイルのエントリ ポイント [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)として使用されます。  
  
-   `type` = **service**  
  
     [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) は、基本クラスおよび標準の実行可能ファイルのエントリ ポイント [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)として使用されます。  
  
-   `type` = **unspecified**  
  
     モジュール属性と関連する ATL コードの挿入を無効にします。  
  
## <a name="example"></a>例  
 生成された .idl ファイルにライブラリ ブロックを作成する方法を次のコードで示します。  
  
```  
// cpp_attr_ref_module1.cpp  
// compile with: /LD  
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];  
```  
  
 次のコードは、 **module**を使用した結果、挿入されたコード内に表示される独自の関数を実装できることを示しています。 挿入されたコードを参照する方法の詳細については、「 [/Fx](../build/reference/fx-merge-injected-code.md) 」を参照してください。 **module** 属性によって挿入された関数の 1 つをオーバーライドするには、実装した関数を含めるクラスを作成し、そのクラスに **module** 属性を含めます。  
  
```  
// cpp_attr_ref_module2.cpp  
// compile with: /LD /link /OPT:NOREF  
#include <atlbase.h>  
#include <atlcom.h>  
#include <atlwin.h>  
#include <atltypes.h>  
#include <atlctl.h>  
#include <atlhost.h>  
#include <atlplus.h>  
  
// no semicolon after attribute block  
[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]   
// module attribute now applies to this class  
class CMyClass {  
public:  
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {  
   // add your own code here  
   return __super::DllMain(dwReason, lpReserved);  
   }  
};  
```  
  
## <a name="requirements"></a>要件  
  
### <a name="attribute-context"></a>属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意の場所|  
|**反復可能**|×|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [IDL 属性](../windows/idl-attributes.md)   
 [クラス属性](../windows/class-attributes.md)   
 [スタンドアロン属性](../windows/stand-alone-attributes.md)   
 [Typedef、Enum、Union、および struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)   
 [usesgetlasterror](../windows/usesgetlasterror.md)   
 [ライブラリ](http://msdn.microsoft.com/library/windows/desktop/aa367069)   
 [helpcontext](../windows/helpcontext.md)   
 [helpstring](../windows/helpstring.md)   
 [ヘルプ ファイル](../windows/helpfile.md)   
 [version](../windows/version-cpp.md)   
