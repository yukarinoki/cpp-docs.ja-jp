---
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 1c9850ad7d7ec9b9c3554e6806f4790ef3613b08
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2020
ms.locfileid: "79425065"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

テンプレートパラメーターとして**char**を使用する特殊な `basic_streambuf`。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムであり、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="wstreambuf"></a>  wstreambuf

テンプレートパラメーターとして**wchar_t**を使用する特殊な `basic_streambuf`。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムであり、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="see-also"></a>参照

[\<streambuf>](../standard-library/streambuf.md)
