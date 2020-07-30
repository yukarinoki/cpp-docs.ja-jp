---
title: switch_is (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_is
helpviewer_keywords:
- switch_is attribute
ms.assetid: f1fffe5d-12d2-4e0f-8803-ccb715177d2d
ms.openlocfilehash: 85ee066a12d4297d9a782ae07ef0fa16798f1616
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228051"
---
# <a name="switch_is"></a>switch_is

共用体メンバーを選択する union 判別として機能する式または識別子を指定します。

## <a name="syntax"></a>構文

```cpp
[switch_is]
```

## <a name="remarks"></a>解説

**Switch_is** C++ 属性には、 [switch_is](/windows/win32/Midl/switch-is) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Switch_is**の使用例については、[大文字と小文字](case-cpp.md)の例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**`typedef`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[switch_type](switch-type.md)
