---
description: '詳細については、「_bstr_t:: operator =」を参照してください。'
title: _bstr_t::operator =
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator=
helpviewer_keywords:
- operator = [C++], bstr
- operator= [C++], bstr
ms.openlocfilehash: d021ba013190ddee262b8644e16876401be846dc
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522717"
---
# `_bstr_t::operator =`

**Microsoft 固有の仕様**

既存の `_bstr_t` オブジェクトに新しい値を代入します。

## <a name="syntax"></a>構文

```cpp
_bstr_t& operator=(const _bstr_t& s1) throw ( );
_bstr_t& operator=(const char* s2);
_bstr_t& operator=(const wchar_t* s3);
_bstr_t& operator=(const _variant_t& var);
```

### <a name="parameters"></a>パラメーター

*`s1`*\
既存の `_bstr_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。

*`s2`*\
既存の `_bstr_t` オブジェクトに割り当てられるマルチバイト文字列。

*`s3`*\
既存の `_bstr_t` オブジェクトに割り当てられる Unicode 文字列。

*`var`*\
既存の `_variant_t` オブジェクトに割り当てられる `_bstr_t` オブジェクト。

**Microsoft 固有の仕様はここまで**

## <a name="example"></a>例

[`_bstr_t::Assign`](../cpp/bstr-t-assign.md)の使用例については、「」を参照してください **`operator=`** 。

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
