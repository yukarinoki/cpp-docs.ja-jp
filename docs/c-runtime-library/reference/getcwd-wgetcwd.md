---
title: _getcwd、_wgetcwd
ms.date: 11/04/2016
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
ms.openlocfilehash: 4c533f0e716cb9a13c152b9be3c46f60291118d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50520239"
---
# <a name="getcwd-wgetcwd"></a>_getcwd、_wgetcwd

現在の作業ディレクトリを取得します。

## <a name="syntax"></a>構文

```C
char *_getcwd(
   char *buffer,
   int maxlen
);
wchar_t *_wgetcwd(
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
パスの格納場所。

*maxlen*<br/>
パスの最大長: **char**の **_getcwd**と**wchar_t**の **_wgetcwd**します。

## <a name="return-value"></a>戻り値

ポインターを返します*バッファー*します。 A **NULL**戻り、エラー値と**errno**設定されて**ENOMEM**、割り当てるメモリが不足していることを示す*maxlen*バイト数 (ときに、 **NULL**として引数が指定されて*バッファー*)、または**ERANGE**、パスがより長いことを示す*maxlen*文字。 場合*maxlen*と同じかそれよりも少ない」の説明に従って、0 にこの関数が、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

**_Getcwd**関数は、既定のドライブの現在の作業ディレクトリの完全なパスを取得しに格納*バッファー*します。 整数の引数*maxlen*パスの最大長を指定します。 (終端の null 文字を含む) のパスの長さを超えた場合にエラーが発生した*maxlen*します。 *バッファー*引数を指定できます**NULL**; バッファーのサイズ以上*maxlen* (必要な場合にのみ詳細) が自動的に割り当てられたを使用して**malloc**パスを格納するため、します。 このバッファーは、呼び出すことによって後で解放できます**無料**を渡して、 **_getcwd** (割り当てられたバッファーへのポインター) の値を返します。

**_getcwd**の現在の作業ディレクトリのパスを表す文字列を返します。 現在の作業ディレクトリがルートの場合、文字列が、円記号で終わる ( **\\** )。 現在の作業ディレクトリがルート以外のディレクトリの場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。

**_wgetcwd**のワイド文字バージョンは、 **_getcwd**、*バッファー*引数と戻り値 **_wgetcwd**はワイド文字列です。 **_wgetcwd**と **_getcwd**動作は同じです。

ときに **_DEBUG**と **_CRTDBG_MAP_ALLOC**への呼び出しで定義されている **_getcwd**と **_wgetcwd**呼び出しに置き換え **_getcwd_dbg**と **_wgetcwd_dbg**デバッグのメモリ割り当てを許可します。 詳細については、「 [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_chdir、_wchdir](chdir-wchdir.md)<br/>
[_mkdir、_wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir、_wrmdir](rmdir-wrmdir.md)<br/>
