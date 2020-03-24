---
title: displaybind (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.displaybind
helpviewer_keywords:
- displaybind attribute
ms.assetid: b3d70396-78e4-43d9-9583-16ddb8c9bb1f
ms.openlocfilehash: 9ca5c84e859d395d71b7f37a34b1158800bceed7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168253"
---
# <a name="displaybind"></a>displaybind

バインド可能としてユーザーに表示される必要があるプロパティを示します。

## <a name="syntax"></a>構文

```cpp
[displaybind]
```

## <a name="remarks"></a>解説

**Displaybind** C++属性には[displaybind](/windows/win32/Midl/displaybind) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Displaybind**の使用例については、[バインド](bindable.md)可能なの例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[データ メンバー属性](data-member-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)
