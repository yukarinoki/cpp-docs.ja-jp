---
title: _getcwd、_wgetcwd
description: C ランタイム ライブラリ関数は、現在の作業ディレクトリを取得_wgetcwd、_getcwd。
ms.date: 4/2/2020
api_name:
- _wgetcwd
- _getcwd
- _o__getcwd
- _o__wgetcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: bc19a416ebebeb901e8dbb435971e6d5f33e4067
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344443"
---
# <a name="_getcwd-_wgetcwd"></a>_getcwd、_wgetcwd

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

*バッファー*\
パスの格納場所。

*Maxlen*\
パスの最大長は文字で **、_getcwd**は**文字で****、wchar_t****は_wgetcwd。**

## <a name="return-value"></a>戻り値

*バッファ*へのポインタを返します。 **NULL**戻り値はエラーを示し **、errno**は**ENOMEM**に設定され、メモリが不足して*最大*バイトを割り当てるためのメモリが不足しているか **(NULL**引数が*バッファ*として指定されている場合)、**または ERANGE**に設定され、パスが*maxlen*文字より長いことを示します。 *maxlen*がゼロ以下の場合、この関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_getcwd**関数は、デフォルトのドライブの現在の作業ディレクトリの完全パスを取得し *、buffer*に格納します。 整数引数*maxlen*は、パスの最大長を指定します。 パスの長さ (終端の NULL 文字を含む) が*maxlen*を超えるとエラーが発生します。 *バッファー*引数は**NULL に**できます。少なくともサイズ*の maxlen* (必要な場合だけ) のバッファは、パスを格納するために**malloc**を使用して自動的に割り当てられます。 このバッファーは、後で解放するには **、解放解放**を呼び出し、それを **_getcwd**戻り値 (割り当てられたバッファーへのポインター) を渡します。

**_getcwd**は、現在の作業ディレクトリのパスを表す文字列を返します。 現在の作業ディレクトリがルートの場合、文字列は円記号 ()`\`で終わります。 現在の作業ディレクトリがルート以外のディレクトリの場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。

**_wgetcwd**はワイド文字の **_getcwd**バージョンです。*バッファ*引数と **_wgetcwd**の戻り値はワイド文字列です。 **_wgetcwd**と **_getcwd**は同じように動作します。

**_DEBUG**と **_CRTDBG_MAP_ALLOC**が定義されている場合 **、_getcwd**および **_wgetcwd**の呼び出しは **、_getcwd_dbg****への呼**び出しに置き換えられ、_wgetcwd_dbgメモリ割り当てのデバッグが可能になります。 詳細については、「 [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getcwd**|\<direct.h>|
|**_wgetcwd**|\<direct.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_getcwd.c
// Compile with: cl /W4 crt_getcwd.c
// This program places the name of the current directory in the
// buffer array, then displays the name of the current directory
// on the screen. Passing NULL as the buffer forces getcwd to allocate
// memory for the path, which allows the code to support file paths
// longer than _MAX_PATH, which are supported by NTFS.

#include <direct.h> // _getcwd
#include <stdlib.h> // free, perror
#include <stdio.h>  // printf
#include <string.h> // strlen

int main( void )
{
   char* buffer;

   // Get the current working directory:
   if ( (buffer = _getcwd( NULL, 0 )) == NULL )
      perror( "_getcwd error" );
   else
   {
      printf( "%s \nLength: %zu\n", buffer, strlen(buffer) );
      free(buffer);
   }
}
```

```Output
C:\Code
```

## <a name="see-also"></a>関連項目

[ディレクトリコントロール](../../c-runtime-library/directory-control.md)\
[_chdir,_wchdir](chdir-wchdir.md)\
[_mkdir、_wmkdir](mkdir-wmkdir.md)\
[_rmdir、_wrmdir](rmdir-wrmdir.md)
