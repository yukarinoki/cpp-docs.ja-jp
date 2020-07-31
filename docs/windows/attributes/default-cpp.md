---
title: 既定 (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.default
helpviewer_keywords:
- default attribute
- attributes [C#], default attribute
- defaults, default attribute
ms.assetid: 0cdca716-1ba8-46d7-9399-167e55492870
ms.openlocfilehash: dc0244897f73a5185451159aa0f4ec66dd9dae56
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215271"
---
# <a name="default-c"></a>default (C++)

コクラス内で定義されるカスタムまたはディスパッチ インターフェイスが既定のプログラミング インターフェイスを表すことを示します。

## <a name="syntax"></a>構文

```cpp
[ default(interface1, interface2) ]
```

### <a name="parameters"></a>パラメーター

*interface1*<br/>
属性で定義されたクラスに基づいてオブジェクトを作成するスクリプト環境で使用可能になる既定のインターフェイス **`default`** 。

既定のインターフェイスが指定されていない場合は、最初に見つかったソース以外のインターフェイスが既定値として使用されます。

*interface2*<br/>
Optional既定のソースインターフェイス。 このインターフェイスを指定する場合は、 [source](source-cpp.md) 属性も使用する必要があります。

既定のソース インターフェイスが指定されていない場合は、最初のソース インターフェイスが既定値として使用されます。

## <a name="remarks"></a>解説

C++ 属性には、 **`default`** [default](/windows/win32/Midl/default) MIDL 属性と同じ機能があります。 属性は、 **`default`** [case](case-cpp.md)属性と共にも使用されます。

## <a name="example"></a>例

次のコードは、を **`default`** 既定のプログラミングインターフェイスとして指定するために、コクラスの定義でを使用する方法を示してい `ICustomDispatch` ます。

```cpp
// cpp_attr_ref_default.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[object, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};

[dual, uuid("9E66A291-4365-11D2-A997-00C04FA37DDB")]
__interface IDual {
   HRESULT Dual([in] long l, [out, retval] long *pLong);
};

[object, uuid("9E66A293-4365-11D2-A997-00C04FA37DDB")]
__interface ICustomDispatch : public IDispatch {
   HRESULT Dispatch([in] long l, [out, retval] long *pLong);
};

[   coclass, default(ICustomDispatch), source(IDual), uuid("9E66A294-4365-11D2-A997-00C04FA37DDB")
]
class CClass : public ICustom, public IDual, public ICustomDispatch {
   HRESULT Custom(long l, long *pLong) { return(S_OK); }
   HRESULT Dual(long l, long *pLong) { return(S_OK); }
   HRESULT Dispatch(long l, long *pLong) { return(S_OK); }
};

int main() {
#if 0 // Can't instantiate without implementations of IUnknown/IDispatch
   CClass *pClass = new CClass;

   long llong;

   pClass->custom(1, &llong);
   pClass->dual(1, &llong);
   pClass->dispinterface(1, &llong);
   pClass->dispatch(1, &llong);

   delete pClass;
#endif
   return(0);
}
```

また、 [source](source-cpp.md)属性には、の使用方法の例も含まれてい **`default`** ます。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`class`**、 **`struct`** 、データメンバー|
|**Repeatable**|いいえ|
|**必須属性**|**coclass** (またはに適用された場合 **`class`** **`struct`** )|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[coclass](coclass.md)
