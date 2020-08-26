---
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: f08c08de0d6449714f953f5a65fadd2e0279ed44
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843197"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

[streambuf](#streambuf)\
[wstreambuf](#wstreambuf)

## <a name="streambuf"></a><a name="streambuf"></a> streambuf

`basic_streambuf` **`char`** テンプレートパラメーターとしてを使用するの特殊化。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムであり、既定の文字の **`char`** 特性を持つ型の要素に対して特殊化されています。

## <a name="wstreambuf"></a><a name="wstreambuf"></a> wstreambuf

`basic_streambuf` **`wchar_t`** テンプレートパラメーターとしてを使用するの特殊化。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート [basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムであり、既定の文字の **`wchar_t`** 特性を持つ型の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<streambuf>](../standard-library/streambuf.md)
