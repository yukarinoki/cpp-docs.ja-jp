---
title: '&lt;sstream&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- sstream/std::swap
ms.assetid: bc9607e8-7c6b-44ef-949b-19e917b450ad
ms.openlocfilehash: 43fcffe12afe50a94f06a18e7ee06729bc85854e
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2020
ms.locfileid: "90039899"
---
# <a name="ltsstreamgt-functions"></a>&lt;sstream&gt; 関数

[スワップ](#sstream_swap)

## <a name="swap"></a><a name="sstream_swap"></a> フォト

2 つの `sstream` オブジェクト間で値を交換します。

```cpp
template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringbuf<Elem, Tr, Alloc>& left,
    basic_stringbuf<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_istringstream<Elem, Tr, Alloc>& left,
    basic_istringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_ostringstream<Elem, Tr, Alloc>& left,
    basic_ostringstream<Elem, Tr, Alloc>& right);

template <class Elem, class Tr, class Alloc>
void swap(
    basic_stringstream<Elem, Tr, Alloc>& left,
    basic_stringstream<Elem, Tr, Alloc>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
`sstream` オブジェクトへの参照。

*そうです*\
`sstream` オブジェクトへの参照。

### <a name="remarks"></a>注釈

このテンプレート関数は、`left.swap(right)` を実行します。

## <a name="see-also"></a>関連項目

[\<sstream>](../standard-library/sstream.md)
