---
title: '&lt;ostream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 18f30a12a6f4d2b97cb5dca3ace98e6241d856a7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447166"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

Char に特`char_traits` **化し、** **char**で特殊化された basic_ostream から型を作成します。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_ostream](../standard-library/basic-ostream-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="wostream"></a>  wostream

Wchar_t に特`char_traits` **化した**basic_ostream から、 **wchar_t**で特殊化された型を作成します。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_ostream](../standard-library/basic-ostream-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)
