---
title: sscanf、_sscanf_l、swscanf、_swscanf_l
ms.date: 11/04/2016
apiname:
- swscanf
- sscanf
- _sscanf_l
- _swscanf_l
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
- _sscanf_l
- _stscanf
- swscanf
- _stscanf_l
- sscanf
- _swscanf_l
helpviewer_keywords:
- swscanf function
- _stscanf function
- sscanf function
- _stscanf_l function
- _sscanf_l function
- _swscanf_l function
- swscanf_l function
- strings [C++], reading data from
- stscanf function
- reading data, strings
- strings [C++], reading
- sscanf_l function
- stscanf_l function
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
ms.openlocfilehash: 60dbb8e89e531c3020c243d998a69370095424e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661969"
---
# <a name="sscanf-sscanfl-swscanf-swscanfl"></a>sscanf、_sscanf_l、swscanf、_swscanf_l

文字列から書式付きデータを読み出します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[sscanf_s、_sscanf_s_l、swscanf_s、_swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int sscanf(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_l(
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
書式指定文字列。 詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md)」を参照してください。

*argument*<br/>
省略可能な引数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

これらの関数は、正常に変換および代入されたフィールドの数を返します。読み込まれただけで代入されなかったフィールドは戻り値には含まれません。 戻り値が 0 の場合は、代入されたフィールドがなかったことを示します。 戻り値は**EOF**エラーの最初の変換の前に、文字列の末尾に達した場合またはします。

場合*バッファー*または*形式*は、 **NULL** 」の説明に従って、ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返し設定と**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Sscanf**関数からデータを読み取る*バッファー*各によって指定された場所に*引数*します。 すべて*引数*に型指定子に対応する型の変数へのポインターである必要があります*形式*します。 *形式*引数コントロール入力の解釈のフィールドし、同じ形式し、機能、*形式*の引数、 **scanf**関数。 重なり合う文字列間でコピーした場合の動作は未定義です。

> [!IMPORTANT]
> 含む文字列を読み取るときに**sscanf**、向けに幅を常に指定、 **%s**形式 (たとえば、 **「% 男女」** の代わりに **"%s"**) それ以外の場合。、適切な形式で入力バッファー オーバーランが発生しやすくします。

**swscanf**のワイド文字バージョンは、 **sscanf**; 引数**swscanf**はワイド文字列です。 **sscanf**マルチバイトの 16 進数の文字を処理しません。 **swscanf** Unicode の全角 16 進数または「互換区域」の文字を処理しません。 それ以外の場合、 **swscanf**と**sscanf**動作は同じです。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf**|**sscanf**|**sscanf**|**swscanf**|
|**_stscanf_l**|**_sscanf_l**|**_sscanf_l**|**_swscanf_l**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**sscanf**、 **_sscanf_l**|\<stdio.h>|
|**swscanf**、 **_swscanf_l**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_sscanf.c
// compile with: /W3
// This program uses sscanf to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string:
   sscanf( tokenstring, "%80s", s ); // C4996
   sscanf( tokenstring, "%c", &c );  // C4996
   sscanf( tokenstring, "%d", &i );  // C4996
   sscanf( tokenstring, "%f", &fp ); // C4996
   // Note: sscanf is deprecated; consider using sscanf_s instead

   // Output the data read
   printf( "String    = %s\n", s );
   printf( "Character = %c\n", c );
   printf( "Integer:  = %d\n", i );
   printf( "Real:     = %f\n", fp );
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
