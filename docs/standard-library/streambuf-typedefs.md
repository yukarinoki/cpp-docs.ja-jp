---
description: 詳細については、「 &lt; streambuf typedef」を参照してください。 &gt;
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: ae5394213143b05704d452e38eaae0b3581849cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221970"
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
