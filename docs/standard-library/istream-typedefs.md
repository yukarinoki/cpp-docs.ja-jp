---
title: '&lt;istream&gt; typedef'
ms.date: 11/04/2016
f1_keywords:
- istream/std::iostream
- istream/std::istream
- istream/std::wiostream
- istream/std::wistream
ms.assetid: 55bc1f84-53a7-46ca-a36f-ac6ef75d0374
ms.openlocfilehash: f647fba2036f6c69cb02393e30553c66df34b9dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62413295"
---
# <a name="ltistreamgt-typedefs"></a>&lt;istream&gt; typedef

||||
|-|-|-|
|[iostream](#iostream)|[istream](#istream)|[wiostream](#wiostream)|
|[wistream](#wistream)|

## <a name="iostream"></a>  iostream

型`basic_iostream`に特殊化された**char**します。

```cpp
typedef basic_iostream<char, char_traits<char>> iostream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_iostream](../standard-library/basic-iostream-class.md)型の要素に対して特殊化されて、 **char**で既定の特性。

## <a name="istream"></a>  istream

型`basic_istream`に特殊化された**char**します。

```cpp
typedef basic_istream<char, char_traits<char>> istream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_istream](../standard-library/basic-istream-class.md)型の要素に対して特殊化されて、 **char**で既定の特性。

## <a name="wiostream"></a>  wiostream

型`basic_iostream`に特殊化された**wchar_t**します。

```cpp
typedef basic_iostream<wchar_t, char_traits<wchar_t>> wiostream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_iostream](../standard-library/basic-iostream-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="wistream"></a>  wistream

型`basic_istream`に特殊化された**wchar_t**します。

```cpp
typedef basic_istream<wchar_t, char_traits<wchar_t>> wistream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_istream](../standard-library/basic-istream-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="see-also"></a>関連項目

[\<istream>](../standard-library/istream.md)<br/>
