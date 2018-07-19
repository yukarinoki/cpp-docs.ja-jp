---
title: _getdcwd_dbg、_wgetdcwd_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
apitype: DLLExport
f1_keywords:
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
dev_langs:
- C++
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f68fc4fe1c19204433e8f5c9b6c7991d8f7f90e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402827"
---
# <a name="getdcwddbg-wgetdcwddbg"></a>_getdcwd_dbg、_wgetdcwd_dbg

[_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md) 関数のデバッグ バージョン (デバッグ中のみ使用可能)。

## <a name="syntax"></a>構文

```C
char *_getdcwd_dbg(
   int drive,
   char *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wgetdcwd_dbg(
   int drive,
   wchar_t *buffer,
   int maxlen,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*ドライブ*<br/>
ディスク ドライブの名前。

*バッファー*<br/>
パスの格納場所。

*maxlen*<br/>
文字数でパスの最大長: **char**の **_getdcwd_dbg**と**wchar_t**の **_wgetdcwd_dbg**です。

*blockType*<br/>
要求されたメモリ ブロックの型: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
割り当て操作が要求されたソース ファイルの数の行または**NULL**です。

## <a name="return-value"></a>戻り値

ポインターを返します*バッファー*です。 A **NULL** 、エラーを返すと**errno**に設定されているいずれかの**ENOMEM**に割り当てる十分なメモリがあることを示す*maxlen*バイト数 (ときに、 **NULL**として引数が指定されている*バッファー*)、または**ERANGE**、パスがより長いことを示す*maxlen*文字です。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**_Getdcwd_dbg**と **_wgetdcwd_dbg**関数と同じ **_getdcwd**と **_wgetdcwd**する点を除いて、 **_DEBUG**が定義されている場合、これらの関数を使用してデバッグ バージョンの**malloc**と **_malloc_dbg**メモリを割り当てる場合**NULL**が渡されますとして、*バッファー*パラメーター。 詳細については、「[_malloc_dbg](malloc-dbg.md)」をご覧ください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、定義することができます、 **_CRTDBG_MAP_ALLOC**フラグ。 ときに **_CRTDBG_MAP_ALLOC**が定義されているを呼び出す **_getdcwd**と **_wgetdcwd**に再マップ **_getdcwd_dbg**と **_wgetdcwd_dbg**をそれぞれに、 *blockType* 'éý' **_NORMAL_BLOCK**です。 したがって、必要はありません、ヒープ ブロックとしてマークする場合を除き、これらの関数を明示的に呼び出す **_CLIENT_BLOCK**です。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h>|
|**_wgetdcwd_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
