---
description: 詳細については、「defaultbind」を参照してください。
title: defaultbind (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultbind
helpviewer_keywords:
- defaultbind attribute
ms.assetid: b20a8437-24e6-4b6d-a2df-09fe5e1006e0
ms.openlocfilehash: 4fbb6c9e9d563687ec4dd2746f7ab87702fe65d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333040"
---
# <a name="defaultbind"></a>defaultbind

オブジェクトを最もよく表す、1つのバインド可能なプロパティを示します。

## <a name="syntax"></a>構文

```cpp
[defaultbind]
```

## <a name="remarks"></a>解説

**Defaultbind** C++ 属性には、 [defaultbind](/windows/win32/Midl/defaultbind) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Defaultbind** の使用例については、[バインド](bindable.md)可能なの例を参照してください。

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
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)
