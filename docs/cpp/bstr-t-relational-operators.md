---
description: 詳細については、「_bstr_t 関係演算子」を参照してください。
title: _bstr_t 関係演算子
ms.date: 05/07/2019
f1_keywords:
- _bstr_t::operator>
- _bstr_t::operator==
- _bstr_t::operator>=
- _bstr_t::operator!=
- _bstr_t::operator<
- _bstr_t::operator<=
- _bstr_t::operator!
helpviewer_keywords:
- _bstr_t [C++]
ms.assetid: e153da72-37c3-4d8a-b8eb-730d65da64dd
ms.openlocfilehash: 3d34c83d9547bb9d52e43174cac2acd259717e76
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308693"
---
# <a name="_bstr_t-relational-operators"></a>_bstr_t 関係演算子

**Microsoft 固有の仕様**

2 つの `_bstr_t` オブジェクトを比較します。

## <a name="syntax"></a>構文

```
bool operator!( ) const throw( );
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

[_bstr_t クラス](../cpp/bstr-t-class.md)
