---
description: '詳細情報: _bstr_t::D etach'
title: _bstr_t::Detach
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.openlocfilehash: bc269f46d3a393485e95a62df23692c60070d75a
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522847"
---
# `_bstr_t::Detach`

**Microsoft 固有の仕様**

`BSTR` でラップされた `_bstr_t` を返し、`BSTR` から `_bstr_t` をデタッチします。

## <a name="syntax"></a>構文

```cpp
BSTR Detach( ) throw;
```

## <a name="return-value"></a>戻り値

によってカプセル化されたを返し `BSTR` `_bstr_t` ます。

## <a name="example"></a>例

[`_bstr_t::Assign`](../cpp/bstr-t-assign.md)の使用例については、「」を参照してください **`Detach`** 。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
