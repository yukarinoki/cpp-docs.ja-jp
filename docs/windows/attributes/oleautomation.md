---
title: oleautomation (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 47842454ce52c65cf71a317f39a7649b0f9dd27d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842183"
---
# <a name="oleautomation"></a>oleautomation

インターフェイスがオートメーションと互換性があることを示します。

## <a name="syntax"></a>構文

```cpp
[oleautomation]
```

## <a name="remarks"></a>解説

**Oleautomation** C++ 属性には、 [oleautomation](/windows/win32/Midl/oleautomation) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Oleautomation**の使用例については、 [defaultvalue](defaultvalue.md)の例と[非拡張](nonextensible.md)の例を参照してください。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|**dispinterface**|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)
