---
title: _variant_t::SetString |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 52ea719a2c9296ca1e64d881ac150994c041e206
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018731"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Microsoft 固有の仕様**

この `_variant_t` オブジェクトに文字列を代入します。

## <a name="syntax"></a>構文

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>パラメーター

*pSrc*<br/>
文字列へのポインター。

## <a name="remarks"></a>Remarks

ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)