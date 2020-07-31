---
title: '&lt;charconv &gt; 関数'
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars
- charconv/std::from_chars
helpviewer_keywords:
- std::charconv [C++], to_chars
- std::charconv [C++], from_chars
ms.openlocfilehash: 276ac2bce70ce5c4ebf8e22bb1da1ac9914db55e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230197"
---
# <a name="ltcharconvgt-functions"></a>&lt;charconv &gt; 関数

ヘッダーには、 \<charconv> 次の非メンバー関数が含まれています。

| **非メンバー関数** | **説明** |
|-|-|
|[to_chars](#to_chars) | 整数または浮動小数点値をのシーケンスに変換 **`char`** します。 |
|[from_chars](#from_chars) | のシーケンスを **`char`** 整数または浮動小数点値に変換します。 |

これらの変換関数は、パフォーマンスのためにチューニングされており、最短ラウンドトリップ動作もサポートしています。 最短ラウンドトリップの動作では、数値が文字に変換されるときに、その文字を浮動小数点型に変換するときに元の数値の復旧を可能にするために、十分な精度だけが書き込まれます。

- 文字を数値に変換する場合、数値を null で終了する必要はありません。 同様に、数値を文字に変換しても、結果は null で終了しません。
- 変換関数はメモリを割り当てません。 バッファーは常に所有しています。
- 変換関数は、をスローしません。 変換が成功したかどうかを判断できる結果が返されます。
- 変換関数は、ランタイムの丸めモードを区別しません。
- 変換関数はロケールに対応していません。 コンマを使用するロケールでは、小数点は常に "" のように印刷および解析さ `'.'` れます。

## `to_chars`

整数または浮動小数点値をのシーケンスに変換 **`char`** します。

は、 `value` 範囲を埋めることによって文字列に変換 \[ `first` `last` されます。) では、は \[ `first` `last` 有効な範囲である必要があります。
[To_chars_result 構造体](to-chars-result-structure.md)を返します。 によって示されているように、変換が成功した場合、 `to_char_result.ec` メンバー `ptr` は書き込まれた文字の1つ後ろのポインターになります。 それ以外の場合、には値が、には値が、 `to_char_result.ec` `errc::value_too_large` `to_char_result.ptr` `last` 範囲の内容は \[ `first` `last` 指定されません。

失敗する唯一の方法 `to_chars` は、結果を保持するのに必要のない大きなバッファーを指定する場合です。

```cpp
// integer to chars

to_chars_result to_chars(char* first, char* last, char value, int base = 10);
to_chars_result to_chars(char* first, char* last, signed char value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned char value, int base = 10);
to_chars_result to_chars(char* first, char* last, short value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned short value, int base = 10);
to_chars_result to_chars(char* first, char* last, int value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned int value, int base = 10);
to_chars_result to_chars(char* first, char* last, long value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned long value, int base = 10);
to_chars_result to_chars(char* first, char* last, long long value, int base = 10);
to_chars_result to_chars(char* first, char* last, unsigned long long value, int base = 10);
to_chars_result to_chars(char* first, char* last, bool value, int base = 10) = delete;

// floating-point to chars

to_chars_result to_chars(char* first, char* last, float value);
to_chars_result to_chars(char* first, char* last, double value);
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="parameters"></a>パラメーター

*まずは*\
格納するバッファーの先頭を指します。

*前の*\
バッファーの末尾を越える1つの文字を指定してデータを格納します。

*数値*\
変換する値。 `value`が負の場合、表現はで始まり `-` ます。

*常用*\
整数変換の場合は、文字に変換するときに使用するベース `value` 。 2 ~ 36 の範囲で指定する必要があります。 先頭に0はありません。 10 ~ 35 の範囲の数字は、小文字 a.. で表されます。方向

*fmt*\
浮動小数点変換の場合は、使用する変換形式を指定するビットマスク (科学的、固定、16進数など)。 詳細については、「 [chars_format](chars-format-class.md) 」を参照してください。

*精度*\
浮動小数点変換の場合は、変換後の値の有効桁数を指定します。

### <a name="return-value"></a>戻り値

変換の結果を格納している[to_chars_result](to-chars-result-structure.md) 。

### <a name="remarks"></a>解説

[Chars_format](chars-format-class.md)パラメーターを受け取る関数は、次のように、を使用しているかのように変換指定子を決定します。がの場合、変換指定子は、がの場合は、がである場合は、がである場合は、がの場合 `printf()` は `f` `fmt` `chars_format::fixed` `e` `fmt` `chars_format::scientific` `a` (先頭に "0x" `fmt` `chars_format::hex` `g` `fmt` `chars_format::general` を付けません)、がの場合は 最短の固定表記法を指定しても、値が非常に大きい場合や非常に小さい場合には、最小の表現になる可能性があるため、出力が長くなる可能性があります。

次の表では、およびパラメーターのさまざまな組み合わせについて、変換の動作について説明し `fmt` `precision` ます。 「最も短いラウンドトリップ」という用語は、対応する関数を使用してその表現を解析するために必要な桁数の最小値を書き込むことを意味し `from_chars` ます。

| `fmt`との `precision` 組み合わせ | 出力 |
|--|--|
|  どちらもオフ | 固定表記または指数表記のいずれかが短い場合は、tiebreaker として固定されています。</br>この動作は、パラメーターを受け取るオーバーロードによってシミュレートすることはできません `fmt` 。 |
| `fmt` | 指定された書式に対する最短のラウンドトリップ動作 (最も短い指数形式など)。 |
| `fmt` および `precision` | 指定された有効桁数を使用し `printf()` ます。短いラウンドトリップ動作は不要です。 |

### <a name="return-value"></a>戻り値

変換の結果を保持する[to_chars_result](to-chars-result-structure.md) 。

### <a name="example"></a>例

```cpp
#include <charconv>
#include <stdio.h>
#include <system_error>

template <typename T> void TestToChars(const T t)
{
    static_assert(std::is_floating_point_v<T>);
    constexpr bool IsFloat = std::is_same_v<T, float>;

    char buf[100]; // 100 is large enough for double and long double values because the longest possible outputs are "-1.23456735e-36" and "-1.2345678901234567e-100".
    constexpr size_t size = IsFloat ? 15 : 24;
    const std::to_chars_result res = std::to_chars(buf, buf + size, t);  // points to buffer area it can use. Must be char, not wchar_t, etc.
    
    if (res.ec == std::errc{}) // no error
    {
        // %.*s provides the exact number of characters to output because the output range, [buf, res.ptr), isn't null-terminated
        printf("success: %.*s\n", static_cast<int>(res.ptr - buf), buf);
    }
    else // probably std::errc::value_too_large
    {
        printf("Error: %d\n", static_cast<int>(res.ec));
    }
}

int main()
{
    TestToChars(123.34);
    return 0;
}
```

## `from_chars`

のシーケンスを **`char`** 整数または浮動小数点値に変換します。

```cpp
// char to an integer value

from_chars_result from_chars(const char* first, const char* last, char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, signed char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned char& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, short& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned short& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, int& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned int& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, long long& value, int base = 10);
from_chars_result from_chars(const char* first, const char* last, unsigned long long& value, int base = 10);

// char to a floating-point value

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general);
from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general);
from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

### <a name="parameters"></a>パラメーター

*まずは*\
変換する文字のバッファーの先頭を指します。

*前の*\
変換する文字のバッファーの末尾の要素の1つ後ろの位置をポイントします。

*数値*\
変換が成功した場合、には変換の結果が格納されます。

*常用*\
整数変換の場合は、変換中に使用するベース。 2 ~ 36 の範囲で指定する必要があります。

*fmt*\
浮動小数点変換の場合は、変換される文字のシーケンスの形式。 詳細については、「 [chars_format](chars-format-class.md) 」を参照してください。

### <a name="remarks"></a>解説

`from_chars()`関数は文字列を分析し \[ `first` `last` ます。) では、数値パターン () \[ `first` `last` は有効な範囲である必要があります。

文字を解析するとき、空白は無視されません。 `strtod()`たとえば、バッファーは有効な数値表現で始まる必要があります。

[From_chars_result 構造体](from-chars-result-structure.md)を返します。

数字パターンに一致する文字がない場合、は変更されず、はを `value` `from_chars_result.ptr` 指し、はです `first` `from_chars_result.ec` `errc::invalid_argument` 。

一部の文字のみが数値パターンに一致する場合は、 `from_chars_result.ptr` パターンに一致しない最初の文字を指します。または、すべての文字が一致する場合は、パラメーターの値を指定し `last` ます。

解析された値がの型で表現可能な範囲内にない場合 `value` 、 `value` は変更されず、 `from_chars_result.ec` はです `errc::result_out_of_range` 。

それ以外の場合、は、丸められ `value` た後、がと等しい、解析された値に設定され `from_chars_result.ec` `errc{}` ます。

### <a name="example"></a>例

```cpp
#include <charconv>
#include <stdio.h>
#include <string_view>
#include <system_error>

double TestFromChars(const std::string_view sv)
{
    const char* const first = sv.data();
    const char* const last = first + sv.size();
    double dbl;

    const std::from_chars_result res = std::from_chars(first, last, dbl);

    if (res.ec == std::errc{}) // no error
    {
        printf("success: %g\n", dbl);
    }
    else
    {
        printf("Error: %d\n", static_cast<int>(res.ec));
    }

    return dbl;
}

int main()
{
    double dbl = TestFromChars("123.34");
    return 0;
}
```

## <a name="see-also"></a>関連項目

[\<charconv>](charconv.md)  
[ラウンドトリップを行う最短の10進数文字列](https://www.exploringbinary.com/the-shortest-decimal-string-that-round-trips-examples/)