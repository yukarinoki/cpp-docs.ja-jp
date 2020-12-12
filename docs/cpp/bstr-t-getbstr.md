---
description: '詳細については、「_bstr_t:: GetBSTR」を参照してください。'
title: _bstr_t::GetBSTR
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.assetid: 0c62ff16-4433-4183-a03c-d5a0a9b731ef
ms.openlocfilehash: ced985bb5123d86ff119279fc49a2b4d181ba8b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229302"
---
# <a name="_bstr_tgetbstr"></a>_bstr_t::GetBSTR

**Microsoft 固有の仕様**

`BSTR` でラップされた `_bstr_t` の先頭を指します。

## <a name="syntax"></a>構文

```
BSTR& GetBSTR( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` の先頭。

## <a name="remarks"></a>解説

**Getbstr** `_bstr_t` は、を共有するすべてのオブジェクトに影響 `BSTR` します。 複数 `_bstr_t` ので、 `BSTR` コピーコンストラクターと **演算子 =** を使用してを共有できます。

## <a name="example"></a>例

**Getbstr** の使用例については、「 [_Bstr_t:: Assign](../cpp/bstr-t-assign.md) 」を参照してください。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
