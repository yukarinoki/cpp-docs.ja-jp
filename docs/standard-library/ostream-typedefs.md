---
title: '&lt;ostream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 82539a3fdadf10d340ca957756e235e8ae00b267
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373579"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

|||
|-|-|
|[オストリーム](#ostream)|[ウォストリーム](#wostream)|

## <a name="ostream"></a><a name="ostream"></a>オストリーム

char に特化し **、char**に`char_traits`特化したbasic_ostreamから**型を作成**します。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_ostream](../standard-library/basic-ostream-class.md)のシノニムです。

## <a name="wostream"></a><a name="wostream"></a>ウォストリーム

**wchar_t**に特化し`char_traits`**、wchar_t**に特化したbasic_ostreamから型を作成します。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_ostream](../standard-library/basic-ostream-class.md)のシノニムです。

## <a name="see-also"></a>関連項目

[\<oストリーム>](../standard-library/ostream.md)
