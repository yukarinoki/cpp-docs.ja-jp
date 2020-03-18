---
title: ハッシュ&lt;string_view&gt; 特殊化
ms.date: 04/19/2019
f1_keywords:
- xstring/basic_string_view::hash
helpviewer_keywords:
- std::basic_string_view::hash
ms.openlocfilehash: b56e9a1d575cc32f02724d1b54c43db0eb109043
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445828"
---
# <a name="hashltstring_viewgt-specialization"></a>ハッシュ&lt;string_view&gt; 特殊化

指定された string_view のハッシュ値を生成するテンプレートの特殊化。

```cpp
template <class CharType, class Traits>
struct hash<basic_string_view<CharType, Traits>>
{
    typedef basic_string_view<CharType, Traits> argument_type;
    typedef size_t result_type;

    size_t operator()(const basic_string_view<CharType, Traits>) const
        noexcept;
};
```

### <a name="remarks"></a>コメント

String_view のハッシュは、基になる文字列オブジェクトのハッシュに相当します。

### <a name="example"></a>例

```cpp
//compile with: /std:c++17
#include <string>
#include <string_view>
#include <iostream>

using namespace std;

int main()
{
    string_view sv{ "Hello world" };
    string s{ "Hello world" };
    cout << boolalpha << (hash<string_view>{}(sv)
        == hash<string>{}(s)); // true
}
```