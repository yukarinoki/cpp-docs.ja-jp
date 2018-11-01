---
title: '&lt;ostream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 02936fdfc990ea65a99b2875cf7f482eb2ce4ebe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50429745"
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

特殊化 basic_ostream から型を作成**char**と`char_traits`に特殊化された**char**します。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_ostream](../standard-library/basic-ostream-class.md)型の要素に対して特殊化されて、 **char**で既定の特性。

## <a name="wostream"></a>  wostream

特殊化 basic_ostream から型を作成**wchar_t**と`char_traits`に特殊化された**wchar_t**します。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_ostream](../standard-library/basic-ostream-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)<br/>
