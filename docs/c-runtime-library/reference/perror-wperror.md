---
title: perror、_wperror
ms.date: 4/2/2020
api_name:
- _wperror
- perror
- _o__wperror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wperror
- _tperror
- perror
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
ms.openlocfilehash: 0c50e77863b4b136ac59b6f79d8e529691032609
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338534"
---
# <a name="perror-_wperror"></a>perror、_wperror

エラー メッセージを印刷します。

## <a name="syntax"></a>構文

```C
void perror(
   const char *message
);
void _wperror(
   const wchar_t *message
);
```

### <a name="parameters"></a>パラメーター

*メッセージ*<br/>
印刷する文字列メッセージ。

## <a name="remarks"></a>解説

**perror**関数は、エラー メッセージを**stderr**に出力します。 **_wperror**はワイド文字の **_perror**です。**_wperror**する*メッセージ*引数はワイド文字ストリングです。 **_wperror**と **_perror**は、そうでなければ同じように動作します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**Perror**|**Perror**|**_wperror**|

*メッセージ*は最初に印刷され、次にコロンが続き、エラーを生成した最後のライブラリー呼び出しに対するシステム・エラー・メッセージが続き、最後に改行文字が出力されます。 *message*が null ポインターまたは null 文字列へのポインターの場合 **、perror**はシステム エラー メッセージのみを出力します。

エラー番号は、変数 [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (ERRNO.H で定義) に格納されます。 システム エラー メッセージは、エラー番号順のメッセージの配列である変数 [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) を使用してアクセスできます。 **perror は****、errno**値を **_sys_errlist**するインデックスとして使用して、適切なエラー メッセージを出力します。 変数[_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)の値は **、_sys_errlist**配列内の要素の最大数として定義されます。

正確な結果を得るには、ライブラリ ルーチンがエラーで戻った直後に**perror**を呼び出します。 それ以外の場合、後続の呼び出しは**errno**値を上書きできます。

Windows オペレーティング システムでは **、ERRNO**に一覧表示されているエラー値があります。H は未使用です。 これらの値は、UNIX オペレーティング システムで使用するために予約されたものです。 Windows オペレーティング・システムで使用される errno 値のリストについては[、_doserrno、errno、_sys_errlist、および_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)を参照してください。 **errno** **perror**は、これらのプラットフォームで使用されていない**errno**値の空の文字列を出力します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**Perror**|\<stdio.h> または \<stdlib.h>|
|**_wperror**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_perror.c
// compile with: /W3
/* This program attempts to open a file named
* NOSUCHF.ILE. Because this file probably doesn't exist,
* an error message is displayed. The same message is
* created using perror, strerror, and _strerror.
*/

#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <share.h>

int main( void )
{
   int  fh;

   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )
   {
      /* Three ways to create error message: */
      perror( "perror says open failed" );
      printf( "strerror says open failed: %s\n",
         strerror( errno ) ); // C4996
      printf( _strerror( "_strerror says open failed" ) ); // C4996
      // Note: strerror and _strerror are deprecated; consider
      // using strerror_s and _strerror_s instead.
   }
   else
   {
      printf( "open succeeded on input file\n" );
      _close( fh );
   }
}
```

```Output
perror says open failed: No such file or directory
strerror says open failed: No such file or directory
_strerror says open failed: No such file or directory
```

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[str エラー、_strerror、_wcserror、_wcserror \_](strerror-strerror-wcserror-wcserror.md)<br/>
