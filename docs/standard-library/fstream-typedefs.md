---
title: '&lt;fstream&gt; typedefs'
ms.date: 11/04/2016
f1_keywords:
- fstream/std::filebuf
- fstream/std::fstream
- fstream/std::ifstream
- fstream/std::ofstream
- fstream/std::wfilebuf
- fstream/std::wfstream
- fstream/std::wifstream
- fstream/std::wofstream
ms.assetid: 8dddef2d-7f17-42a6-ba08-6f6f20597d23
ms.openlocfilehash: a0f62f951fb6de4b32a27511ae38e1346cbc22e3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215752"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a><a name="filebuf"></a>filebuf

`basic_filebuf`テンプレートパラメーターに特殊化された型 **`char`** 。

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_filebuf](../standard-library/basic-filebuf-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## <a name="fstream"></a><a name="fstream"></a>fstream

`basic_fstream`テンプレートパラメーターに特殊化された型 **`char`** 。

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_fstream](../standard-library/basic-fstream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## <a name="ifstream"></a><a name="ifstream"></a>ifstream

ファイルから 1 バイト文字のデータを順番に読み取るために使用するストリームを定義します。 `ifstream`は、のクラステンプレートを特殊化する typedef です `basic_ifstream` **`char`** 。

また `wifstream` 、2つの `basic_ifstream` ワイド文字を読み取ることを専門とする typedef もあり **`wchar_t`** ます。 詳細については、「[wifstream](../standard-library/fstream-typedefs.md#wifstream)」を参照してください。

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_ifstream](../standard-library/basic-ifstream-class.md)のシノニムであり、既定の文字の特性を持つ char 型の要素に対して特殊化されています。 次に例を示します。

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a><a name="ofstream"></a>ofstream

`basic_ofstream`テンプレートパラメーターに特殊化された型 **`char`** 。

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_ofstream](../standard-library/basic-ofstream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`char`** ます。

## <a name="wfstream"></a><a name="wfstream"></a>wfstream

`basic_fstream`テンプレートパラメーターに特殊化された型 **`wchar_t`** 。

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_fstream](../standard-library/basic-fstream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="wifstream"></a><a name="wifstream"></a>wifstream

`basic_ifstream`テンプレートパラメーターに特殊化された型 **`wchar_t`** 。

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_ifstream](../standard-library/basic-ifstream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="wofstream"></a><a name="wofstream"></a>wofstream

`basic_ofstream`テンプレートパラメーターに特殊化された型 **`wchar_t`** 。

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_ofstream](../standard-library/basic-ofstream-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="wfilebuf"></a><a name="wfilebuf"></a>wfilebuf

`basic_filebuf`テンプレートパラメーターに特殊化された型 **`wchar_t`** 。

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>解説

この型は、クラステンプレート[basic_filebuf](../standard-library/basic-filebuf-class.md)のシノニムであり、既定の文字の特性を持つ型の要素に対して特殊化されてい **`wchar_t`** ます。

## <a name="see-also"></a>関連項目

[\<fstream>](../standard-library/fstream.md)
