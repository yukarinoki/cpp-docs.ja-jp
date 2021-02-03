---
description: '詳細については、「_bstr_t:: GetBSTR」を参照してください。'
title: _bstr_t::GetBSTR
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::GetBSTR
helpviewer_keywords:
- GetBSTR method [C++]
ms.openlocfilehash: b48dd082b21c0f3416c8b58b8ae2669c74d9d227
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522756"
---
# `_bstr_t::GetBSTR`

**Microsoft 固有の仕様**

`BSTR` でラップされた `_bstr_t` の先頭を指します。

## <a name="syntax"></a>構文

```cpp
BSTR& GetBSTR( );
```

## <a name="return-value"></a>戻り値

`BSTR` でラップされた `_bstr_t` の先頭。

## <a name="remarks"></a>解説

**`GetBSTR`**`_bstr_t`を共有するすべてのオブジェクトに影響 `BSTR` します。 複数ので `_bstr_t` 、 `BSTR` コピーコンストラクターおよびを使用してを共有でき `operator=` ます。

## <a name="example"></a>例

[`_bstr_t::Assign`](../cpp/bstr-t-assign.md)の使用例については、「」を参照してください **`GetBSTR`** 。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)