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
ms.openlocfilehash: b0692c9befaa6b7e787ada624dcbb56b074c9f9d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160464"
---
# <a name="_variant_tchangetype"></a>_variant_t::ChangeType

**Microsoft 固有の仕様**

`_variant_t` オブジェクトの型を、指定した `VARTYPE`に変更します。

## <a name="syntax"></a>構文

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>パラメーター

*vartype*<br/>
この `_variant_t` オブジェクトの `VARTYPE`。

*.Psrc*<br/>
変換する `_variant_t` オブジェクトへのポインター。 この値が NULL の場合は、変換が行われます。

## <a name="remarks"></a>解説

このメンバー関数は、`_variant_t` オブジェクトを、指定された `VARTYPE`に変換します。 *Psrc*が NULL の場合、変換は適切に行われます。それ以外の場合は、この `_variant_t` オブジェクトが*psrc*からコピーされ、変換されます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_variant_t クラス](../cpp/variant-t-class.md)
