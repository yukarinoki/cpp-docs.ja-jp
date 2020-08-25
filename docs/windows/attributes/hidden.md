---
title: hidden (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.hidden
helpviewer_keywords:
- hidden attribute
ms.assetid: 199c96dd-fc07-46c7-af93-92020aebebe7
ms.openlocfilehash: ffa1ce01cfd570de7b699e415f10b27acf525047
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830957"
---
# <a name="hidden"></a>hidden

項目が存在するが、ユーザー指向のブラウザーに表示されないことを示します。

## <a name="syntax"></a>構文

```cpp
[hidden]
```

## <a name="remarks"></a>解説

**Hidden** C++ 属性には、 [hidden](/windows/win32/Midl/hidden) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**非表示**の使用方法の例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**、 **`class`** 、 **`struct`** 、メソッド、プロパティ|
|**Repeatable**|いいえ|
|**必須属性**|**coclass** (またはに適用された場合 **`class`** **`struct`** )|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)
