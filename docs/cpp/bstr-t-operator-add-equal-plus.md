---
description: '詳細については、次を参照してください: _bstr_t:: operator + =、_bstr_t:: operator +'
title: '_bstr_t:: operator + =、_bstr_t:: operator +'
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.openlocfilehash: 44a525891ee072ea797026bd022ecae7b62fd6d1
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522522"
---
# <a name="_bstr_toperator--_bstr_toperator-"></a>`_bstr_t::operator +=`, `_bstr_t::operator +`

**Microsoft 固有の仕様**

オブジェクトの末尾に文字を追加する `_bstr_t` か、2つの文字列を連結します。

## <a name="syntax"></a>構文

```cpp
_bstr_t& operator+=( const _bstr_t& s1 );
_bstr_t operator+( const _bstr_t& s1 );
friend _bstr_t operator+( const char* s2, const _bstr_t& s1);
friend _bstr_t operator+( const wchar_t* s3, const _bstr_t& s1);
```

### <a name="parameters"></a>パラメーター

*`s1`*\
`_bstr_t` オブジェクト。

*`s2`*\
マルチバイト文字列。

*`s3`*\
Unicode 文字列。

## <a name="remarks"></a>解説

これらの演算子は文字列連結を実行します。

- `operator+=( s1 )` のカプセル化されたの文字を、 `BSTR` *`s1`* このオブジェクトのカプセル化されたの末尾に追加し `BSTR` ます。

- `operator+( s1 )``_bstr_t`このオブジェクトとのを連結して形成される新しいを返し `BSTR` *`s1`* ます。

- `operator+( s2, s1 )``_bstr_t`マルチバイト文字列 *`s2`* 、Unicode に変換された、およびにカプセル化されたを連結して形成される新しいを返し `BSTR` *`s1`* ます。

- `operator+( s3, s1 )``_bstr_t`Unicode 文字列 *`s3`* とでカプセル化されたを連結して形成される新しいを返し `BSTR` *`s1`* ます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
