---
title: _itoa、_itow 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
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
apilocation:
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
apitype: DLLExport
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 95aa140eae6d8a06eff84d03cbb562444c3bd552
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="itoa-itoa-ltoa-ltoa-ultoa-ultoa-i64toa-ui64toa-itow-ltow-ultow-i64tow-ui64tow"></a>itoa、_itoa、ltoa、_ltoa、ultoa、_ultoa、_i64toa、_ui64toa、_itow、_ltow、_ultow、_i64tow、_ui64tow

整数を文字列に変換します。 これらの関数のより安全なバージョンを利用できます。参照してください[_itoa_s、_itow_s 関数](itoa-s-itow-s.md)です。

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

// These Posix versions of the functions have deprecated names:
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

*値*<br/>
変換される数値。

*バッファー*<br/>
変換の結果を保持するバッファー。

*radix*<br/>
変換に使用する基本*値*2 ~ 36 の範囲にする必要があります。

*size*<br/>
文字型の単位のバッファーの長さ。 このパラメーターはから推測、*バッファー* C++ での引数。

## <a name="return-value"></a>戻り値

これらの関数の各へのポインターを返します*バッファー*です。 エラーの戻り値はありません。

## <a name="remarks"></a>コメント

**_Itoa**、 **_ltoa**、 **_ultoa**、 **_i64toa**、および **_ui64toa**の桁を関数に変換指定された*値*文字の null で終わる文字列とストア結果への引数 (の場合最大 33 文字 **_itoa**、 **_ltoa**、および **_ultoa**、場合最大 65 **_i64toa**と **_ui64toa**) で*バッファー*です。 場合*基数*10 に等しいと*値*は負の場合、格納された文字列の最初の文字が負符号 (**-**)。 **_Itow**、 **_ltow**、 **_ultow**、 **_i64tow**、および **_ui64tow**関数は、ワイド文字バージョンの **_itoa**、 **_ltoa**、 **_ultoa**、 **_i64toa**、および **_ui64toa**、それぞれします。

> [!IMPORTANT]
> これらの関数は、小さすぎてバッファーの末尾に記述できます。 バッファー オーバーランを防ぐには、*バッファー*変換された数字と末尾の null 文字、および符号文字を保持するために十分な大きさです。 これらの関数の誤用には、コードで重大なセキュリティ問題を可能性があります。

これらの関数により、潜在的なセキュリティ問題については、既定には使用中止警告が発生する[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md):**この関数または変数がセーフである可能性があります。使用を検討して** *safe_function* **代わりにします。廃止予定機能を無効にするには、_CRT_SECURE_NO_WARNINGS を使用します。** 使用するソース コードを変更することをお勧め、 *safe_function*警告メッセージが提示されます。 安全な関数では、指定したバッファー サイズを超える文字数は書き込まれません。 詳細については、次を参照してください。 [_itoa_s、_itow_s 関数](itoa-s-itow-s.md)です。

廃止警告なしのこれらの関数を使用して、定義、 **_CRT_SECURE_NO_WARNINGS** CRT ヘッダーをインクルードする前に、プリプロセッサ マクロです。 これを行う開発者コマンド プロンプトでコマンドの行に追加することによって、 **/D_CRT_SECURE_NO_WARNINGS**コンパイラ オプションを**cl**コマンド。 それ以外の場合、ソース ファイルでマクロを定義します。 プリコンパイル済みヘッダーを使用する場合は、プリコンパイル済みヘッダーの上部にあるマクロを定義します。 通常 stdafx.h ファイルを含めるようにします。 マクロを定義する、ソース コードで、使用、 **#define**ディレクティブ例のように、任意の CRT ヘッダーをインクルードする前に。

```C
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++ では、これらの関数より安全なバージョンを呼び出しますテンプレートのオーバー ロードがあります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

Posix 名**itoa**、 **ltoa**、および**ultoa**のエイリアスとして存在している、 **_itoa**、 **_ltoa**、および **_ultoa**関数。 ISO c の実装固有の関数名の規則に従っていないため Posix 名は使用されていません既定では、これらの関数は使用中止警告が発生する[C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md):**このアイテムの POSIX 名は使用されなくなりました。代わりに、ISO C および C++ に準拠する名前を使用:** *new_name*です。 これらの関数より安全なバージョンを使用するソース コードを変更することをお勧め **_itoa_s**、 **_ltoa_s**、または **_ultoa_s**です。 詳細については、次を参照してください。 [_itoa_s、_itow_s 関数](itoa-s-itow-s.md)です。

ソース コードの移植性に対する、コード内の Posix 名を保持することができます。 廃止警告なしのこれらの関数を使用するには、両方を定義、 **_CRT_NONSTDC_NO_WARNINGS**と **_CRT_SECURE_NO_WARNINGS** CRT ヘッダーをインクルードする前に、プリプロセッサ マクロです。 これを行う開発者コマンド プロンプトでコマンドの行に追加することによって、 **/D_CRT_SECURE_NO_WARNINGS**と **/D_CRT_NONSTDC_NO_WARNINGS**コンパイラ オプションを**cl**コマンド。 それ以外の場合、ソース ファイル内のマクロを定義します。 プリコンパイル済みヘッダーを使用する場合は、定義プリコンパイル済みヘッダーの上部にあるマクロが通常 stdafx.h ファイルを含めるようにします。 マクロを定義する、ソース コードで、次のように使用します。 **#define**ディレクティブ例のように、任意の CRT ヘッダーをインクルードする前に。

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>変換の最大数マクロ

変換をセキュリティで保護されたバッファーを作成するために、CRT には、いくつかの便利なマクロが含まれています。 これらは、null 終端文字を含む、各整数型の最も長い可能な値に変換するために必要なバッファーのサイズを定義し、いくつかの一般的なベースの文字を署名します。 変換バッファーがで指定した基数での変換はすべてを受信するのに十分な大きさであることを確認する*基数*、これらのいずれかは、バッファーを割り当てるときにマクロを定義します。 これは、整数型を文字列に変換すると、バッファー オーバーラン エラーを防ぐのに役立ちます。 ソースの stdlib.h または wchar.h のいずれかを含める場合は、これらのマクロが定義されます。

使用するにはこれらのマクロのいずれかの文字列変換関数の適切な文字型の変換バッファーを宣言し、バッファー ディメンションとして、整数型とベースのマクロの値を使用します。 次の表は、マクロの一覧に基本クラスの各関数に対して適切であるを一覧します。

||||
|-|-|-|
|関数|radix|[マクロ]|
|**_itoa**、 **_itow**|16<br/>10<br/>9<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**、 **_ltow**|16<br/>10<br/>9<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**、 **_ultow**|16<br/>10<br/>9<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**、 **_i64tow**|16<br/>10<br/>9<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**、 **_ui64tow**|16<br/>10<br/>9<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

この例では、変換数マクロを使用して、定義を格納するのに十分な大きさのバッファー、 **unsigned long long 型**2 を底で。

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

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**itoa**、 **ltoa**、 **ultoa**|\<stdlib.h>|
|**_itoa**、 **_ltoa**、 **_ultoa**、 **_i64toa**、 **_ui64toa**|\<stdlib.h>|
|**_itow**、 **_ltow**、 **_ultow**、 **_i64tow**、 **_ui64tow**|\<stdlib.h> または \<wchar.h>|

これらの関数とマクロは、Microsoft 固有です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

このサンプルでは、いくつかの整数の変換関数の使用を示します。 使用に注意してください、 **_CRT_SECURE_NO_WARNINGS** C4996 の警告を無音にマクロです。

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
[_itoa_s、_itow_s 関数](itoa-s-itow-s.md)<br/>
