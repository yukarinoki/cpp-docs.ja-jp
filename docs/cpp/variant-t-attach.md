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
ms.openlocfilehash: d0822dfc730cbbb64f8364e6fa8fe8bc7207f9f9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750745"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**マイクロソフト固有**

_variant_t オブジェクト`VARIANT`にオブジェクトを **_variant_t**アタッチします。

## <a name="syntax"></a>構文

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>パラメーター

*varSrc*<br/>
この`VARIANT`**_variant_t**オブジェクトにアタッチされるオブジェクト。

## <a name="remarks"></a>解説

の所有権を`VARIANT`カプセル化して取得します。 このメンバー関数は、既存のカプセル`VARIANT`化 を解放してから`VARIANT`、指定された`VARTYPE`をコピーし、_variant_t**デストラクター**によってのみリソースを解放できるように、VT_EMPTY に設定します。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
