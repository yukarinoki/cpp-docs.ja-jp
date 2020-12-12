---
description: '詳細については、次を参照してください: _getdcwd_dbg、_wgetdcwd_dbg'
title: _getdcwd_dbg、_wgetdcwd_dbg
ms.date: 11/04/2016
api_name:
- _getdcwd_dbg
- _wgetdcwd_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _getdcwd_dbg
- getdcwd_dbg
- _wgetdcwd_dbg
- wgetdcwd_dbg
helpviewer_keywords:
- working directory
- _getdcwd_dbg function
- wgetdcwd_dbg function
- current working directory
- getdcwd_dbg function
- _wgetdcwd_dbg function
- directories [C++], current working
ms.assetid: 266bf6f0-0417-497f-963d-2e0f306d9385
ms.openlocfilehash: b46847662aca04c07d6bdae42490d8a7d2ffe2cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256589"
---
# <a name="_getdcwd_dbg-_wgetdcwd_dbg"></a>_getdcwd_dbg、_wgetdcwd_dbg

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

*駆動*<br/>
ディスク ドライブの名前。

*格納*<br/>
パスの格納場所。

*maxlen*<br/>
文字数でのパスの最大長 **`char`** : **_getdcwd_dbg** の場合は、 **`wchar_t`** **_wgetdcwd_dbg** の場合は。

*blockType*<br/>
要求されたメモリブロックの種類: **_CLIENT_BLOCK** または **_NORMAL_BLOCK**。

*filename*<br/>
割り当て操作を要求したソースファイルの名前へのポインターまたは **NULL**。

*linenumber*<br/>
割り当て操作が要求されたソースファイル内の行番号または **NULL**。

## <a name="return-value"></a>戻り値

*バッファー* へのポインターを返します。 **Null** の戻り値はエラーを示し、 **errno** は **ENOMEM** に設定されます。これは、( **NULL** 引数が *バッファー* として指定されている場合) *maxlen* バイトを割り当てるのに十分なメモリがないことを示し、 **ERANGE** は、パスが *maxlen* 文字より長いことを示します。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Getdcwd_dbg** 関数と **_wgetdcwd_dbg** 関数は **_getdcwd** および **_wgetdcwd** と同じですが、 **_DEBUG** が定義されている場合、これらの関数は、*バッファー* パラメーターとして **NULL** が渡された場合に、 **malloc** および **_malloc_dbg** のデバッグバージョンを使用してメモリを割り当てます。 詳細については、「[_malloc_dbg](malloc-dbg.md)」をご覧ください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、 **_CRTDBG_MAP_ALLOC** フラグを定義できます。 **_CRTDBG_MAP_ALLOC** が定義されている場合、 **_getdcwd** と **_wgetdcwd** の呼び出しは、それぞれ **_getdcwd_dbg** および **_wgetdcwd_dbg** に再マップされ、 *blocktype* が **_NORMAL_BLOCK** に設定されます。 したがって、ヒープブロックを **_CLIENT_BLOCK** としてマークする場合を除き、これらの関数を明示的に呼び出す必要はありません。 詳細については、「 [デバッグヒープ上のブロックの種類](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_dbg**|**_getdcwd_dbg**|**_getdcwd_dbg**|**_wgetdcwd_dbg**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_getdcwd_dbg**|\<crtdbg.h>|
|**_wgetdcwd_dbg**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[_getdcwd、_wgetdcwd](getdcwd-wgetdcwd.md)<br/>
[ディレクトリコントロール](../../c-runtime-library/directory-control.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
