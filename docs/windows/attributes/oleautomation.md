---
title: oleautomation (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.oleautomation
helpviewer_keywords:
- oleautomation attribute
ms.assetid: c1086c91-260b-4dc3-b244-662852d09906
ms.openlocfilehash: 201916eeb235d48473d21188da42d19cafb93bce
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214682"
---
# <a name="oleautomation"></a>oleautomation

インターフェイスがオートメーションと互換性があることを示します。

## <a name="syntax"></a>構文

```cpp
[oleautomation]
```

## <a name="remarks"></a>解説

**Oleautomation** C++属性には、 [oleautomation](/windows/win32/Midl/oleautomation) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Oleautomation**の使用例については、 [defaultvalue](defaultvalue.md)の例と[非拡張](nonextensible.md)の例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|**dispinterface**|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)
