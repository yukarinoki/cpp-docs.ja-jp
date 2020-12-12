---
description: '詳細情報: &lt; ostream &gt; typedef'
title: '&lt;ostream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 886fb729f389fac161e4d154e00898b530d1d9f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193020"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

[ostream](#ostream)\
[wostream](#wostream)

## <a name="ostream"></a><a name="ostream"></a> ostream

に特殊化された basic_ostream から型を作成し、 **`char`** `char_traits` に特殊化し **`char`** ます。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_ostream](../standard-library/basic-ostream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## <a name="wostream"></a><a name="wostream"></a> wostream

に特殊化された basic_ostream から型を作成し、 **`wchar_t`** `char_traits` に特殊化し **`wchar_t`** ます。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_ostream](../standard-library/basic-ostream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)
