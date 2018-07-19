---
title: '&lt;ostream&gt; typedef | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 094952a76d8e46e4244cf57a8c5a47c929f3ae37
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960355"
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
