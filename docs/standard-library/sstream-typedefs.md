---
title: '&lt;sstream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- iosfwd/std::istringstream
- iosfwd/std::ostringstream
- iosfwd/std::stringbuf
- iosfwd/std::stringstream
- iosfwd/std::wistringstream
- iosfwd/std::wostringstream
- iosfwd/std::wstringbuf
- iosfwd/std::wstringstream
ms.assetid: d102edd2-ecea-4a35-a398-cf96e58dd422
ms.openlocfilehash: c25d3fa66b5105ad2e1ff5a08ebdde90d1d156be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336640"
---
# <a name="ltsstreamgt-typedefs"></a>&lt;sstream&gt; typedefs

||||
|-|-|-|
|[イストリングストリーム](#istringstream)|[オストリングストリーム](#ostringstream)|[ストリングブフ](#stringbuf)|
|[ストリングストリーム](#stringstream)|[ウィストリングストリーム](#wistringstream)|[ウォストリングストリーム](#wostringstream)|
|[文字列ブフ](#wstringbuf)|[文字列ストリーム](#wstringstream)|

## <a name="istringstream"></a><a name="istringstream"></a>イストリングストリーム

char テンプレート`basic_istringstream`パラメーターに特化**char**した型を作成します。

```cpp
typedef basic_istringstream<char> istringstream;
```

### <a name="remarks"></a>解説

型は、 **char**型の要素に特化したクラス テンプレート[basic_istringstream](../standard-library/basic-istringstream-class.md)のシノニムです。

## <a name="ostringstream"></a><a name="ostringstream"></a>オストリングストリーム

char テンプレート`basic_ostringstream`パラメーターに特化**char**した型を作成します。

```cpp
typedef basic_ostringstream<char> ostringstream;
```

### <a name="remarks"></a>解説

型は、 **char**型の要素に特化したクラス テンプレート[basic_ostringstream](../standard-library/basic-ostringstream-class.md)のシノニムです。

## <a name="stringbuf"></a><a name="stringbuf"></a>ストリングブフ

char テンプレート`basic_stringbuf`パラメーターに特化**char**した型を作成します。

```cpp
typedef basic_stringbuf<char> stringbuf;
```

### <a name="remarks"></a>解説

型は、 **char**型の要素に特化したクラス テンプレート[basic_stringbuf](../standard-library/basic-stringbuf-class.md)のシノニムです。

## <a name="stringstream"></a><a name="stringstream"></a>ストリングストリーム

char テンプレート`basic_stringstream`パラメーターに特化**char**した型を作成します。

```cpp
typedef basic_stringstream<char> stringstream;
```

### <a name="remarks"></a>解説

型は、 **char**型の要素に特化したクラス テンプレート[basic_stringstream](../standard-library/basic-stringstream-class.md)のシノニムです。

## <a name="wistringstream"></a><a name="wistringstream"></a>ウィストリングストリーム

wchar_t テンプレート`basic_istringstream`パラメーターに特化**wchar_t**した型を作成します。

```cpp
typedef basic_istringstream<wchar_t> wistringstream;
```

### <a name="remarks"></a>解説

型はクラス テンプレート[basic_istringstream](../standard-library/basic-istringstream-class.md)のシノニム**wchar_tです**。

## <a name="wostringstream"></a><a name="wostringstream"></a>ウォストリングストリーム

wchar_t テンプレート`basic_ostringstream`パラメーターに特化**wchar_t**した型を作成します。

```cpp
typedef basic_ostringstream<wchar_t> wostringstream;
```

### <a name="remarks"></a>解説

型はクラス テンプレート[basic_ostringstream](../standard-library/basic-ostringstream-class.md)のシノニム**wchar_tです**。

## <a name="wstringbuf"></a><a name="wstringbuf"></a>文字列ブフ

wchar_t テンプレート`basic_stringbuf`パラメーターに特化**wchar_t**した型を作成します。

```cpp
typedef basic_stringbuf<wchar_t> wstringbuf;
```

### <a name="remarks"></a>解説

型は、 wchar_t型の要素に特化したクラス テンプレート[basic_stringbuf](../standard-library/basic-stringbuf-class.md)のシノニ**ムです。**

## <a name="wstringstream"></a><a name="wstringstream"></a>文字列ストリーム

wchar_t テンプレート`basic_stringstream`パラメーターに特化**wchar_t**した型を作成します。

```cpp
typedef basic_stringstream<wchar_t> wstringstream;
```

### <a name="remarks"></a>解説

型は、 wchar_t 型の要素に特化したクラス テンプレート[basic_stringstream](../standard-library/basic-stringstream-class.md)のシノニム**です**。

## <a name="see-also"></a>関連項目

[\<スストリーム>](../standard-library/sstream.md)
