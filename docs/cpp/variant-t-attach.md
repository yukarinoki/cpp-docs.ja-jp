---
title: _variant_t::Attach
ms.date: 11/04/2016
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
ms.openlocfilehash: 3792ed4d0fcd86c4a4e846771c450413fda130b5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187766"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft 固有の仕様**

`VARIANT` オブジェクトを **_variant_t**オブジェクトにアタッチします。

## <a name="syntax"></a>構文

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>パラメーター

*varSrc*<br/>
この **_variant_t**オブジェクトにアタッチされる `VARIANT` オブジェクト。

## <a name="remarks"></a>解説

カプセル化することによって、`VARIANT` の所有権を取得します。 このメンバー関数は、既存のカプセル化された `VARIANT`を解放し、指定された `VARIANT`をコピーし、その `VARTYPE` を VT_EMPTY に設定して、そのリソースが **_variant_t**デストラクターによってのみ解放されるようにします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
