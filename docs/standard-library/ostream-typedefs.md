---
title: '&lt;ostream&gt; typedef | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iosfwd/std::ostream
- iosfwd/std::wostream
ms.assetid: 2ec4dc52-a01f-4654-bd65-dd5288777c48
ms.openlocfilehash: 3f5511cfbf73ddf74fa12954e1a108d8accf875e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltostreamgt-typedefs"></a>&lt;ostream&gt; typedef

|||
|-|-|
|[ostream](#ostream)|[wostream](#wostream)|

## <a name="ostream"></a>  ostream

`char` に対して特殊化された basic_ostream と `char` に対して特殊化された `char_traits` に基づいて型を作成します。

```cpp
typedef basic_ostream<char, char_traits<char>> ostream;
```

### <a name="remarks"></a>コメント

この型はテンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) の同意語であり、既定の特性を持つ型 `char` の要素に対して特殊化されています。

## <a name="wostream"></a>  wostream

`wchar_t` に対して特殊化された basic_ostream と `wchar_t` に対して特殊化された `char_traits` に基づいて型を作成します。

```cpp
typedef basic_ostream<wchar_t, char_traits<wchar_t>> wostream;
```

### <a name="remarks"></a>コメント

この型はテンプレート クラス [basic_ostream](../standard-library/basic-ostream-class.md) の同意語であり、既定の特性を持つ型 `wchar_t` の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<ostream>](../standard-library/ostream.md)<br/>
