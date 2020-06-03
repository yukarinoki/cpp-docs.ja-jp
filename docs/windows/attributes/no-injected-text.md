---
title: no_injected_text (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 5f98be3478b2e1eeb4b464f1784f3f4ece22d8a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166615"
---
# <a name="no_injected_text"></a>no_injected_text

属性の使用によってコードが挿入されないようにします。

## <a name="syntax"></a>構文

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>パラメーター

*boolean*<br/>
Optionalコードを挿入しない場合は**true** 、コードを挿入できるようにする場合は**false** 。 既定値は**true**です。

## <a name="remarks"></a>解説

**No_injected_text** C++属性の最も一般的な用途は、 [/fx](../../build/reference/fx-merge-injected-code.md)コンパイラオプションによって**no_injected_text**属性が .mrg ファイルに挿入されることです。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[コンパイラ属性](compiler-attributes.md)
