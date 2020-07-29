---
title: _getcwd、_wgetcwd
description: C ランタイムライブラリ関数 _getcwd、_wgetcwd 現在の作業ディレクトリを取得します。
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b6fb32a593a969f93a934f251f38cd50960440b0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221888"
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

*格納*\
パスの格納場所。

*maxlen*\
文字数でのパスの最大長 **`char`** : **_getcwd**の場合は、 **`wchar_t`** **_wgetcwd**の場合は。

## <a name="return-value"></a>戻り値

*バッファー*へのポインターを返します。 **Null**の戻り値はエラーを示し、 **errno**は**ENOMEM**に設定されます。これは、( **NULL**引数が*バッファー*として指定されている場合) *maxlen*バイトを割り当てるのに十分なメモリがないことを示し、 **ERANGE**は、パスが*maxlen*文字より長いことを示します。 *Maxlen*が0以下の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、この関数は無効なパラメーターハンドラーを呼び出します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Getcwd**関数は、既定のドライブの現在の作業ディレクトリの完全なパスを取得し、*バッファー*に格納します。 Integer 引数*maxlen*は、パスの最大長を指定します。 パスの長さ (終端の null 文字を含む) が*maxlen*を超えると、エラーが発生します。 *Buffer*引数には**NULL**を指定できます。パスを格納するために、少なくともサイズが*maxlen* (必要な場合にのみ) のバッファーが**malloc**を使用して自動的に割り当てられます。 このバッファーは、後で**free**を呼び出して、 **_getcwd**の戻り値 (割り当てられたバッファーへのポインター) を渡すことによって解放できます。

**_getcwd**は、現在の作業ディレクトリのパスを表す文字列を返します。 現在の作業ディレクトリがルートの場合、文字列は円記号 () で終わり `\` ます。 現在の作業ディレクトリがルート以外のディレクトリの場合、文字列は、円記号ではなく、ディレクトリの名前で終わります。

**_wgetcwd**は **_getcwd**のワイド文字バージョンです。**_wgetcwd**の*バッファー*引数と戻り値はワイド文字列です。 **_wgetcwd**と **_getcwd**は同じように動作します。

**_DEBUG**と **_CRTDBG_MAP_ALLOC**が定義されている場合、 **_getcwd**と **_wgetcwd**への呼び出しは、メモリ割り当てのデバッグを可能にするために **_getcwd_dbg**と **_wgetcwd_dbg**の呼び出しに置き換えられます。 詳細については、「 [_getcwd_dbg, _wgetcwd_dbg](getcwd-dbg-wgetcwd-dbg.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd**|**_getcwd**|**_getcwd**|**_wgetcwd**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
[_chdir、_wchdir](chdir-wchdir.md)\
[_mkdir、_wmkdir](mkdir-wmkdir.md)\
[_rmdir、_wrmdir](rmdir-wrmdir.md)
