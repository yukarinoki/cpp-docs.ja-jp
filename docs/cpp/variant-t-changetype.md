---
description: '詳細については、「_variant_t:: ChangeType」を参照してください。'
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
ms.openlocfilehash: 32ce43f1d9afb388c97e5271927113c71d31bb92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116627"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft 固有の仕様**

オブジェクトの型 `_variant_t` を、指定されたに変更 `VARTYPE` します。

## <a name="syntax"></a>構文

```cpp
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>パラメーター

*vartype*<br/>
`VARTYPE`このオブジェクトの `_variant_t` 。

*.Psrc*<br/>
変換する `_variant_t` オブジェクトへのポインター。 この値が NULL の場合は、変換が行われます。

## <a name="remarks"></a>解説

このメンバー関数は、 `_variant_t` オブジェクトを指定されたに変換し `VARTYPE` ます。 *Psrc* が NULL の場合、変換は適切に行われます。それ以外の場合は、この `_variant_t` オブジェクトが *psrc* からコピーされ、変換されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)
