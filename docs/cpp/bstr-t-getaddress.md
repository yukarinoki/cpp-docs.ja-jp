---
description: '詳細については、「_bstr_t:: GetAddress」を参照してください。'
title: _bstr_t::GetAddress
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::GetAddress
helpviewer_keywords:
- GetAddress method [C++]
ms.openlocfilehash: 23013a6666b8e268a6437532b69050933ffe6b42
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522834"
---
# `_bstr_t::GetAddress`

**Microsoft 固有の仕様**

既存の文字列を解放し、新しく割り当てられた文字列のアドレスを返します。

## <a name="syntax"></a>構文

```cpp
BSTR* GetAddress( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` へのポインター。

## <a name="remarks"></a>解説

**`GetAddress`**`_bstr_t`を共有するすべてのオブジェクトに影響 `BSTR` します。 複数ので `_bstr_t` 、 `BSTR` コピーコンストラクターおよびを使用してを共有でき **`operator=`** ます。

## <a name="example"></a>例

[`_bstr_t::Assign`](../cpp/bstr-t-assign.md)の使用例については、「」を参照してください **`GetAddress`** 。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)