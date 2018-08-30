---
title: バインド可能な |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.bindable
dev_langs:
- C++
helpviewer_keywords:
- bindable attribute
ms.assetid: a2360f92-927b-4af8-98cc-6eca7f4ec954
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2e0ce7cffb397aaa170f13bac9fc1f4c1693d25f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43214853"
---
# <a name="bindable"></a>bindable

プロパティがデータ バインディングをサポートすることを示します。

## <a name="syntax"></a>構文

```cpp
[bindable]
```

## <a name="remarks"></a>Remarks

**バインド可能な**C++ 属性と同じ機能を持つ、[バインド可能な](/windows/desktop/Midl/bindable)MIDL 属性。 定義されたプロパティで使用することができます、 [propget](../windows/propget.md)、 [propput](../windows/propput.md)、または[propputref](../windows/propputref.md)属性、またはことにより手動でバインド可能なメソッドが定義できます。

次の MFC のサンプルでの使用方法を示して**バインド可能な**:

- [コントロールのサンプル: MFC ベースの ActiveX コントロール](https://msdn.microsoft.com/a44adf86-0ba0-4504-bedb-512b6cba2e63)

- [ActiveX コントロールの円のサンプル:](https://msdn.microsoft.com/9ba34d04-280e-49f4-90ae-41a6be44c95b)

- [ヒントとヘルプ TESTHELP サンプル: ActiveX コントロール](https://msdn.microsoft.com/d822861d-c6f0-4d0a-ad11-970eebb1e8cd)

## <a name="example"></a>例

次のコードを使用する方法を示しています。**バインド可能な**プロパティ。

```cpp
// cpp_attr_ref_bindable.cpp
// compile with: /LD
#include <windows.h>
[
   uuid("479B29E3-9A2C-11D0-B696-00A0C903487A"),
   dispinterface,
   helpstring("property demo Interface")  
]
__interface IPropDemo : IDispatch {

   [propget, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([out, retval] long *nSize);
   [propput, id(1), bindable, displaybind, defaultbind, requestedit] HRESULT P1([in] long nSize);
   [id(3), bindable, propget] HRESULT Object([out, retval] IDispatch **ppObj);
   [id(3), bindable, propputref] HRESULT Object([in] IDispatch* pObj);
   [id(-552), helpstring("method AboutBox")] HRESULT AboutBox();
};

[ module(name="PropDemoLib", uuid="479B29E2-9A2C-11D0-B696-00A0C903487A", version="1.0", helpstring="property demo") ];
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[defaultbind](../windows/defaultbind.md)  
[displaybind](../windows/displaybind.md)  
[immediatebind](../windows/immediatebind.md)  
[requestedit](../windows/requestedit.md)  