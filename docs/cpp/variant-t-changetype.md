---
title: _variant_t::ChangeType |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a2883cba0d04bbed38ec44e8d00fdab0d4d5695
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021045"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType

**Microsoft 固有の仕様**

型を変更、`_variant_t`オブジェクトを指定された`VARTYPE`します。

## <a name="syntax"></a>構文

```
void ChangeType(
   VARTYPE vartype,
   const _variant_t* pSrc = NULL
);
```

#### <a name="parameters"></a>パラメーター

*vartype*<br/>
`VARTYPE`この`_variant_t`オブジェクト。

*pSrc*<br/>
変換する `_variant_t` オブジェクトへのポインター。 この値が NULL の場合は、変換が適切に実行されます。

## <a name="remarks"></a>Remarks

このメンバー関数に変換する`_variant_t`オブジェクトを指定された`VARTYPE`します。 場合*pSrc*が NULL の場合、変換が行われる場所、それ以外の場合にこの`_variant_t`からオブジェクトをコピー *pSrc*変換と。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)