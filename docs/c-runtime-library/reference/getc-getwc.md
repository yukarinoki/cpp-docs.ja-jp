---
title: getc、getwc
ms.date: 4/2/2020
api_name:
- getwc
- getc
- _o_getc
- _o_getwc
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _gettc
- getwc
- _gettchar
- getc
helpviewer_keywords:
- characters, reading
- _gettc function
- getwchar function
- streams, reading characters from
- reading characters from streams
- getc function
- getwc function
- gettc function
ms.assetid: 354ef514-d0c7-404b-92f5-995f6a834bb3
ms.openlocfilehash: 5c05d7a2743cd0c1e843d6895e8f5574031ab098
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344833"
---
# <a name="getc-getwc"></a>getc、getwc

ストリームから単一の文字を読み取ります。

## <a name="syntax"></a>構文

```C
int getc(
   FILE *stream
);
wint_t getwc(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
入力ストリーム。

## <a name="return-value"></a>戻り値

読み取られた文字を返します。 読み取りエラーまたはファイルの終わりの条件を示すには **、getc は** **EOF**を返し **、getwc は** **WEOF**を返します。 **getc**の場合は **、ferror**または**feof**を使用して、エラーまたはファイルの終わりをチェックします。 *ストリーム*が**NULL**の場合は **、getc**と**getwc**が無効なパラメータ ハンドラを呼び[出します。](../../c-runtime-library/parameter-validation.md) 実行を続行できる場合、これらの関数は**EOF** **(getwc**の**場合は WEOF)** を返し **、errno**を**EINVAL**に設定します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

各ルーチンはファイルの現在の位置から 1 文字読み取り、関連付けられたファイル ポインター (定義されている場合) をインクリメントして次の文字を指します。 ファイルは*stream*に関連付けられます。

これらの関数は呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンについては、「[_getc_nolock、_getwc_nolock](getc-nolock-getwc-nolock.md)」をご覧ください。

ルーチン固有の解説は、次のとおりです。

|ルーチン|解説|
|-------------|-------------|
|**getc**|**fgetc**と同じですが、関数およびマクロとして実装されます。|
|**getwc**|**getc**のワイドキャラクターバージョン。 *ストリーム*がテキスト モードまたはバイナリ モードで開かれているかどうかに応じて、マルチバイト文字またはワイド文字を読み取ります。|

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettc**|**getc**|**getc**|**getwc**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**getc**|\<stdio.h>|
|**getwc**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_getc.c
// Use getc to read a line from a file.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;
    FILE* fp;

    // Read a single line from the file "crt_getc.txt".

    fopen_s(&fp, "crt_getc.txt", "r");
    if (!fp)
    {
       printf("Failed to open file crt_getc.txt.\n");
       exit(1);
    }

    for (i = 0; (i < 80) && ((ch = getc(fp)) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);

    fclose(fp);
}
```

### <a name="input-crt_getctxt"></a>入力: crt_getc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
Input was: Line one.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc、fgetwc](fgetc-fgetwc.md)<br/>
[_getch、_getwch](getch-getwch.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
[ungetc、ungetwc](ungetc-ungetwc.md)<br/>
