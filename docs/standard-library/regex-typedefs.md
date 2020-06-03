---
title: '&lt;regex&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- regex/std::cmatch
- regex/std::cregex_iterator
- regex/std::cregex_token_iterator
- regex/std::csub_match
- regex/std::regex
- regex/std::smatch
- regex/std::sregex_iterator
- regex/std::sregex_token_iterator
- regex/std::ssub_match
- regex/std::wcmatch
- regex/std::wcregex_iterator
- regex/std::wcregex_token_iterator
- regex/std::wcsub_match
- regex/std::wregex
- regex/std::wsmatch
- regex/std::wsregex_iterator
- regex/std::wsregex_token_iterator
- regex/std::wssub_match
ms.assetid: e6a69067-106c-4a24-9e08-7c867a3a2260
ms.openlocfilehash: 5dbda2df4877da7594dd633e9f203a3780b4adb1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368551"
---
# <a name="ltregexgt-typedefs"></a>&lt;regex&gt; typedefs

||||
|-|-|-|
|[cmatch](#cmatch)|[cregex_iterator](#cregex_iterator)|[cregex_token_iterator](#cregex_token_iterator)|
|[csub_match](#csub_match)|[regex](#regex)|[smatch](#smatch)|
|[sregex_iterator](#sregex_iterator)|[sregex_token_iterator](#sregex_token_iterator)|[ssub_match](#ssub_match)|
|[wcmatch](#wcmatch)|[wcregex_iterator](#wcregex_iterator)|[wcregex_token_iterator](#wcregex_token_iterator)|
|[wcsub_match](#wcsub_match)|[wregex](#wregex)|[wsmatch](#wsmatch)|
|[wsregex_iterator](#wsregex_iterator)|[wsregex_token_iterator](#wsregex_token_iterator)|[wssub_match](#wssub_match)|

## <a name="cmatch-typedef"></a><a name="cmatch"></a>クマッチタイプデフ

char match_results の型定義です。

```cpp
typedef match_results<const char*> cmatch;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[match_results Class](../standard-library/match-results-class.md)の特殊化`const char*`を表します。

## <a name="cregex_iterator-typedef"></a><a name="cregex_iterator"></a>cregex_iteratorタイプデフ

char regex_iterator の型定義。

```cpp
typedef regex_iterator<const char*> cregex_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_iterator Class](../standard-library/regex-iterator-class.md)の特殊化`const char*`を表します。

## <a name="cregex_token_iterator-typedef"></a><a name="cregex_token_iterator"></a>cregex_token_iterator・タイプデフ

char regex_token_iterator の型定義

```cpp
typedef regex_token_iterator<const char*> cregex_token_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_token_iterator Class](../standard-library/regex-token-iterator-class.md)の特殊化`const char*`を表します。

## <a name="csub_match-typedef"></a><a name="csub_match"></a>csub_match・タイプデフ

char sub_match の型定義です。

```cpp
typedef sub_match<const char*> csub_match;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[sub_match Class](../standard-library/sub-match-class.md)の特殊化`const char*`を表します。

## <a name="regex-typedef"></a><a name="regex"></a>正規表現タイプデフ

char basic_regex の型定義です。

```cpp
typedef basic_regex<char> regex;
```

### <a name="remarks"></a>解説

この型は、クラス テンプレートの特殊化[basic_regex](../standard-library/basic-regex-class.md) **char**型の要素に対する Class を表します。

> [!NOTE]
> ハイビット文字は、`regex` を使用すると予測できない結果を起こします。 0 から 127 の範囲を外れる値を使用すると未定義の動作をすることがあります。

## <a name="smatch-typedef"></a><a name="smatch"></a>スマッチタイプデフ

string match_results の型定義です。

```cpp
typedef match_results<string::const_iterator> smatch;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[match_results Class](../standard-library/match-results-class.md)の特殊化`string::const_iterator`を表します。

## <a name="sregex_iterator-typedef"></a><a name="sregex_iterator"></a>sregex_iterator・タイプデフ

文字列 regex_iterator  の型定義です。

```cpp
typedef regex_iterator<string::const_iterator> sregex_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_iterator Class](../standard-library/regex-iterator-class.md)の特殊化`string::const_iterator`を表します。

## <a name="sregex_token_iterator-typedef"></a><a name="sregex_token_iterator"></a>sregex_token_iteratorタイプデフ

文字列 regex_token_iterator の型定義です。

```cpp
typedef regex_token_iterator<string::const_iterator> sregex_token_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_token_iterator Class](../standard-library/regex-token-iterator-class.md)の特殊化`string::const_iterator`を表します。

## <a name="ssub_match-typedef"></a><a name="ssub_match"></a>ssub_match・タイプデフ

string sub_match の型定義です。

```cpp
typedef sub_match<string::const_iterator> ssub_match;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[sub_match Class](../standard-library/sub-match-class.md)の特殊化`string::const_iterator`を表します。

## <a name="wcmatch-typedef"></a><a name="wcmatch"></a>wc マッチ・タイプデフ

wchar_t match_results の型定義です。

```cpp
typedef match_results<const wchar_t *> wcmatch;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[match_results Class](../standard-library/match-results-class.md)の特殊化`const wchar_t*`を表します。

## <a name="wcregex_iterator-typedef"></a><a name="wcregex_iterator"></a>wcregex_iterator・タイプデフ

wchar_t regex_iterator の型定義です。

```cpp
typedef regex_iterator<const wchar_t*> wcregex_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_iterator Class](../standard-library/regex-iterator-class.md)の特殊化`const wchar_t*`を表します。

## <a name="wcregex_token_iterator-typedef"></a><a name="wcregex_token_iterator"></a>wcregex_token_iterator・タイプ定義

wchar_t regex_token_iterator の型定義です。

```cpp
typedef regex_token_iterator<const wchar_t*> wcregex_token_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_token_iterator Class](../standard-library/regex-token-iterator-class.md)の特殊化`const wchar_t*`を表します。

## <a name="wcsub_match-typedef"></a><a name="wcsub_match"></a>wcsub_match・タイプ定義

wchar_t sub_match の型定義です。

```cpp
typedef sub_match<const wchar_t*> wcsub_match;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[sub_match Class](../standard-library/sub-match-class.md)の特殊化`const wchar_t*`を表します。

## <a name="wregex-typedef"></a><a name="wregex"></a>ドレペックス・タイプデフ

wchar_t basic_regex の型定義です。

```cpp
typedef basic_regex<wchar_t> wregex;
```

### <a name="remarks"></a>解説

この型は、型の要素に対するクラス テンプレート[basic_regex Class](../standard-library/basic-regex-class.md)の特殊化**wchar_t**記述します。

## <a name="wsmatch-typedef"></a><a name="wsmatch"></a>タイプデフを見る

wstring match_results の型定義です。

```cpp
typedef match_results<wstring::const_iterator> wsmatch;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[match_results Class](../standard-library/match-results-class.md)の特殊化`wstring::const_iterator`を表します。

## <a name="wsregex_iterator-typedef"></a><a name="wsregex_iterator"></a>wsregex_iteratorタイプデフ

wstring regex_iterator の型定義です。

```cpp
typedef regex_iterator<wstring::const_iterator> wsregex_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_iterator Class](../standard-library/regex-iterator-class.md)の特殊化`wstring::const_iterator`を表します。

## <a name="wsregex_token_iterator-typedef"></a><a name="wsregex_token_iterator"></a>wsregex_token_iteratorタイプデフ

wstring regex_token_iterator の型定義です。

```cpp
typedef regex_token_iterator<wstring::const_iterator> wsregex_token_iterator;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[regex_token_iterator Class](../standard-library/regex-token-iterator-class.md)の特殊化`wstring::const_iterator`を表します。

## <a name="wssub_match-typedef"></a><a name="wssub_match"></a>wssub_match・タイプデフ

Wstring sub_match の型定義です。

```cpp
typedef sub_match<wstring::const_iterator> wssub_match;
```

### <a name="remarks"></a>解説

型は、型の反復子のクラス テンプレート[sub_match Class](../standard-library/sub-match-class.md)の特殊化`wstring::const_iterator`を表します。

## <a name="see-also"></a>関連項目

[\<正規表現>](../standard-library/regex.md)\
[regex_constantsクラス](../standard-library/regex-constants-class.md)\
[regex_errorクラス](../standard-library/regex-error-class.md)\
[\<正規表現>関数](../standard-library/regex-functions.md)\
[regex_iteratorクラス](../standard-library/regex-iterator-class.md)\
[\<正規表現>演算子](../standard-library/regex-operators.md)\
[regex_token_iteratorクラス](../standard-library/regex-token-iterator-class.md)\
[regex_traits クラス](../standard-library/regex-traits-class.md)
