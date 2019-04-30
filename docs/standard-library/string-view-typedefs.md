---
title: '&lt;string_view&gt; typedef'
ms.date: 04/19/2019
f1_keywords:
- xstring/std::string_view
- xstring/std::u16string_view
- xstring/std::u32string_view
- xstring/std::wstring_view
ms.openlocfilehash: 16d7ba49facf24dcffb7df444e445d83d92255e0
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346970"
---
# <a name="ltstringviewgt-typedefs"></a>&lt;string_view&gt; typedef

||||
|-|-|-|
|[string_view](#string_view)|[u16string_view](#u16string_view)|[u32string_view](#u32string_view)|
|[wstring_view](#wstring_view)|

## <a name="string_view"></a> string_view

クラス テンプレートの特殊化を表す型[basic_string_view](../standard-library/basic-string-view-class.md)型の要素を含む**char**します。

```cpp
typedef basic_string_view<char, char_traits<char>> string_view;
```

### <a name="remarks"></a>Remarks

次の宣言は等価です。

```cpp
string_view str("Hello");

basic_string_view<char> str("Hello");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u16string_view"></a> u16string_view

クラス テンプレートの特殊化を表す型[basic_string_view](../standard-library/basic-string-view-class.md)型の要素を含む`char16_t`します。

```cpp
typedef basic_string_view<char16_t, char_traits<char16_t>> u16string_view;
```

### <a name="remarks"></a>Remarks

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="u32string_view"></a> u32string_view

クラス テンプレートの特殊化を表す型[basic_string_view](../standard-library/basic-string-view-class.md)型の要素を含む`char32_t`します。

```cpp
typedef basic_string_view<char32_t, char_traits<char32_t>> u32string_view;
```

### <a name="remarks"></a>Remarks

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

## <a name="wstring_view"></a>  wstring_view

クラス テンプレートの特殊化を表す型[basic_string_view](../standard-library/basic-string-view-class.md)型の要素を含む**wchar_t**します。

```cpp
typedef basic_string_view<wchar_t, char_traits<wchar_t>> wstring_view;
```

### <a name="remarks"></a>Remarks

次の宣言は等価です。

```cpp
wstring_view wstr(L"Hello");

basic_string_view<wchar_t> wstr(L"Hello");
```

文字列コンストラクターの一覧については、「[basic_string::basic_string](../standard-library/basic-string-class.md#basic_string)」をご覧ください。

> [!NOTE]
> サイズ**wchar_t** Windows 上の 2 つのバイトが、必ずしもにはこれがすべてのプラットフォームの場合になることはありません。 String_view のワイド文字型が必要な場合、すべてのプラットフォームで同一に維持することが保証される幅を使用して[u16string_view](../standard-library/string-view-typedefs.md#u16string_view)または[u32string_view](../standard-library/string-view-typedefs.md#u32string_view)します。

## <a name="see-also"></a>関連項目

[\<string_view>](../standard-library/string-view.md)<br/>
