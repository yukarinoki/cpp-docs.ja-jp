---
title: sscanf_s、_sscanf_s_l、swscanf_s、_swscanf_s_l
ms.date: 11/04/2016
apiname:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
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
apitype: DLLExport
f1_keywords:
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
helpviewer_keywords:
- stscanf_s_l function
- stscanf_s function
- swscanf_s function
- swscanf_s_l function
- sscanf_s_l function
- _stscanf_s_l function
- strings [C++], reading data from
- sscanf_s function
- _swscanf_s_l function
- _stscanf_s function
- reading data, strings
- strings [C++], reading
- _sscanf_s_l function
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
ms.openlocfilehash: b1f535ad8a418fa3ce6492f9bdaa6e0299073504
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538139"
---
# <a name="sscanfs-sscanfsl-swscanfs-swscanfsl"></a>sscanf_s、_sscanf_s_l、swscanf_s、_swscanf_s_l

文字列から書式付きデータを読み込みます。 これらのバージョンの [sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md) は、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。

## <a name="syntax"></a>構文

```C
int sscanf_s(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_s_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf_s(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_s_l(
   const wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument ] ...
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
格納されるデータ。

*format*<br/>
書式指定文字列。 詳細については、「[Format Specification Fields: scanf and wscanf Functions](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」(scanf 関数と wscanf 関数の書式指定フィールド) をご覧ください。

*argument*<br/>
省略可能な引数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 戻り値は**EOF**エラーの最初の変換の前に、文字列の末尾に達した場合またはします。

場合*バッファー*または*形式*は、 **NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返し設定と**errno**に**EINVAL**

エラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Sscanf_s**関数からデータを読み取る*バッファー*それぞれで指定された場所に*引数*します。 書式指定文字列の後に続く引数で型指定子に対応する型を持つ変数へのポインターを指定する*形式*します。 安全なバージョンとは異なり[sscanf](sscanf-sscanf-l-swscanf-swscanf-l.md)、型フィールド文字を使用する場合は、バッファー サイズのパラメーターは必要な**c**、 **C**、 **s**、**S**、または文字列コントロール セットで囲まれた **:operator[]** します。 バッファー サイズ (文字単位) は、バッファー サイズが必要な各バッファーの後に追加パラメーターとして指定する必要があります。 たとえば、文字列を読み込む場合、その文字列のバッファー サイズは次のように渡されます。

```C
wchar_t ws[10];
swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9
```

バッファー サイズには、終端 null も含まれます。 読み取られたトークンがバッファーに確実に収まるように、幅指定フィールドが使用される場合もあります。 幅指定フィールドが使用されない場合で、読み取られたトークンがバッファーに収まらない場合、そのバッファーには何も書き込まれません。

文字の場合、次のように 1 文字読み込む場合もあります。

```C
wchar_t wc;
swscanf_s(in_str, L"%c", &wc, 1);
```

次に、この例では、入力文字列とデータ ストアから 1 つの文字をワイド文字バッファーに読み込みます。 null で終わらない文字列に対して複数の文字列を読み込む場合、幅指定とバッファー サイズとして符号なし整数が使用されます。

```C
char c[4];
sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated
```

詳細については、「[scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)」と「[scanf 関数の型フィールド文字](../../c-runtime-library/scanf-type-field-characters.md)」を参照してください。

> [!NOTE]
> 型のサイズのパラメーターが**符号なし**ではなく、 **size_t**します。 64 ビット ターゲットのコンパイルをするときに、静的キャストを使用して、変換する **_countof**または**sizeof**結果を適切なサイズにします。

*形式*引数コントロール入力の解釈のフィールドし、同じ形式し、機能、*形式*の引数、 **scanf_s**関数。 重なり合う文字列間でコピーした場合の動作は未定義です。

**swscanf_s**のワイド文字バージョンは、 **sscanf_s**; 引数**swscanf_s**はワイド文字列です。 **sscanf_s**マルチバイトの 16 進数の文字を処理しません。 **swscanf_s** Unicode の全角 16 進数または「互換区域」の文字を処理しません。 それ以外の場合、 **swscanf_s**と**sscanf_s**動作は同じです。

これらの関数がのバージョン、 **_l**現在のスレッド ロケールの代わりに渡されるロケール パラメーターを使用することを除き、サフィックスは同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf_s**|**sscanf_s**|**sscanf_s**|**swscanf_s**|
|**_stscanf_s_l**|**_sscanf_s_l**|**_sscanf_s_l**|**_swscanf_s_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**sscanf_s**、 **_sscanf_s_l**|\<stdio.h>|
|**swscanf_s**、 **_swscanf_s_l**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_sscanf_s.c
// This program uses sscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string plus null terminator
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );
   sscanf_s( tokenstring, "%d", &i );
   sscanf_s( tokenstring, "%f", &fp );

   // Output the data read
   printf_s( "String    = %s\n", s );
   printf_s( "Character = %c\n", c );
   printf_s( "Integer:  = %d\n", i );
   printf_s( "Real:     = %f\n", fp );
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fscanf、_fscanf_l、fwscanf、_fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf、_scanf_l、wscanf、_wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[snprintf、_snprintf、_snprintf_l、_snwprintf、_snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)<br/>
