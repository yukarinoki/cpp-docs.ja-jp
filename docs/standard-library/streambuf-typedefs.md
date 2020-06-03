---
title: '&lt;streambuf&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::streambuf
- iosfwd/std::wstreambuf
ms.assetid: 2678e18f-f0f0-4995-bc53-f1bc7dfc4ec6
ms.openlocfilehash: 8eb058f161a9f30ccf5e9d49307b50c215f79c22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376691"
---
# <a name="ltstreambufgt-typedefs"></a>&lt;streambuf&gt; typedef

|||
|-|-|
|[streambuf](#streambuf)|[wstreambuf](#wstreambuf)|

## <a name="streambuf"></a><a name="streambuf"></a>ストリームバブフ

テンプレートパラメータ`basic_streambuf`として**char**を使用する特殊化。

```cpp
typedef basic_streambuf<char, char_traits<char>> streambuf;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムです。

## <a name="wstreambuf"></a><a name="wstreambuf"></a>wstreambuf

テンプレート パラメーターとして`basic_streambuf`**wchar_t**を使用する特殊化。

```cpp
typedef basic_streambuf<wchar_t, char_traits<wchar_t>> wstreambuf;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_streambuf](../standard-library/basic-streambuf-class.md)のシノニムです。

## <a name="see-also"></a>関連項目

[\<ストリームブフ>](../standard-library/streambuf.md)
