---
title: defaultbind (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.defaultbind
helpviewer_keywords:
- defaultbind attribute
ms.assetid: b20a8437-24e6-4b6d-a2df-09fe5e1006e0
ms.openlocfilehash: 72d1f5a5720466bf7abf08aaad4acdbab05c408f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167161"
---
# <a name="defaultbind"></a>defaultbind

オブジェクトを最もよく表す、1つのバインド可能なプロパティを示します。

## <a name="syntax"></a>構文

```cpp
[defaultbind]
```

## <a name="remarks"></a>解説

**Defaultbind** C++属性には、 [defaultbind](/windows/win32/Midl/defaultbind) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Defaultbind**の使用例については、[バインド](bindable.md)可能なの例を参照してください。

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
[displaybind](displaybind.md)<br/>
[immediatebind](immediatebind.md)<br/>
[requestedit](requestedit.md)
