---
title: _variant_t::Attach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e680f4f42881ea89510048f43d657d1579686527
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109263"
---
# <a name="varianttattach"></a>_variant_t::Attach

**Microsoft 固有の仕様**

アタッチを`VARIANT`オブジェクトを **_variant_t**オブジェクト。

## <a name="syntax"></a>構文

```
void Attach(VARIANT& varSrc);
```

#### <a name="parameters"></a>パラメーター

*varSrc*<br/>
A`VARIANT`オブジェクトにアタッチされる **_variant_t**オブジェクト。

## <a name="remarks"></a>Remarks

所有権を取得、`VARIANT`によってカプセル化しています。 このメンバー関数は、既存のカプセル化を解放`VARIANT`をコピーし、指定された`VARIANT`、設定とその`VARTYPE`VT_EMPTY を確認するにそのリソースのみ解放できますが、 **_variant_t**デストラクターです。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)