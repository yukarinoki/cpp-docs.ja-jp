---
title: '&lt;istream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: 864854fa2697a76c2f3476bcb050d5f5d084dc9d
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458749"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedef

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

Char に`basic_iostream`特化した型。

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_iostream](../standard-library/basic-iostream-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="istream"></a>  istream

Char に`basic_istream`特化した型。

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_istream](../standard-library/basic-istream-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="wiostream"></a>  wiostream

Wchar_t に`basic_iostream`特化した型。

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_iostream](../standard-library/basic-iostream-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="wistream"></a>  wistream

Wchar_t に`basic_istream`特化した型。

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_istream](../standard-library/basic-istream-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)
