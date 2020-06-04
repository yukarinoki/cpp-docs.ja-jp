---
title: fputc、fputwc
ms.date: 4/2/2020
api_name:
- fputc
- fputwc
- _o_fputc
- _o_fputwc
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fputc
- fputwc
- _fputtc
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
ms.openlocfilehash: 90091bff6a8ee3ced050c359ed540f45afe74f6b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910201"
---
# <a name="fputc-fputwc"></a>fputc、fputwc

ストリームに文字を書き込みます。

## <a name="syntax"></a>構文

```C
int fputc(
   int c,
   FILE *stream
);
wint_t fputwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*40u-c*<br/>
書き込む文字。

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

これらの各関数は、書き込まれた文字を返します。 **Fputc**の場合、 **EOF**の戻り値はエラーを示します。 **Fputwc**の場合、 **WEOF**の戻り値はエラーを示します。 *Stream*が**NULL**の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、 **EOF**を返し、 **errno**を**EINVAL**に設定します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

これらの各関数は、関連付けられたファイルの位置インジケーター (定義されている場合) によって示される位置にあるファイルに1文字*c*を書き込み、必要に応じてインジケーターを進めます。 **Fputc**と**fputwc**の場合、ファイルは*stream*に関連付けられています。 ファイルが配置要求をサポートできない場合、または追加モードでファイルが開かれた場合、文字はストリームの末尾に追加されます。

ストリームが ANSI モードで開かれている場合、2 つの関数の動作は同じになります。 **fputc**は、現在 UNICODE ストリームへの出力をサポートしていません。

**_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 詳細については、「[_fputc_nolock、_fputwc_nolock](fputc-nolock-fputwc-nolock.md)」を参照してください。

ルーチン固有の解説は、次のとおりです。

|ルーチン|解説|
|-------------|-------------|
|**fputc**|**Putc**と同じですが、関数およびマクロとしてではなく、関数としてのみ実装されます。|
|**fputwc**|**Fputc**のワイド文字バージョン。 *ストリーム*がテキストモードとバイナリモードのどちらで開かれているかに従って、 *c*をマルチバイト文字またはワイド文字として書き込みます。|

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fputtc**|**fputc**|**fputc**|**fputwc**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fputc**|\<stdio.h>|
|**fputwc**|\<stdio.h> または \<wchar.h>|

コンソールは、ユニバーサル Windows プラットフォーム (UWP) アプリではサポートされていません。 コンソール (**stdin**、 **stdout**、 **stderr**) に関連付けられている標準ストリームハンドルは、C ランタイム関数が UWP アプリで使用できるようになる前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fputc.c
// This program uses fputc
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
   char strptr1[] = "This is a test of fputc!!\n";
   char *p;

   // Print line to stream using fputc.
   p = strptr1;
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;

}
```

```Output
This is a test of fputc!!
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc、fgetwc](fgetc-fgetwc.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
