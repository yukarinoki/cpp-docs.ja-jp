---
title: '&lt;string&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- string/std::string
- string/std::u16string
- string/std::u32string
- string/std::wstring
ms.assetid: fdca01e9-f2f1-4b59-abda-0093d760b3cc
ms.openlocfilehash: 8e662e4c13012f31014817489b61ee3ed6bc36e0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202299"
---
# <a name="ltstringgt-typedefs"></a>&lt;string&gt; typedefs

||||
|-|-|-|
|[string](#string)|[u16string](#u16string)|[u32string](#u32string)|
|[wstring](#wstring)|

## <a name="string"></a><a name="string"></a> 文字列

型の要素を持つ[basic_string](../standard-library/basic-string-class.md)クラステンプレートの特殊化を記述する型 **`char`** 。

`basic_string` を特殊化する他の typedef には、[wstring](../standard-library/string-typedefs.md#wstring)、[u16string](../standard-library/string-typedefs.md#u16string)、および [u32string](../standard-library/string-typedefs.md#u32string) があります。

```cpp
typedef basic_string<char, char_traits<char>, allocator<char>> string;
```

### <a name="remarks"></a>解説

次の宣言は等価です。

```cpp
string str("");

basic_string<char> str("");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u16string"></a><a name="u16string"></a>u16string

型の要素を持つ[basic_string](../standard-library/basic-string-class.md)クラステンプレートの特殊化を記述する型 **`char16_t`** 。

`basic_string` を特殊化する他の typedef には、[wstring](../standard-library/string-typedefs.md#wstring)、[string](../standard-library/string-typedefs.md#string)、および [u32string](../standard-library/string-typedefs.md#u32string) があります。

```cpp
typedef basic_string<char16_t, char_traits<char16_t>, allocator<char16_t>> u16string;
```

### <a name="remarks"></a>解説

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u32string"></a><a name="u32string"></a>u32string

型の要素を持つ[basic_string](../standard-library/basic-string-class.md)クラステンプレートの特殊化を記述する型 **`char32_t`** 。

`basic_string` を特殊化する他の typedef には、[string](../standard-library/string-typedefs.md#string)、[u16string](../standard-library/string-typedefs.md#u16string)、および [wstring](../standard-library/string-typedefs.md#wstring) があります。

```cpp
typedef basic_string<char32_t, char_traits<char32_t>, allocator<char32_t>> u32string;
```

### <a name="remarks"></a>解説

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="wstring"></a><a name="wstring"></a>wstring

型の要素を持つ[basic_string](../standard-library/basic-string-class.md)クラステンプレートの特殊化を記述する型 **`wchar_t`** 。

`basic_string` を特殊化する他の typedef には、[string](../standard-library/string-typedefs.md#string)、[u16string](../standard-library/string-typedefs.md#u16string)、および [u32string](../standard-library/string-typedefs.md#u32string) があります。

```cpp
typedef basic_string<wchar_t, char_traits<wchar_t>, allocator<wchar_t>> wstring;
```

### <a name="remarks"></a>解説

次の宣言は等価です。

```cpp
wstring wstr(L"");

basic_string<wchar_t> wstr(L"");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

> [!NOTE]
> のサイズ **`wchar_t`** は実装で定義されています。 コードが特定のサイズに依存している場合は **`wchar_t`** 、プラットフォームの実装 (など) を確認し `sizeof(wchar_t)` ます。 幅をすべてのプラットフォームで同一にできる文字列の文字の型が必要な場合は、[string](../standard-library/string-typedefs.md#string)、[u16string](../standard-library/string-typedefs.md#u16string)、または [u32string](../standard-library/string-typedefs.md#u32string) を使用します。

## <a name="see-also"></a>関連項目

[\<string>](../standard-library/string.md)
