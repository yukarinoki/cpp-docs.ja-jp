---
title: '&lt;ostream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: ff9f19f56c8d8fdb9e469e6361a5419468fe7e67
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88846408"
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
