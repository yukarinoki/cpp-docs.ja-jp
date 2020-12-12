---
description: 詳細については、「 &lt; filesystem 演算子」を参照してください。 &gt;
title: '&lt;filesystem&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::operator==
- FILESYSTEM/std::experimental::filesystem::operator!=
- FILESYSTEM/std::experimental::filesystem::operator<
- FILESYSTEM/std::experimental::filesystem::operator<=
- FILESYSTEM/std::experimental::filesystem::operator>
- FILESYSTEM/std::experimental::filesystem::operator>=
- FILESYSTEM/std::experimental::filesystem::operator/
- FILESYSTEM/std::experimental::filesystem::operator<<
- FILESYSTEM/std::experimental::filesystem::operator>>
ms.assetid: 102c4833-aa3b-41a8-8998-f5003c546bfd
ms.openlocfilehash: 140ef553cbfd17fe2b1cfc41bedba397506da817
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232467"
---
# <a name="ltfilesystemgt-operators"></a>&lt;filesystem&gt; 演算子

演算子は、2 つのパスの構文を文字列として比較します。 関数を使用し `equivalent` て、2つのパス (たとえば、相対パスと絶対パス) がディスク上の同じファイルまたはディレクトリを参照しているかどうかを確認します。

詳細については、「[ファイル システムのナビゲーション](../standard-library/file-system-navigation.md)」を参照してください。

## <a name="operator"></a>operator==

```cpp
bool operator==(const path& left, const path& right) noexcept;
```

left.native() == right.native() が返されます。

## <a name="operator"></a>operator!=

```cpp
bool operator!=(const path& left, const path& right) noexcept;
```

!(left == right) が返されます。

## <a name="operator"></a>operator<

```cpp
bool operator<(const path& left, const path& right) noexcept;
```

left.native() < right.native() が返されます。

## <a name="operator"></a>operator<=

```cpp
bool operator<=(const path& left, const path& right) noexcept;
```

!(right \< left) が返されます。

## <a name="operator"></a>operator>

```cpp
bool operator>(const path& left, const path& right) noexcept;
```

right \< left が返されます。

## <a name="operator"></a>operator>=

```cpp
bool operator>=(const path& left, const path& right) noexcept;
```

!(left < right) が返されます。

## <a name="operator"></a>operator/

```cpp
path operator/(const path& left, const path& right);
```

この関数は、次のコードを実行します。

```cpp
basic_string<Elem, Traits> str;
path ans = left;
return (ans /= right);
```

## <a name="operator"></a>operator<<

```cpp
template <class Elem, class Traits>
basic_ostream<Elem, Traits>& operator<<(basic_ostream<Elem, Traits>& os, const path& pval);
```

関数は os << pval \<Elem, Traits> () を返します。

## <a name="operator"></a>operator>>

```cpp
template <class Elem, class Traits>
basic_istream<Elem, Traits>& operator<<(basic_istream<Elem, Traits>& is, const path& pval);
```

この関数は、次のコードを実行します。

```cpp
basic_string<Elem, Traits> str;
is>> str;
pval = str;
return (is);
```
