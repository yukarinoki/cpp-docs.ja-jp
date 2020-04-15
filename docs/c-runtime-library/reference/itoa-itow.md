---
title: _itoa、_itow機能
ms.date: 4/2/2020
api_name:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- _o__i64toa
- _o__i64tow
- _o__itoa
- _o__itow
- _o__ltoa
- _o__ltow
- _o__ui64toa
- _o__ui64tow
- _o__ultoa
- _o__ultow
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
ms.openlocfilehash: 0cc084076c5e39843ecc1afa08671ce6b2f06d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342709"
---
# <a name="itoa-_itoa-ltoa-_ltoa-ultoa-_ultoa-_i64toa-_ui64toa-_itow-_ltow-_ultow-_i64tow-_ui64tow"></a>itoa、_itoa、ltoa、_ltoa、ultoa、_ultoa、_i64toa、_ui64toa、_itow、_ltow、_ultow、_i64tow、_ui64tow

整数を文字列に変換します。 これらの関数のより安全なバージョンを使用できます。[_itoa_s、_itow_s機能](itoa-s-itow-s.md)を参照してください。

## <a name="syntax"></a>構文

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These POSIX versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>パラメーター

*value*<br/>
変換される数値。

*バッファー*<br/>
変換の結果を保持するバッファー。

*基数*<br/>
*値*の変換に使用する基数は、2 から 36 の範囲内になければなりません。

*サイズ*<br/>
文字タイプの単位で表したバッファーの長さ。 このパラメーターは、C++ の*バッファー*引数から推論されます。

## <a name="return-value"></a>戻り値

これらの関数は、 *buffer*へのポインタを返します。 エラーの戻り値はありません。

## <a name="remarks"></a>解説

**_itoa**、 **_ltoa**、 **_ultoa**、 **_i64toa**、および **_ui64toa**関数は、指定された*引数*の数字を NULL で終わる文字列に変換し、結果 ( **_itoa**、 **_ltoa**、 、 **_ultoa**、 および **_i64toa**と **_ui64toa**の場合は 65 文字まで ) を*buffer*に格納します。 *基数*が 10 に等しく、*値*が負の場合、格納された文字列の最初の文字**-** はマイナス記号 ( ) です。 **_itow**、 **_ltow**、 **_ultow**、 **_i64tow**、 および **_ui64tow**関数は、 それぞれ **、 _itoa**、 **_ltoa**、 **_ultoa**、 **_i64toa**、**および _ui64toa**のワイド文字バージョンです。

> [!IMPORTANT]
> これらの関数は、小さすぎるバッファの終端を超えて書き込むことができます。 バッファー オーバーランを防ぐには、*変換*後の数字に続くヌル文字と符号文字を保持できるバッファーの大きさを確認します。 これらの関数を誤用すると、コード内の重大なセキュリティ問題が発生する可能性があります。

セキュリティ上の問題が発生する可能性があるため、既定では、これらの関数は廃止警告[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md):**この関数または変数は安全でない可能性があります。代わりにsafe_functionを使用することを検討してください***safe_function***。非推奨を無効にするには、_CRT_SECURE_NO_WARNINGSを使用します。** 警告メッセージに示される*safe_function*を使用するようにソース コードを変更することをお勧めします。 より安全な関数は、指定されたバッファー サイズより多くの文字を書き込みしません。 詳細については、「関数の[_itoa_s_itow_s」](itoa-s-itow-s.md)を参照してください。

非推奨の警告を表示せずにこれらの関数を使用するには、CRT ヘッダーをインクルードする前に **、_CRT_SECURE_NO_WARNINGS**プリプロセッサ マクロを定義します。 これは **、/D_CRT_SECURE_NO_WARNINGS**コンパイラ オプションを**cl**コマンドに追加することで、開発者コマンド プロンプトのコマンド ラインで行うことができます。 それ以外の場合は、ソース ファイルでマクロを定義します。 プリコンパイル済みヘッダーを使用する場合は、プリコンパイル済みヘッダーインクルード ファイル*pch.h* (Visual Studio 2017 および 2017 以前の*stdafx.h)* の先頭にマクロを定義します。 ソース コードでマクロを定義するには、次の例のように、CRT ヘッダーをインクルードする前に **#define**ディレクティブを使用します。

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++ では、これらの関数は、より安全な関数を呼び出すテンプレートのオーバーロードを持っています。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

POSIX の名前**は、イトア**、 **ltoa**、および**ultoa**の **_itoa**、 **_ltoa**、および **_ultoa**関数の別名として存在します。 POSIX 名は、ISO C の実装固有のグローバル関数名規則に従わないため、非推奨です。デフォルトでは、これらの関数は廃止警告[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md):**この項目の POSIX 名は非推奨です。代わりに、ISO C および C++ の準拠名を使用** *new_nameします*。 これらの関数の安全なバージョン **、_itoa_s、_ltoa_s、** または **_ultoa_s**を使用 **_ltoa_s**するようにソース コードを変更することをお勧めします。 詳細については、「関数の[_itoa_s_itow_s」](itoa-s-itow-s.md)を参照してください。

ソース コードの移植性のために、コード内の POSIX 名を保持する方がよい場合があります。 非推奨の警告を表示せずにこれらの関数を使用するには、CRT ヘッダーを含める前に **、_CRT_NONSTDC_NO_WARNINGS**と **_CRT_SECURE_NO_WARNINGS**プリプロセッサ マクロの両方を定義します。 これは **、/D_CRT_SECURE_NO_WARNINGS**および **/D_CRT_NONSTDC_NO_WARNINGS**コンパイラ オプションを**cl**コマンドに追加することで、開発者コマンド プロンプトのコマンド ラインで行うことができます。 それ以外の場合は、ソース ファイルにマクロを定義します。 プリコンパイル済みヘッダーを使用する場合は、プリコンパイル済みヘッダーインクルードファイルの先頭にマクロを定義します。 ソース コードでマクロを定義するには、次**の**例のように、CRT ヘッダーをインクルードする前に#define ディレクティブを使用します。

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>最大変換数マクロ

変換用の安全なバッファを作成するために、CRT には便利なマクロがいくつか含まれています。 これらは、いくつかの共通のベースの null 終端文字と符号文字を含む、各整数型の可能な最も長い値を変換するために必要なバッファーのサイズを定義します。 radix で指定されたベースで変換を受け取るために変換バッファーの大*radix*きさを確保するには、バッファーを割り振るときに、これらの定義済みマクロのいずれかを使用します。 これは、整数型を文字列に変換するときに、バッファー オーバーラン エラーを防ぐのに役立ちます。 これらのマクロは、ソースに stdlib.h または wchar.h を含めるときに定義されます。

これらのマクロのいずれかを文字列変換関数で使用するには、適切な文字型の変換バッファーを宣言し、整数型のマクロ値と基本値をバッファー ディメンションとして使用します。 次の表に、リストされたベースの各関数に適したマクロを示します。

||||
|-|-|-|
|関数|radix|マクロ|
|**_itoa** **,_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

次の例では、変換カウント マクロを使用して、底 2 に**符号なし long long**を含めるのに十分な大きさのバッファーを定義します。

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**イトー ,** **ltoa**,**ウルトー**|\<stdlib.h>|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<stdlib.h>|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h> または \<wchar.h>|

これらの関数とマクロは、マイクロソフト固有のものです。 互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

このサンプルでは、いくつかの整数変換関数の使用例を示します。 警告 C4996 を消音するために **_CRT_SECURE_NO_WARNINGS**マクロを使用することに注意してください。

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s、_itow_s機能](itoa-s-itow-s.md)<br/>
