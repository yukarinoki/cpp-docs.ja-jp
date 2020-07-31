---
title: no_injected_text (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 7e5c822c45888f41e8dd849f25658d0139e6fda0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201246"
---
# <a name="no_injected_text"></a>no_injected_text

属性の使用によってコードが挿入されないようにします。

## <a name="syntax"></a>構文

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>パラメーター

*boolean*<br/>
(省略可能) **`true`** コードが挿入されないようにする場合は **`false`** 。コードを挿入できるようにする場合は。 **`true`** は既定値です。

## <a name="remarks"></a>解説

**No_injected_text** C++ 属性の最も一般的な用途は、 [/fx](../../build/reference/fx-merge-injected-code.md)コンパイラオプションによって**no_injected_text**属性が .mrg ファイルに挿入されることです。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)
