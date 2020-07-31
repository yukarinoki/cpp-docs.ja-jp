---
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 3c5dbefba8e2106c6e3e678002bce26fffd26a62
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215622"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a><a name="streambuf"></a>streambuf

`basic_streambuf` **`char`** テンプレートパラメーターとしてを使用するの特殊化。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムであり、既定の文字の **`char`** 特性を持つ型の要素に対して特殊化されています。

## <a name="wstreambuf"></a><a name="wstreambuf"></a>wstreambuf

`basic_streambuf` **`wchar_t`** テンプレートパラメーターとしてを使用するの特殊化。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムであり、既定の文字の **`wchar_t`** 特性を持つ型の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<streambuf>](../standard-library/streambuf.md)
