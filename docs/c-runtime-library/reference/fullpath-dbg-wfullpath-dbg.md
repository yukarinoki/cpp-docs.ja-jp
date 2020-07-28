---
title: _fullpath_dbg、_wfullpath_dbg
ms.date: 11/04/2016
api_name:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
ms.openlocfilehash: b728090c201c9c5d07cc2f1bec4f53b1682e0e92
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220679"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg、_wfullpath_dbg

[_Wfullpath _fullpath](fullpath-wfullpath.md)のバージョン。 **malloc**のデバッグバージョンを使用してメモリを割り当てます。

## <a name="syntax"></a>構文

```C
char *_fullpath_dbg(
   char *absPath,
   const char *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wfullpath_dbg(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*absPath*<br/>
絶対パス名または完全パス名を格納しているバッファーへのポインター、または**NULL**。

*relPath*<br/>
相対パス名。

*maxLength*<br/>
絶対パス名バッファー (*Abspath*) の最大長。 この長さは、 **_fullpath**の場合はバイト単位ですが、 **`wchar_t`** **_wfullpath**の場合はワイド文字 () になります。

*blockType*<br/>
要求されたメモリブロックの種類: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**。

*ファイル名*<br/>
割り当て操作を要求したソースファイルの名前へのポインターまたは**NULL**。

*linenumber*<br/>
割り当て操作が要求されたソースファイル内の行番号または**NULL**。

## <a name="return-value"></a>戻り値

各関数は、絶対パス名 (*Abspath*) を格納しているバッファーへのポインターを返します。 エラーが発生した場合 (たとえば、 *relPath*に渡された値に有効でないドライブ文字が含まれている場合や、見つからない場合、または作成された絶対パス名 (*abspath*) の長さが*maxLength*を超える場合)、関数は**NULL**を返します。

## <a name="remarks"></a>解説

**_Fullpath_dbg**関数と **_wfullpath_dbg**関数は **_fullpath**および **_wfullpath**と同じですが、 **_DEBUG**が定義されている場合、最初のパラメーターとして**NULL**が渡されると、これらの関数は**malloc**, **_malloc_dbg**のデバッグバージョンを使用してメモリを割り当てます。 **_Malloc_dbg**のデバッグ機能の詳細については、「 [_malloc_dbg](malloc-dbg.md)」を参照してください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、 **_CRTDBG_MAP_ALLOC**フラグを定義できます。 **_CRTDBG_MAP_ALLOC**が定義されている場合、 **_fullpath**と **_wfullpath**の呼び出しは、それぞれ **_fullpath_dbg**および **_wfullpath_dbg**に再マップされ、 *blocktype*が **_NORMAL_BLOCK**に設定されます。 したがって、ヒープブロックを **_CLIENT_BLOCK**としてマークする場合を除き、これらの関数を明示的に呼び出す必要はありません。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
