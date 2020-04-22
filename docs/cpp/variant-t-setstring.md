---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: 60ad1c1bd95eb35f2a4f2800f79d0326c68a1176
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745852"
---
# <a name="_variant_tsetstring"></a>_variant_t::SetString

**マイクロソフト固有**

この `_variant_t` オブジェクトに文字列を代入します。

## <a name="syntax"></a>構文

```cpp
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>パラメーター

*pSrc*<br/>
文字列へのポインター。

## <a name="remarks"></a>解説

ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
