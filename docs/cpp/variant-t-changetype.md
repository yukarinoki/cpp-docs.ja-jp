---
title: _variant_t::ChangeType
ms.date: 11/04/2016
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
ms.openlocfilehash: c2283158856a6781ab2e12c51f4e2ad0e4f1d531
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750730"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**マイクロソフト固有**

オブジェクトの型を示`_variant_t``VARTYPE`された .

## <a name="syntax"></a>構文

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>パラメーター

*Vartype*<br/>
この`VARTYPE``_variant_t`オブジェクトの。

*pSrc*<br/>
変換する `_variant_t` オブジェクトへのポインター。 この値が NULL の場合、変換は所定の位置で行われます。

## <a name="remarks"></a>解説

このメンバー関数は、オブジェクト`_variant_t`を指定された`VARTYPE`. *pSrc*が NULL の場合、変換は所定の位置`_variant_t`で行われ、それ以外の場合はこのオブジェクトは*pSrc*からコピーされてから変換されます。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
