---
title: _fullpath_dbg、_wfullpath_dbg
ms.date: 11/04/2016
apiname:
- _wfullpath_dbg
- _fullpath_dbg
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
ms.openlocfilehash: b84c5b77d0a9bfb298d4c597e372cd39a92441f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488011"
---
# <a name="fullpathdbg-wfullpathdbg"></a>_fullpath_dbg、_wfullpath_dbg

バージョンの[_fullpath、_wfullpath](fullpath-wfullpath.md)のデバッグ バージョンを使用する**malloc**メモリを割り当てることです。

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
絶対または完全パス名を格納するバッファーへのポインターまたは**NULL**します。

*relPath*<br/>
相対パス名。

*MaxLength*<br/>
絶対パス名のバッファーの最大長 (*absPath*)。 この長さはバイト単位、 **_fullpath**がワイド文字 (**wchar_t**) の **_wfullpath**します。

*blockType*<br/>
要求されたメモリ ブロックの種類: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**します。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
割り当て操作が要求されたソース ファイル内の番号を行または**NULL**します。

## <a name="return-value"></a>戻り値

各関数の絶対パス名を格納するバッファーへのポインターを返します (*absPath*)。 エラーがある場合 (値が渡された場合など、 *relPath*が正しくないか、見つからないドライブ文字が含まれます場合、または作成された絶対パス名の長さ (*absPath*) より大きい*maxLength*) を返します**NULL**します。

## <a name="remarks"></a>Remarks

**_Fullpath_dbg**と **_wfullpath_dbg**関数と同じ **_fullpath**と **_wfullpath**する点を除いて、 **_DEBUG**が定義されている場合、これらの関数でのデバッグ バージョンを使用**malloc**、 **_malloc_dbg**場合に、メモリを割り当て、 **NULL**が渡されます最初のパラメーター。 デバッグ機能について **_malloc_dbg**を参照してください[_malloc_dbg](malloc-dbg.md)します。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、定義、 **_CRTDBG_MAP_ALLOC**フラグ。 ときに **_CRTDBG_MAP_ALLOC**が定義されている、呼び出し **_fullpath**と **_wfullpath**にマップし直され **_fullpath_dbg**と **_wfullpath_dbg**をそれぞれで、 *blockType*設定 **_NORMAL_BLOCK**します。 したがって、としてヒープ ブロックをマークする場合、これらの関数を明示的に呼び出す必要はない **_CLIENT_BLOCK**します。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
