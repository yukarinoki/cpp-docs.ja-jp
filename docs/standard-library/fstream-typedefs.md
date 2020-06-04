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
ms.openlocfilehash: 57e481c131a6e4a1111b1ed88217b891d6fc96a8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317191"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs

||||
|-|-|-|
|[filebuf](#filebuf)|[フストリーム](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[ウィフストリーム](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a><a name="filebuf"></a>ファイルブフ

char`basic_filebuf`テンプレートパラメーターに**char**特化した型。

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_filebuf](../standard-library/basic-filebuf-class.md)のシノニムです。

## <a name="fstream"></a><a name="fstream"></a>フストリーム

char`basic_fstream`テンプレートパラメーターに**char**特化した型。

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>解説

型はクラス テンプレート[basic_fstream](../standard-library/basic-fstream-class.md)のシノニムであり、既定の文字特性を持つ**char**型の要素に特化しています。

## <a name="ifstream"></a><a name="ifstream"></a>ifstream

ファイルから 1 バイト文字のデータを順番に読み取るために使用するストリームを定義します。 `ifstream`は、 `basic_ifstream` **char**のクラス テンプレートを特化した typedef です。

また`wifstream`**、ダブルワイド**文字の読み取`basic_ifstream`りを専門wchar_ttypedefもあります。 詳細については、「[wifstream](../standard-library/fstream-typedefs.md#wifstream)」を参照してください。

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>解説

型はクラス テンプレート[basic_ifstream](../standard-library/basic-ifstream-class.md)のシノニムで、既定の文字特性を持つ char 型の要素に特化しています。 次に例を示します。

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a><a name="ofstream"></a>の流れ

char`basic_ofstream`テンプレートパラメーターに**char**特化した型。

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ**char**型の要素に特化したクラス テンプレート[basic_ofstream](../standard-library/basic-ofstream-class.md)のシノニムです。

## <a name="wfstream"></a><a name="wfstream"></a>wfstream

テンプレート`basic_fstream`パラメーターに特化した型**wchar_t。**

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_fstream](../standard-library/basic-fstream-class.md)のシノニムです。

## <a name="wifstream"></a><a name="wifstream"></a>ウィフストリーム

テンプレート`basic_ifstream`パラメーターに特化した型**wchar_t。**

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_ifstream](../standard-library/basic-ifstream-class.md)のシノニムです。

## <a name="wofstream"></a><a name="wofstream"></a>ウォフストリーム

テンプレート`basic_ofstream`パラメーターに特化した型**wchar_t。**

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>解説

型は、クラス テンプレート[basic_ofstream](../standard-library/basic-ofstream-class.md)のシノニムであり、既定の文字特性を持つ型**wchar_t**要素に特化しています。

## <a name="wfilebuf"></a><a name="wfilebuf"></a>wfilebuf

テンプレート`basic_filebuf`パラメーターに特化した型**wchar_t。**

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>解説

型は、既定の文字特性を持つ型**wchar_t**要素に特化したクラス テンプレート[basic_filebuf](../standard-library/basic-filebuf-class.md)のシノニムです。

## <a name="see-also"></a>関連項目

[\<フストリーム>](../standard-library/fstream.md)
