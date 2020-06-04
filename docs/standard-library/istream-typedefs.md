---
title: '&lt;istream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: e9228bddcc3b99503b6b5f0e93b5ed6eeed773d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363092"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedef

||||
|-|-|-|
|[iostream](#iostream)|[Istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a><a name="iostream"></a>Iostream

char`basic_iostream`に特化した**char**型。

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_iostream](../standard-library/basic-iostream-class.md)のシノニムです。

## <a name="istream"></a><a name="istream"></a>Istream

char`basic_istream`に特化した**char**型。

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_istream](../standard-library/basic-istream-class.md)のシノニムです。

## <a name="wiostream"></a><a name="wiostream"></a>wiostream

wchar_tに`basic_iostream`特化した型**wchar_t**。

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>解説

型は、クラス テンプレート[basic_iostream](../standard-library/basic-iostream-class.md)のシノニムで、既定の文字特性を持つ**型wchar_t**要素に特化しています。

## <a name="wistream"></a><a name="wistream"></a>ウィストリーム

wchar_tに`basic_istream`特化した型**wchar_t**。

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_istream](../standard-library/basic-istream-class.md)のシノニムです。

## <a name="see-also"></a>関連項目

[\<i流>](../standard-library/istream.md)
