---
title: _fputchar、_fputwchar
ms.date: 11/04/2016
apiname:
- _fputchar
- _fputwchar
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
- fputtchar
- _fputwchar
- fputwchar
- _fputtchar
- fputchar
- _fputchar
helpviewer_keywords:
- fputchar function
- standard output, writing to
- _fputtchar function
- fputwchar function
- _fputwchar function
- fputtchar function
- _fputchar function
ms.assetid: b92ff600-a924-4f2b-b0e7-3097ee31bdff
ms.openlocfilehash: 57ec2350fa1d0b681c6eed0c4cfc4ec4660977e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287931"
---
# <a name="fputchar-fputwchar"></a>_fputchar、_fputwchar

**stdout** に文字を出力します。

## <a name="syntax"></a>構文

```C
int _fputchar(
   int c
);
wint_t _fputwchar(
   wchar_t c
);
```

### <a name="parameters"></a>パラメーター

*c*<br/>
書き込む文字。

## <a name="return-value"></a>戻り値

これらの各関数は、書き込まれた文字を返します。 **_Fputchar**、戻り値の**EOF**はエラーを示します。 **_Fputwchar**、戻り値の**WEOF**はエラーを示します。 C が場合**NULL**、」の説明に従って、これらの関数は、無効なパラメーター例外を生成[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 返されるかどうかは、引き続き実行が許可された、 **EOF** (または**WEOF**) を設定および**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

これらの関数の両方が 1 文字を書き込み*c*に**stdout**を適切なインジケーターを進めます。 **_fputchar**と等価`fputc( stdout )`します。 等しくも**putchar**が、関数とマクロではなく関数としてのみを実装します。 異なり**fputc**と**putchar**、これらの関数は ANSI 規格と互換性がありません。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_fputtchar**|**_fputchar**|**_fputchar**|**_fputwchar**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fputchar**|\<stdio.h>|
|**_fputwchar**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールがサポートされていません。 コンソールに関連付けられている標準ストリームのハンドル、**stdin**、 **stdout**、および**stderr**-C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります. 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fputchar.c
// This program uses _fputchar
// to send a character array to stdout.

#include <stdio.h>

int main( void )
{
    char strptr[] = "This is a test of _fputchar!!\n";
    char *p = NULL;

    // Print line to stream using _fputchar.
    p = strptr;
    while( (*p != '\0') && _fputchar( *(p++) ) != EOF )
      ;
}
```

```Output
This is a test of _fputchar!!
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fgetc、fgetwc](fgetc-fgetwc.md)<br/>
[putc、putwc](putc-putwc.md)<br/>
