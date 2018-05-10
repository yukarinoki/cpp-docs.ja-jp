---
title: _getcwd、_wgetcwd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10f242569579680c8e388b84bdcaca235a142a34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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
文字数でパスの最大長: **char**の **_getcwd**と**wchar_t**の **_wgetcwd**です。

## <a name="return-value"></a>戻り値

ポインターを返します*バッファー*です。 A **NULL** 、エラーを返すと**errno**に設定されているいずれかの**ENOMEM**に割り当てる十分なメモリがあることを示す*maxlen*バイト数 (ときに、 **NULL**として引数が指定されている*バッファー*)、または**ERANGE**、パスがより長いことを示す*maxlen*文字です。 場合*maxlen*以下が 0 の場合にこの関数によって呼び出されます、無効なパラメーター ハンドラーを」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Getcwd**関数は、既定のドライブの現在の作業ディレクトリの完全パスを取得しに格納*バッファー*です。 整数の引数*maxlen*パスの最大長を指定します。 パス (終端の null 文字を含む) の長さを超えた場合にエラーが発生した*maxlen*です。 *バッファー*引数を指定できます**NULL**以外の場合は、少なくともサイズのバッファー *maxlen* (必要な場合にのみ以上) が自動的に割り当てられたを使用して**malloc**、パスを格納します。 このバッファーは、呼び出すことによって後で解放できます**空き**を渡すこと、 **_getcwd**値 (割り当てられたバッファーへのポインター) を返します。

**_getcwd**を現在の作業ディレクトリのパスを表す文字列を返します。 現在の作業ディレクトリがルートの場合、文字列が、円記号で終わる ( **\\** )。 現在の作業ディレクトリがルート以外のディレクトリの場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。

**_wgetcwd**のワイド文字バージョンは、 **_getcwd**;*バッファー*引数と戻り値の **_wgetcwd**ワイド文字列です。 **_wgetcwd**と **_getcwd**それ以外の場合の動作は同じです。

ときに **_DEBUG**と **_CRTDBG_MAP_ALLOC**への呼び出しで定義されている **_getcwd**と **_wgetcwd**への呼び出しによって置き換えられます **_getcwd_dbg**と **_wgetcwd_dbg**メモリ割り当てをデバッグできるようにします。 詳細については、「[_getcwd_dbg、_wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md)」をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
