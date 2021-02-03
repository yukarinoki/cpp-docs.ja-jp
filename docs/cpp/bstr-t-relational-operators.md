---
description: 詳細については、「_bstr_t 関係演算子」を参照してください。
title: _bstr_t 関係演算子
ms.date: 02/02/2021
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
helpviewer_keywords:
- _bstr_t relational operators[C++]
ms.openlocfilehash: eef66f8165fc1dfbb29730507ee8d3b996800b7b
ms.sourcegitcommit: c20734f18d3d49bb38b1628c68b53b54b3eeeb03
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "99522587"
---
# <a name="_bstr_t-relational-operators"></a>`_bstr_t` 関係演算子

**Microsoft 固有の仕様**

2 つの `_bstr_t` オブジェクトを比較します。

## <a name="syntax"></a>構文

```cpp
bool operator==(const _bstr_t& str) const throw( );
bool operator!=(const _bstr_t& str) const throw( );
bool operator<(const _bstr_t& str) const throw( );
bool operator>(const _bstr_t& str) const throw( );
bool operator<=(const _bstr_t& str) const throw( );
bool operator>=(const _bstr_t& str) const throw( );
```

## <a name="remarks"></a>解説

これらの演算子は 2 つの `_bstr_t` オブジェクトを辞書式に比較します。 演算子は、 **`true`** 比較が保留されている場合はを返し、それ以外の場合はを返し **`false`** ます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[`_bstr_t` 講義](../cpp/bstr-t-class.md)
