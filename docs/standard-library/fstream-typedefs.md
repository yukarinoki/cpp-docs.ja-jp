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
ms.openlocfilehash: 6144826254c6acc509db2c0285b21811fe37bd4e
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454048"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>  filebuf

Char テンプレート`basic_filebuf`パラメーターに特殊化された型。

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_filebuf](../standard-library/basic-filebuf-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="fstream"></a>  fstream

Char テンプレート`basic_fstream`パラメーターに特殊化された型。

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_fstream](../standard-library/basic-fstream-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="ifstream"></a>  ifstream

ファイルから 1 バイト文字のデータを順番に読み取るために使用するストリームを定義します。 `ifstream`は、 `basic_ifstream` **char**のテンプレートクラスを特殊化する typedef です。

また、 **wchar_t**の二重ワイド文字を`basic_ifstream`読み取ることを専門とする typedef も`wifstream`あります。 詳細については、「[wifstream](../standard-library/fstream-typedefs.md#wifstream)」を参照してください。

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_ifstream](../standard-library/basic-ifstream-class.md)のシノニムで、既定の文字の特性を持つ char 型の要素に対して特殊化されています。 次に例を示します。

```cpp
using namespace std;

ifstream infile("existingtextfile.txt");

if (!infile.bad())
{
    // Dump the contents of the file to cout.
    cout << infile.rdbuf();infile.close();
}
```

## <a name="ofstream"></a>  ofstream

Char テンプレート`basic_ofstream`パラメーターに特殊化された型。

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_ofstream](../standard-library/basic-ofstream-class.md)のシノニムで、既定の文字の特性を持つ**char**型の要素に対して特殊化されています。

## <a name="wfstream"></a>  wfstream

Wchar_t テンプレート`basic_fstream`パラメーターに特化した型。

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_fstream](../standard-library/basic-fstream-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="wifstream"></a>  wifstream

Wchar_t テンプレート`basic_ifstream`パラメーターに特化した型。

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_ifstream](../standard-library/basic-ifstream-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="wofstream"></a>  wofstream

Wchar_t テンプレート`basic_ofstream`パラメーターに特化した型。

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_ofstream](../standard-library/basic-ofstream-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="wfilebuf"></a>  wfilebuf

Wchar_t テンプレート`basic_filebuf`パラメーターに特化した型。

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Remarks

この型はテンプレートクラス[basic_filebuf](../standard-library/basic-filebuf-class.md)のシノニムで、既定の文字の特性を持つ**wchar_t**型の要素に対して特殊化されています。

## <a name="see-also"></a>関連項目

[\<fstream>](../standard-library/fstream.md)
