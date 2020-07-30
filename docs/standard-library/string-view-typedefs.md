---
title: '&lt;string_view &gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 6aadd4ad3ff08a0b020fd8e683e60063fe516c63
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215596"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view &gt; typedef

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a><a name="string_view"></a>string_view

型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型 **`char`** 。

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

型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型 **`char16_t`** 。

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>解説

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u32string_view"></a><a name="u32string_view"></a>u32string_view

型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型 **`char32_t`** 。

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>解説

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="wstring_view"></a><a name="wstring_view"></a>wstring_view

型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型 **`wchar_t`** 。

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
> のサイズは **`wchar_t`** Windows では2バイトですが、すべてのプラットフォームで必ずしも同じであるとは限りません。 すべてのプラットフォームで同じままであることが保証されている幅を持つ string_view ワイド文字型が必要な場合は、 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)または[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)を使用します。

## <a name="see-also"></a>関連項目

[\<string_view>](../standard-library/string-view.md)
