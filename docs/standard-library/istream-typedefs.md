---
description: 'Istream の詳細情報: &lt; istream &gt; typedef'
title: '&lt;istream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 576d1be7733a01689b4cfc511049dfad89390f63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277857"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedef

[iostream](#iostream)\
[istream](#istream)\
[wiostream](#wiostream)\
[wistream](#wistream)

## <a name="iostream"></a><a name="iostream"></a> iostream

`basic_iostream`に特殊化された型 **`char`** 。

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_iostream](../standard-library/basic-iostream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## <a name="istream"></a><a name="istream"></a> istream

`basic_istream`に特殊化された型 **`char`** 。

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_istream](../standard-library/basic-istream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## <a name="wiostream"></a><a name="wiostream"></a> wiostream

`basic_iostream`に特殊化された型 **`wchar_t`** 。

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_iostream](../standard-library/basic-iostream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="wistream"></a><a name="wistream"></a> wistream

`basic_istream`に特殊化された型 **`wchar_t`** 。

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_istream](../standard-library/basic-istream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)
