---
description: '詳細情報: displaybind'
title: displaybind (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.displaybind
helpviewer_keywords:
- displaybind attribute
ms.assetid: b3d70396-78e4-43d9-9583-16ddb8c9bb1f
ms.openlocfilehash: 98411ec7f07c3145216c536db3e1c19ef7043429
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236322"
---
# <a name="displaybind"></a>displaybind

バインド可能としてユーザーに表示される必要があるプロパティを示します。

## <a name="syntax"></a>構文

```cpp
[displaybind]
```

## <a name="remarks"></a>解説

**Displaybind** C++ 属性には [displaybind](/windows/win32/Midl/displaybind) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Displaybind** の使用例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|インターフェイス メソッド|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[データメンバー属性](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)
