---
description: '詳細については、「_bstr_t:: operator!」を参照してください。'
title: '_bstr_t:: operator!'
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator!
helpviewer_keywords:
- '! operator'
- operator!, bstr
- operator !, bstr
ms.openlocfilehash: 712aeafd26fda6c8291a54a9b897d31fa77ac02e
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522600"
---
# `_bstr_t::operator !`

**Microsoft 固有の仕様**

カプセル化されたが NULL 文字列であるかどうかを確認 `BSTR` します。

## <a name="syntax"></a>構文

```cpp
bool operator!( ) const throw( );
```

## <a name="return-value"></a>戻り値

**`true`** カプセル化されたが NULL 文字列の場合はを返します。それ以外の場合はを返し `BSTR` **`false`** ます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
