---
description: '詳細については、「_variant_t:: Attach」を参照してください。'
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
ms.openlocfilehash: de13b1e8138eb24971e52165ee84fc92d97ca3d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116653"
---
# <a name="_variant_tattach"></a>_variant_t::Attach

**Microsoft 固有の仕様**

オブジェクトを `VARIANT` **_variant_t** オブジェクトにアタッチします。

## <a name="syntax"></a>構文

```cpp
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>パラメーター

*varSrc*<br/>
`VARIANT`この **_variant_t** オブジェクトにアタッチされるオブジェクト。

## <a name="remarks"></a>解説

をカプセル化することで、の所有権を取得 `VARIANT` します。 このメンバー関数は、カプセル化された既存のをすべて解放し、 `VARIANT` 指定されたをコピーし、 `VARIANT` を VT_EMPTY に設定して、その `VARTYPE` リソースが **_variant_t** デストラクターによってのみ解放されるようにします。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
