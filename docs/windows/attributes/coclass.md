---
title: coclass (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.coclass
helpviewer_keywords:
- coclass attribute
ms.assetid: 42da6a10-3af9-4b43-9a1d-689d00b61eb3
ms.openlocfilehash: 76540e90fef2e840b91bb07f570a7b8c0987eb10
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168332"
---
# <a name="coclass"></a>coclass

Com インターフェイスを実装できる COM オブジェクトを作成します。

## <a name="syntax"></a>構文

```cpp
[coclass]
```

## <a name="remarks"></a>解説

**Coclass** C++属性は、生成された .idl ファイルにコクラスコンストラクトを配置します。

コクラスを定義するときに、 [uuid](uuid-cpp-attributes.md)、 [version](version-cpp.md)、[スレッド](threading-cpp.md)、 [vi_progid](vi-progid.md)、および[progid](progid.md)属性を指定することもできます。 これらのいずれかが指定されていない場合は、生成されます。

2つのヘッダーファイルに**コクラス**属性を持つクラスが含まれていて、guid を指定していない場合、コンパイラは両方のクラスに同じ guid を使用します。これにより、MIDL エラーが発生します。  したがって、**コクラス**を使用する場合は、`uuid` 属性を使用する必要があります。

**ATL プロジェクト**

この属性が ATL プロジェクトのクラスまたは構造体の定義の前にある場合は、次のようになります。

- オブジェクトの自動登録をサポートするために、コードまたはデータを挿入します。

- オブジェクトの COM クラスファクトリをサポートするために、コードまたはデータを挿入します。

- `IUnknown` 実装するコードまたはデータを挿入し、オブジェクトを COM によって作成可能なオブジェクトにします。

具体的には、次の基本クラスがターゲットオブジェクトに追加されます。

- [CComCoClass クラス](../../atl/reference/ccomcoclass-class.md)には、オブジェクトの既定のクラスファクトリと集計モデルが用意されています。

- [CComObjectRootEx クラス](../../atl/reference/ccomobjectrootex-class.md)には、[スレッド](threading-cpp.md)属性によって指定されたスレッドモデルクラスに基づくテンプレートがあります。 `threading` 属性が指定されていない場合、既定のスレッドモデルはアパートメントです。

- [IProvideClassInfo2Impl](../../atl/reference/iprovideclassinfo2impl-class.md)は、 [noncreatable](noncreatable.md)属性が対象のオブジェクトに対して指定されていない場合に追加されます。

最後に、埋め込み IDL を使用して定義されていないデュアルインターフェイスは、対応する[IDispatchImpl](../../atl/reference/idispatchimpl-class.md)クラスに置き換えられます。 デュアルインターフェイスが埋め込み IDL で定義されている場合、基本リスト内の特定のインターフェイスは変更されません。

また、**コクラス**属性は、挿入されたコードまたは `GetObjectCLSID`の場合に、基底クラス `CComCoClass`の静的メソッドとして、次の関数を使用できるようにします。

- `UpdateRegistry` は、ターゲットクラスのクラスファクトリを登録します。

- 登録に関連する `GetObjectCLSID`は、ターゲットクラスの CLSID を取得するためにも使用できます。

- `GetObjectFriendlyName` 既定では、"\<*ターゲットクラス名*> `Object`" という形式の文字列が返されます。 この関数が既に存在する場合は、追加されません。 この関数をターゲットクラスに追加して、自動的に生成されたものよりもわかりやすい名前を返します。

- 登録に関連する `GetProgID`は、 [progid](progid.md)属性で指定された文字列を返します。

- `GetVersionIndependentProgID` には `GetProgID`と同じ機能がありますが、 [vi_progid](vi-progid.md)で指定された文字列が返されます。

COM マップに関連する次の変更は、ターゲットクラスに対して行われます。

- COM マップは、ターゲットクラスが派生したすべてのインターフェイスのエントリと、 [Com インターフェイスのエントリポイント](../../mfc/com-interface-entry-points.md)属性で指定されたすべてのエントリ、または[集計](aggregates.md)属性で必要なすべてのエントリと共に追加されます。

- COM マップに[OBJECT_ENTRY_AUTO](../../atl/reference/object-map-macros.md#object_entry_auto)マクロが挿入されます。

クラスの .idl ファイルで生成されるコクラスの名前は、クラスと同じ名前になります。  たとえば、次のサンプルを参照すると、MIDL によって生成されたヘッダーファイルを介してクライアントで、コクラス `CMyClass`のクラス ID にアクセスするには、`CLSID_CMyClass`を使用します。

## <a name="example"></a>例

次のコードは、 **coclass**属性の使用方法を示しています。

```cpp
// cpp_attr_ref_coclass1.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I {
   HRESULT func();
};

[coclass, progid("MyCoClass.coclass.1"), vi_progid("MyCoClass.coclass"),
appobject, uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")]
class CMyClass : public I {};
```

次の例は、**コクラス**属性によって挿入されたコードに表示される関数の既定の実装をオーバーライドする方法を示しています。 挿入されたコードを参照する方法の詳細については、「 [/Fx](../../build/reference/fx-merge-injected-code.md) 」を参照してください。 クラスに使用する基本クラスまたはインターフェイスは、挿入されたコードに表示されます。 さらに、挿入されたコードにクラスが既定で含まれていて、そのクラスをコクラスのベースとして明示的に指定した場合、属性プロバイダーは、コードで指定された形式を使用します。

```cpp
// cpp_attr_ref_coclass2.cpp
// compile with: /LD
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

[module(name="MyLib")];

[object, uuid("00000000-0000-0000-0000-000000000000")]
__interface bb {};

[coclass, uuid("00000000-0000-0000-0000-000000000001")]
class CMyClass : public bb {
public:
   // by adding the definition of UpdateRegistry to your code, // the function will not be included in the injected code
   static HRESULT WINAPI UpdateRegistry(BOOL bRegister) {
      // you can add to the default implementation
      CRegistryVirtualMachine rvm;
      HRESULT hr;
      if (FAILED(hr = rvm.AddStandardReplacements()))
         return hr;
      rvm.AddReplacement(_T("FriendlyName"), GetObjectFriendlyName());
      return rvm.VMUpdateRegistry(GetOpCodes(), GetOpcodeStringVals(),       GetOpcodeDWORDVals(), GetOpcodeBinaryVals(), bRegister);
   }
};
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[COM 属性](com-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[appobject](appobject.md)
