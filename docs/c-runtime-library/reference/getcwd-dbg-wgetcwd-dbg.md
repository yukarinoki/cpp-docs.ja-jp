---
title: _getcwd_dbg、_wgetcwd_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wgetcwd_dbg
- _getcwd_dbg
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
apitype: DLLExport
f1_keywords:
- _getcwd_dbg
- _wgetcwd_dbg
- getcwd_dbg
- wgetcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- wgetcwd_dbg function
- working directory
- _getcwd_dbg function
- getcwd_dbg function
- current working directory
- _wgetcwd_dbg function
- directories [C++], current working
ms.assetid: 8d5d151f-d844-4aa6-a28c-1c11a22dc00d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b4124b5825f27ec26afdb40f0ccc9e4de4ed087
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401556"
---
# <a name="getcwddbg-wgetcwddbg"></a>_getcwd_dbg、_wgetcwd_dbg

[_getcwd、_wgetcwd](getcwd-wgetcwd.md) 関数のデバッグ バージョン (デバッグ中のみ使用可能)。

## <a name="syntax"></a>構文

```C
char *_getcwd_dbg(
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetcwd_dbg(
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
パスの格納場所。

*maxlen*<br/>
文字数でパスの最大長: **char**の **_getcwd_dbg**と**wchar_t**の **_wgetcwd_dbg**です。

*blockType*<br/>
要求されたメモリ ブロックの型: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
割り当て操作が要求されたソース ファイルの数の行または**NULL**です。

## <a name="return-value"></a>戻り値

ポインターを返します*バッファー*です。 A **NULL** 、エラーを返すと**errno**に設定されているいずれかの**ENOMEM**に割り当てる十分なメモリがあることを示す*maxlen*バイト数 (ときに、 **NULL**として引数が指定されている*バッファー*)、または**ERANGE**、パスがより長いことを示す*maxlen*文字です。

詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_Getcwd_dbg**と **_wgetcwd_dbg**関数と同じ **_getcwd**と **_wgetcwd**する点を除いて、 **_デバッグ**が定義されている場合、これらの関数を使用してデバッグ バージョンの**malloc**と **_malloc_dbg**メモリを割り当てる場合**NULL**として渡される、最初のパラメーター。 詳細については、「[_malloc_dbg](malloc-dbg.md)」をご覧ください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、定義することができます、 **_CRTDBG_MAP_ALLOC**フラグ。 ときに **_CRTDBG_MAP_ALLOC**が定義されているを呼び出す **_getcwd**と **_wgetcwd**に再マップ **_getcwd_dbg**と **_wgetcwd_dbg**をそれぞれに、 *blockType* 'éý' **_NORMAL_BLOCK**です。 したがって、必要はありません、ヒープ ブロックとしてマークする場合を除き、これらの関数を明示的に呼び出す **_CLIENT_BLOCK**です。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

## <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetcwd_dbg**|**_getcwd_dbg**|**_getcwd_dbg**|**_wgetcwd_dbg**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getcwd_dbg**|\<crtdbg.h>|
|**_wgetcwd_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_getcwd、_wgetcwd](getcwd-wgetcwd.md)<br/>
[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
