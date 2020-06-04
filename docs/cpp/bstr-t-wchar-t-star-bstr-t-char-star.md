---
title: _bstr_t::wchar_t *、_bstr_t::char*
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::wchar_t*
- _bstr_t::char*
helpviewer_keywords:
- operator wchar_t* [C++]
- operator char* [C++]
ms.assetid: acd9f4a7-b427-42c2-aaae-acae21cab317
ms.openlocfilehash: 5fdce29b0be7e9aabae9e3c602822045a7bccafd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190301"
---
# <a name="_bstr_twchar_t-_bstr_tchar"></a>_bstr_t::wchar_t\*、_bstr_t::char\*

**Microsoft 固有の仕様**

BSTR 文字をナロー文字配列またはワイド文字配列として返します。

## <a name="syntax"></a>構文

```
operator const wchar_t*( ) const throw( );
operator wchar_t*( ) const throw( );
operator const char*( ) const;
operator char*( ) const;
```

## <a name="remarks"></a>解説

これらの演算子は `BSTR` オブジェクトによってカプセル化された文字データを抽出するために使用できます。 返されたポインターに新しい値を割り当てると、元の BSTR データは変更されません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_bstr_t クラス](../cpp/bstr-t-class.md)
