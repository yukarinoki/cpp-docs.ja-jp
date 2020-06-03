---
title: _bstr_t::operator +=、+
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: b9eddca85d66f4978e1b33299ca655cd880cf45e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181149"
---
# <a name="_bstr_toperator--"></a>_bstr_t::operator +=、+

**Microsoft 固有の仕様**

`_bstr_t` オブジェクトの末尾に文字を追加するか、2 つの文字列を連結します。

## <a name="syntax"></a>構文

```
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

#### <a name="parameters"></a>パラメーター

*s1*<br/>
`_bstr_t` オブジェクト。

*s2*<br/>
マルチバイト文字列。

*s3*<br/>
Unicode 文字列。

## <a name="remarks"></a>解説

これらの演算子は文字列連結を実行します。

- **operator + = (** *s1* **)** *S1*のカプセル化された `BSTR` の文字を、このオブジェクトのカプセル化された `BSTR`の末尾に追加します。

- **演算子 + (** *s1* **)** このオブジェクトの `BSTR` と*s1*の値を連結して形成された新しい `_bstr_t` を返します。

- **演算子 + (** *s2* **&#124;** *s1* **)** Unicode に変換されたマルチバイト文字列*s2*と*s1*にカプセル化された `BSTR` を連結して形成される新しい `_bstr_t` を返します。

- **operator + (** *s3* **、** *s1* **)** *S1*にカプセル化された `BSTR` と Unicode 文字列*s3*を連結して形成される新しい `_bstr_t` を返します。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>参照

[_bstr_t クラス](../cpp/bstr-t-class.md)
