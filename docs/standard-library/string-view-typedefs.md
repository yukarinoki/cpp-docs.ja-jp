---
title: '&lt;string_view&gt;タイプ定義'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 0ec278484b7c1c9887771f6cbe7e5d0b05205dd7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376672"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt;タイプ定義

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a><a name="string_view"></a>string_view

クラス テンプレートの特殊化を記述する型[basic_string_view](../standard-library/basic-string-view-class.md) **char**型の要素を持つ。

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>解説

次の宣言は等価です。

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u16string_view"></a><a name="u16string_view"></a>u16string_view

クラス テンプレートの特殊化を記述する型[basic_string_view](../standard-library/basic-string-view-class.md)型の要素を使用します`char16_t`。

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>解説

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u32string_view"></a><a name="u32string_view"></a>u32string_view

クラス テンプレートの特殊化を記述する型[basic_string_view](../standard-library/basic-string-view-class.md)型の要素を使用します`char32_t`。

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>解説

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="wstring_view"></a><a name="wstring_view"></a>wstring_view

クラス テンプレートの特殊化を記述する型[basic_string_view](../standard-library/basic-string-view-class.md)型**wchar_t**の要素を持つ。

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>解説

次の宣言は等価です。

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

> [!NOTE]
> **wchar_t**のサイズは Windows では 2 バイトですが、すべてのプラットフォームに必ずしも当てはまるわけではありません。 すべてのプラットフォームで同じ長さを保つ幅を持つstring_viewワイド文字タイプが必要な場合は、 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)または[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)を使用します。

## <a name="see-also"></a>関連項目

[\<>string_view](../standard-library/string-view.md)
