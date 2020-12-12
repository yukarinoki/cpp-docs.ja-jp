---
description: '詳細については、「_bstr_t:: operator + =, +」を参照してください。'
title: _bstr_t::operator +=、+
ms.date: 11/04/2016
f1_keywords:
- _bstr_t::operator+
- _bstr_t::operator+=
helpviewer_keywords:
- += operator [C++], appending strings
- + operator [C++], _bstr_t objects
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
ms.openlocfilehash: e3ae71a3a43e189251ac0ddaf77572656a031aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308810"
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

- **operator + = (***s1***)** S1 のカプセル化されたの文字を、 `BSTR` カプセル化されたこのオブジェクトの末尾に追加し `BSTR` ます。    

- **演算子 + (***s1***)**`_bstr_t`このオブジェクト `BSTR` と *s1* のを連結して形成された新しいを返します。    

- **operator + (***s2* **&#124;** *s1***)**`_bstr_t`Unicode に変換されたマルチバイト文字列 *s2* を `BSTR` *s1* にカプセル化されたを連結して形成される新しいを返します。        

- **operator + (***s3* **、***s1***)**`_bstr_t`Unicode 文字列 *s3* を `BSTR` *s1* にカプセル化されたと連結することによって形成される新しいを返します。      

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_bstr_t クラス](../cpp/bstr-t-class.md)
