---
title: fputs、fputws
ms.date: 11/04/2016
apiname:
- fputs
- fputws
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fputs
- fputws
- _fputts
helpviewer_keywords:
- streams, writing strings to
- fputws function
- _fputts function
- fputs function
- fputts function
ms.assetid: d48c82b8-aa17-4830-8c7d-30442ddbb326
ms.openlocfilehash: 3f7c7cff3300ae28717062a41aebd9e19c0cb5e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50574851"
---
# <a name="fputs-fputws"></a>fputs、fputws

ストリームに文字列を書き込みます。

## <a name="syntax"></a>構文

```C
int fputs(
   const char *str,
   FILE *stream
);
int fputws(
   const wchar_t *str,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*str*<br/>
出力する文字列。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

これらの関数は、正常に終了した場合に 0 以上の値を返します。 エラーが発生、 **fputs**と**fputws**返す**EOF**します。 場合*str*または*ストリーム*null ポインターの場合は、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**し**fputs**返します**EOF**、および**fputws**返します**WEOF**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

これらの関数のコピー *str*出力に*ストリーム*現在の位置。 **fputws**ワイド文字引数をコピー *str*に*ストリーム*マルチバイト文字の文字列またはワイド文字の文字列かどうかに従ってとして*ストリーム*それぞれテキスト モードまたはバイナリ モードで開かれます。 どちらの関数も、終端の null 文字をコピーしません。

ストリームが ANSI モードで開かれている場合、2 つの関数の動作は同じになります。 **fputs** UNICODE ストリームへ現在出力をサポートしません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputts**|**fputs**|**fputs**|**fputws**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fputs**|\<stdio.h>|
|**fputws**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル、**stdin**、 **stdout**、および**stderr**-C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fputs.c
// This program uses fputs to write
// a single line to the stdout stream.

#include <stdio.h>

int main( void )
{
   fputs( "Hello world from fputs.\n", stdout );
}
```

```Output
Hello world from fputs.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgets、fgetws](fgets-fgetws.md)<br/>
[gets、_getws](../../c-runtime-library/gets-getws.md)<br/>
[puts、_putws](puts-putws.md)<br/>
