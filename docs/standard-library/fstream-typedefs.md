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
ms.openlocfilehash: d5a4b0e2d671bb787501767d4321bd3ed61deb88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481940"
---
# <a name="ltfstreamgt-typedefs"></a>&lt;fstream&gt; typedefs

||||
|-|-|-|
|[filebuf](#filebuf)|[fstream](#fstream)|[ifstream](#ifstream)|
|[ofstream](#ofstream)|[wfilebuf](#wfilebuf)|[wfstream](#wfstream)|
|[wifstream](#wifstream)|[wofstream](#wofstream)|

## <a name="filebuf"></a>  filebuf

型`basic_filebuf`に特殊化された**char**テンプレート パラメーター。

```cpp
typedef basic_filebuf<char, char_traits<char>> filebuf;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_filebuf](../standard-library/basic-filebuf-class.md)型の要素に対して特殊化されて、 **char**で既定の特性。

## <a name="fstream">fstream</a>

型`basic_fstream`に特殊化された**char**テンプレート パラメーター。

```cpp
typedef basic_fstream<char, char_traits<char>> fstream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_fstream](../standard-library/basic-fstream-class.md)型の要素に対して特殊化されて、 **char**で既定の特性。

## <a name="ifstream"></a>  ifstream

ファイルから 1 バイト文字のデータを順番に読み取るために使用するストリームを定義します。 `ifstream` テンプレート クラスを専門とする typedef`basic_ifstream`の**char**します。

`wifstream`を専門とする typedef`basic_ifstream`を読み取る**wchar_t** 2 ワイド文字。 詳細については、「[wifstream](../standard-library/fstream-typedefs.md#wifstream)」を参照してください。

```cpp
typedef basic_ifstream<char, char_traits<char>> ifstream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_ifstream](../standard-library/basic-ifstream-class.md)既定の特性を持つ型 char の要素に対して特殊化します。 次に例を示します。

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

型`basic_ofstream`に特殊化された**char**テンプレート パラメーター。

```cpp
typedef basic_ofstream<char, char_traits<char>> ofstream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_ofstream](../standard-library/basic-ofstream-class.md)型の要素に対して特殊化されて、 **char**で既定の特性。

## <a name="wfstream"></a>  wfstream

型`basic_fstream`に特殊化された**wchar_t**テンプレート パラメーター。

```cpp
typedef basic_fstream<wchar_t, char_traits<wchar_t>> wfstream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_fstream](../standard-library/basic-fstream-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="wifstream"></a>  wifstream

型`basic_ifstream`に特殊化された**wchar_t**テンプレート パラメーター。

```cpp
typedef basic_ifstream<wchar_t, char_traits<wchar_t>> wifstream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_ifstream](../standard-library/basic-ifstream-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="wofstream"></a>  wofstream

型`basic_ofstream`に特殊化された**wchar_t**テンプレート パラメーター。

```cpp
typedef basic_ofstream<wchar_t, char_traits<wchar_t>> wofstream;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_ofstream](../standard-library/basic-ofstream-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="wfilebuf"></a>  wfilebuf

型`basic_filebuf`に特殊化された**wchar_t**テンプレート パラメーター。

```cpp
typedef basic_filebuf<wchar_t, char_traits<wchar_t>> wfilebuf;
```

### <a name="remarks"></a>Remarks

型はテンプレート クラスのシノニム[basic_filebuf](../standard-library/basic-filebuf-class.md)型の要素に対して特殊化されて、 **wchar_t**で既定の特性。

## <a name="see-also"></a>関連項目

[\<fstream>](../standard-library/fstream.md)<br/>
