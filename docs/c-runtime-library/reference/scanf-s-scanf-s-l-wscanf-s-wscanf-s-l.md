---
title: scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l
ms.date: 03/26/2019
apiname:
- wscanf_s
- _wscanf_s_l
- scanf_s
- _scanf_s_l
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
- wscanf_s
- _tscanf_s_l
- _wscanf_s_l
- scanf_s
- _tscanf_s
- _scanf_s_l
helpviewer_keywords:
- reading data [C++], from input streams
- buffers [C++], buffer overruns
- _scanf_s_l function
- _wscanf_s_l function
- tscanf_s_l function
- tscanf_s function
- scanf_s function
- data [C++], reading from input stream
- wscanf_s function
- _tscanf_s_l function
- _tscanf_s function
- scanf_s_l function
- formatted data [C++], from input streams
- wscanf_s_l function
- buffers [C++], avoiding overruns
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
ms.openlocfilehash: 28697cac20181c3dda0581c7486ebb673aec1241
ms.sourcegitcommit: 06fc71a46e3c4f6202a1c0bc604aa40611f50d36
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "58508803"
---
# <a name="scanfs-scanfsl-wscanfs-wscanfsl"></a>scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l

標準入力ストリームから書式付きデータを読み取ります。 これらのバージョンの [scanf、_scanf_l、wscanf、_wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md) は、「[CRT のセキュリティ強化](../../c-runtime-library/security-features-in-the-crt.md)」にあるとおり、セキュリティが強化されています。

## <a name="syntax"></a>構文

```C
int scanf_s(
   const char *format [,
   argument]...
);
int _scanf_s_l(
   const char *format,
   locale_t locale [,
   argument]...
);
int wscanf_s(
   const wchar_t *format [,
   argument]...
);
int _wscanf_s_l(
   const wchar_t *format,
   locale_t locale [,
   argument]...
);
```

### <a name="parameters"></a>パラメーター

*format*<br/>
書式指定文字列。

*argument*<br/>
省略可能な引数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常に変換および代入されたフィールドの数を返します。 戻り値には、読まれたが割り当てられていないフィールドは含まれません。 戻り値 0 は、フィールドが割り当てられていないことを示します。 戻り値は**EOF**エラー、またはファイルの終端文字または文字列の終端文字が文字を読み取るには、最初の試行で見つかった場合。 場合*形式*は、 **NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**scanf_s**と**wscanf_s**返す**EOF**設定と**errno**に**EINVAL**.

エラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Scanf_s**関数は、標準の入力ストリームからデータを読み取る**stdin**、し、それを書き込みます*引数*します。 各*引数*に型指定子に対応する変数の型へのポインターである必要があります*形式*します。 重なり合う文字列間でコピーした場合の動作は未定義です。

**wscanf_s**のワイド文字バージョンです**scanf_s**、*形式*引数**wscanf_s**はワイド文字列です。 **wscanf_s**と**scanf_s**ストリームが ANSI モードで開かれている場合の動作は同じです。 **scanf_s** UNICODE ストリームからの入力を現在サポートされていません。

これらの関数のバージョン、 **_l**サフィックスは同じですが、それらを使用して、*ロケール*パラメーターは、現在のスレッド ロケールの代わりにします。

異なり**scanf**と**wscanf**、 **scanf_s**と**wscanf_s**いくつかのパラメーターのバッファー サイズを指定する必要があります。 すべてのサイズを指定**c**、 **C**、 **s**、 **S**、または文字列コントロール セット **:operator[]** パラメーター。 バッファー サイズを文字では、追加のパラメーターとして渡されます。 バッファーまたは変数に、ポインターの直後にします。 たとえば、文字列を読み取る場合として次のようなその文字列のバッファー サイズが渡されます。

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

バッファー サイズには、ターミナル、null が含まれます。 幅指定フィールドを使用すると、バッファーに適合で読み取られたトークンを確認します。 トークンが大きすぎて、幅指定がない限り、バッファーに書き込ま nothing です。

> [!NOTE]
> 型のサイズのパラメーターが**符号なし**ではなく、 **size_t**します。 静的キャストを使用して変換を**size_t**値を**符号なし**64 ビット用の構成をビルドします。

バッファー サイズのパラメーターには、バイトではなく、文字の最大数について説明します。 この例では、バッファーの種類の幅は、書式指定子の幅と一致しません。

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

**S**書式指定子は、「反対」の既定の幅は、関数でサポートする、文字幅を使用することを意味します。 文字幅は 1 バイトですが、関数は、2 バイト文字をサポートしています。 この例では、最大 9 つの単一バイト幅文字の文字列を読み取り、ダブル バイト幅文字バッファーに格納されます。 文字は 1 バイト値として処理されます。したがって、最初の 2 文字は `ws[0]` に格納され、次の 2 文字は `ws[1]` に格納され、以降も同様に処理されます。

この例では、1 つの文字を読み取ります。

```C
char c;
scanf_s("%c", &c, 1);
```

Null で終わる文字列の複数の文字が読み取られると、整数が、幅指定とバッファー サイズの両方を使用します。

```C
char c[4];
scanf_s("%4c", c, (unsigned)_countof(c)); // not null terminated
```

詳細については、「[scanf 関数の文字幅指定](../../c-runtime-library/scanf-width-specification.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tscanf_s**|**scanf_s**|**scanf_s**|**wscanf_s**|
|**_tscanf_s_l**|**_scanf_s_l**|**_scanf_s_l**|**_wscanf_s_l**|

詳細については、「[Format Specification Fields: scanf and wscanf Functions](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」(scanf 関数と wscanf 関数の書式指定フィールド) をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**scanf_s**、 **_scanf_s_l**|\<stdio.h>|
|**wscanf_s**、 **_wscanf_s_l**|\<stdio.h> または \<wchar.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリでサポートされていません。 標準ストリームのハンドル**stdin**、 **stdout**、および**stderr** C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_scanf_s.c
// This program uses the scanf_s and wscanf_s functions
// to read formatted input.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int      i,
            result;
   float    fp;
   char     c,
            s[80];
   wchar_t  wc,
            ws[80];

   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   printf( "The number of fields input is %d\n", result );
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,
           wc, s, ws);
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );
   wprintf( L"The number of fields input is %d\n", result );
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,
            c, wc, s, ws);
}
```

この入力を使用すると、このプログラムでは次の出力が生成されます。

```Input
71 98.6 h z Byte characters
36 92.3 y n Wide characters
```

```Output
The number of fields input is 6
The contents are: 71 98.599998 h z Byte characters
The number of fields input is 6
The contents are: 36 92.300003 y n Wide characters
```

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[fscanf、_fscanf_l、fwscanf、_fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[printf、_printf_l、wprintf、_wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[sscanf、_sscanf_l、swscanf、_swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
