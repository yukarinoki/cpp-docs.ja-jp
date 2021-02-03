---
description: '詳細については、「_bstr_t:: wchar_t *、_bstr_t:: char」を参照し* てください。'
title: _bstr_t::wchar_t *、_bstr_t::char*
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.openlocfilehash: b2e98ea4b62d4a2e346b552d31d66d23f301817c
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522548"
---
# <a name="_bstr_twchar_t-_bstr_tchar"></a>`_bstr_t::wchar_t*`, `_bstr_t::char*`

**Microsoft 固有の仕様**

文字を `BSTR` ナローまたはワイド文字配列として返します。

## <a name="syntax"></a>構文

```cpp
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>解説

これらの演算子を使用すると、オブジェクトによってカプセル化された文字データを抽出でき `BSTR` ます。 返されたポインターに新しい値を代入しても、元のデータは変更されません `BSTR` 。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
