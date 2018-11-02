---
title: scanf_s、_scanf_s_l、wscanf_s、_wscanf_s_l
ms.date: 11/04/2016
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
ms.openlocfilehash: 0fcf2a9f3ac8585e71caa9f2cc990c7e303a2f5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528613"
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

正常に変換され、代入されたフィールドの数を返します。この数には、読み取られても代入されなかったフィールドは含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 戻り値は**EOF**エラー、またはファイルの終端文字または文字列の終端文字が文字を読み取るには、最初の試行で発生した場合。 場合*形式*は、 **NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**scanf_s**と**wscanf_s**返す**EOF**設定と**errno**に**EINVAL**.

エラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Scanf_s**関数は、標準入力ストリームからデータを読み取る**stdin**で指定された場所にデータを書き込みます*引数*します。 各*引数*に型指定子に対応する型の変数へのポインターである必要があります*形式*します。 重なり合う文字列間でコピーした場合の動作は未定義です。

**wscanf_s**のワイド文字バージョンです**scanf_s**、*形式*引数**wscanf_s**はワイド文字列です。 **wscanf_s**と**scanf_s**ストリームが ANSI モードで開かれている場合の動作は同じです。 **scanf_s** UNICODE ストリームからの入力を現在サポートされていません。

これらの関数がのバージョン、 **_l**現在のスレッド ロケールの代わりに渡されるロケール パラメーターを使用することを除き、サフィックスは同じです。

異なり**scanf**と**wscanf**、 **scanf_s**と**wscanf_s**バッファー サイズをすべての種類の入力パラメーターを指定する必要があります**c**、 **C**、 **s**、 **S**、または文字列コントロール セットで囲まれた **:operator[]** します。 バッファー サイズ (文字単位) は、バッファーまたは変数のポインターの直後に追加パラメーターとして渡されます。 たとえば、文字列を読み込む場合、その文字列のバッファー サイズは次のように渡されます。

```C
char s[10];
scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9
```

バッファー サイズには、終端 null も含まれます。 幅指定フィールドを使用して、読み取られたトークンがバッファーに確実に収まるようにすることができます。 幅指定フィールドが使用されない場合で、読み取られたトークンがバッファーに収まらない場合、そのバッファーには何も書き込まれません。

> [!NOTE]
> 型のサイズのパラメーターが**符号なし**ではなく、 **size_t**します。 静的キャストを使用して変換を**size_t**値を**符号なし**64 ビット用の構成をビルドします。

バッファー サイズ パラメーターで、バイトではなく、文字の最大数を指定する例を次に示します。 呼び出しで**wscanf_s**バッファーの種類によって示される文字の幅が、書式指定子で示される文字の幅と一致しません。

```C
wchar_t ws[10];
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));
```

**S**書式指定子は、「反対」、関数でサポートされている既定の幅は、文字幅の使用を示します。 文字幅は 1 バイトですが、関数は 2 バイト文字をサポートしています。 この例では、最大で 9 つの 1 バイト幅文字の文字列が読み取られ、2 バイト幅文字バッファーに格納されます。 文字は 1 バイト値として処理されます。したがって、最初の 2 文字は `ws[0]` に格納され、次の 2 文字は `ws[1]` に格納され、以降も同様に処理されます。

文字の場合、次のように 1 文字読み込む場合もあります。

```C
char c;
scanf_s("%c", &c, 1);
```

null で終わらない文字列に対して複数の文字列を読み込む場合、幅指定とバッファー サイズとして整数が使用されます。

```C
char c[4];
scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated
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

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル**stdin**、 **stdout**、および**stderr**、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
