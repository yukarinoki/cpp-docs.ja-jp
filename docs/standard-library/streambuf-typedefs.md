---
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 178b489d92a4ed7340084490329fdf8fa16c2aa7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449585"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a>  streambuf

テンプレートパラメーターと`basic_streambuf`して**char**を使用するの特殊化。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="wstreambuf"></a>  wstreambuf

テンプレートパラメーターと`basic_streambuf`して**wchar_t**を使用するの特殊化。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<streambuf>](../standard-library/streambuf.md)
