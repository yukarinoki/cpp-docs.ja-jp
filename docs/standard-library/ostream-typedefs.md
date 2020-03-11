---
title: '&lt;ostream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: d0ceae12069712c7a124990d0f81968c21bc683a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856610"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

**Char で**特殊化された basic_ostream から型を作成し、 **char**に特化した `char_traits` します。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>コメント

この型は、クラステンプレート[basic_ostream](../standard-library/basic-ostream-class.md)のシノニムであり、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="wostream"></a>  wostream

`char_traits` **wchar_t**に特化し、 **wchar_t**で特殊化された basic_ostream から型を作成します。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>コメント

この型は、クラステンプレート[basic_ostream](../standard-library/basic-ostream-class.md)のシノニムであり、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="see-also"></a>参照

[\<ostream>](../standard-library/ostream.md)
