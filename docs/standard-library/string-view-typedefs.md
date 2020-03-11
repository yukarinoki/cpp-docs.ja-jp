---
title: '&lt;string_view&gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: c3367afe1353ac70abb74a59658a255614ac8470
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/06/2020
ms.locfileid: "78865848"
---
# <a name="ltstring_viewgt-typedefs"></a>&lt;string_view&gt; typedef

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a>string_view

**Char**型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型。

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>コメント

次の宣言は等価です。

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u16string_view"></a>u16string_view

`char16_t`型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型。

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>コメント

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u32string_view"></a>u32string_view

`char32_t`型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型。

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>コメント

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="wstring_view"></a>wstring_view

**Wchar_t**型の要素を持つ[basic_string_view](../standard-library/basic-string-view-class.md)クラステンプレートの特殊化を記述する型。

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>コメント

次の宣言は等価です。

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

> [!NOTE]
> **Wchar_t**のサイズは Windows では2バイトですが、必ずしもすべてのプラットフォームに当てはまります。 すべてのプラットフォームで同じままであることが保証されている幅を持つ string_view ワイド文字型が必要な場合は、 [u16string_view](../standard-library/string-view-typedefs.md#u16string_view)または[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)を使用します。

## <a name="see-also"></a>参照

[\<string_view >](../standard-library/string-view.md)
