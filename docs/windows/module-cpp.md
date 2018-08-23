---
title: モジュール (C++) |Microsoft Docs
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
ms.openlocfilehash: 6e25f33e882769219200e6b9a6f8a0949a01d661
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593358"
---
# <a name="module-c"></a>module (C++)

.idl ファイルのライブラリ ブロックを定義します。

## <a name="syntax"></a>構文

```cpp
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

### <a name="parameters"></a>パラメーター

*型*(省略可能)  
次のいずれかの値を指定します。

- `dll` 結果の DLL がインプロセス COM サーバーとして機能できるようにする関数およびクラスを追加します。 これが既定値です。

- `exe` 結果を許可する関数およびクラスを追加します。 実行可能ファイルがアウト プロセス COM サーバーとして機能します。

- `service` 結果を許可する関数およびクラスを追加します。 実行可能ファイルが NT サービスとして機能します。

- `unspecified` モジュール属性に関連する ATL コードの挿入を無効にします。 の ATL モジュール クラス、グローバル インスタンス _AtlModule およびエントリ ポイント関数。 プロジェクト内のその他の属性による ATL コードの挿入は無効になりせん。

*name* (省略可能)  
ライブラリ ブロックの名前です。

*バージョン*(省略可能)  
ライブラリ ブロックに割り当てるバージョン番号です。 既定値は 1.0 です。

*uuid*  
ライブラリの一意の ID です。 このパラメーターを省略した場合、ライブラリの ID は自動的に生成されます。 取得する必要があります、 *uuid* 、識別子を使用して行うことができます、ライブラリ ブロックの **_ _uuidof (** *libraryname* **)** します。

*lcid*  
ローカリゼーション パラメーターです。 詳細については、「 [lcid](http://msdn.microsoft.com/library/windows/desktop/aa367067) 」を参照してください。

*コントロール*(省略可能)  
ライブラリ内のすべてのコクラスがコントロールであることを指定します。

*helpstring*  
タイプ ライブラリを指定します。

*helpstringdll* (省略可能)  
ドキュメントの文字列を検索する .dll ファイルの名前を設定します。 詳細については、「 [helpstringdll](http://msdn.microsoft.com/library/windows/desktop/aa366860) 」を参照してください。

*helpfile* (省略可能)  
名前、**ヘルプ**タイプ ライブラリ ファイル。

*helpcontext* (省略可能)  
**ヘルプ ID**このタイプ ライブラリ。

*helpstringcontext* (省略可能)  
詳細については、「 [helpstringcontext](../windows/helpstringcontext.md) 」を参照してください。

*非表示*(省略可能)  
ライブラリ全体が表示されないようにします。 これは、コントロールと共に使用します。 ホストは、拡張プロパティを使用し、コントロールをラップする新しいタイプ ライブラリを作成する必要があります。 詳細については、「 [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) 」の MIDL 属性に関する説明を参照してください。

*制限付き*(省略可能)  
ライブラリのメンバーは、任意に呼び出すことはできません。 詳細については、「 [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) 」の MIDL 属性に関する説明を参照してください。

*カスタム*(省略可能)  
1 つ以上の属性です。これは、 [custom](../windows/custom-cpp.md) 属性と似ています。 最初のパラメーター*カスタム*属性の GUID です。 例えば:

```
[module(custom={guid,1}, custom={guid1,2})]
```

*resource_name*  
DLL、実行可能ファイルまたはサービスの登録に使用される .rgs ファイルの文字列リソース ID です。 モジュールがタイプ サービスである場合、この引数はサービス名を含む文字列の ID の取得にも使用されます。

> [!NOTE]
> .rgs ファイルとサービス名を含む文字列の両方に、同じ数値が必要です。

## <a name="remarks"></a>Remarks

指定しない限り、*制限*パラメーターを[emitidl](../windows/emitidl.md)、**モジュール**C++ 属性を使用するすべてのプログラムが必要です。

ライブラリ ブロックは、ソース コードで、 **module** 属性に加え、 [dispinterface](../windows/dispinterface.md)、 [dual](../windows/dual.md)、 [object](../windows/object-cpp.md)、または [coclass](../windows/coclass.md)を意味する属性も使用されている場合に作成されます。

.idl ファイルでは、1 つのライブラリ ブロックが許可されています。 ソース コードに複数のモジュールのエントリがある場合、実装されている最新のパラメーター値と結合されます。

この属性が ATL を使用するプロジェクト内で使用されている場合、属性の動作は変わります。 上記の動作に加え、属性も挿入のグローバル オブジェクト (と呼ばれる`_AtlModule`) の正しい型およびその他のサポート コード。 属性がスタンドアロンの場合、正しいモジュールの種類から派生したクラスが挿入されます。 属性がクラスに適用された場合、正しいモジュールの種類の基本クラスが追加されます。 適切な型がの値によって決まりますが、*型*パラメーター。

- `type` = **dll**

   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) は COM サーバーに必要な基本クラスと標準の DLL エントリ ポイントとして使用されます。 これらのエントリ ポイントは、 [DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583)、 [DllRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms682162)、 [DllUnRegisterServer](http://msdn.microsoft.com/library/windows/desktop/ms691457)、 [DllCanUnloadNow](http://msdn.microsoft.com/library/windows/desktop/ms690368)、および [DllGetClassObject](http://msdn.microsoft.com/library/windows/desktop/dd797891)です。

- `type` = **exe**

   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) は、基本クラスおよび標準の実行可能ファイルのエントリ ポイント [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)として使用されます。

- `type` = **service**

   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) は、基本クラスおよび標準の実行可能ファイルのエントリ ポイント [WinMain](http://msdn.microsoft.com/library/windows/desktop/ms633559)として使用されます。

- `type` = **unspecified**

   モジュール属性と関連する ATL コードの挿入を無効にします。

## <a name="example"></a>例

生成された .idl ファイルにライブラリ ブロックを作成する方法を次のコードで示します。

```cpp
// cpp_attr_ref_module1.cpp
// compile with: /LD
[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];
```

次のコードは、 **module**を使用した結果、挿入されたコード内に表示される独自の関数を実装できることを示しています。 挿入されたコードを参照する方法の詳細については、「 [/Fx](../build/reference/fx-merge-injected-code.md) 」を参照してください。 **module** 属性によって挿入された関数の 1 つをオーバーライドするには、実装した関数を含めるクラスを作成し、そのクラスに **module** 属性を含めます。

```cpp
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
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[クラス属性](../windows/class-attributes.md)  
[スタンドアロン属性](../windows/stand-alone-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  
[usesgetlasterror](../windows/usesgetlasterror.md)  
[ライブラリ](http://msdn.microsoft.com/library/windows/desktop/aa367069)  
[helpcontext](../windows/helpcontext.md)  
[helpstring](../windows/helpstring.md)  
[helpfile](../windows/helpfile.md)  
[version](../windows/version-cpp.md)  