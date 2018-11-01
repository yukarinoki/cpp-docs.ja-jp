---
title: _strdup_dbg、_wcsdup_dbg
ms.date: 11/04/2016
apiname:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
ms.openlocfilehash: 3092c27df1e39c7b719f6e7037efa202d29c9e81
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50531158"
---
# <a name="strdupdbg-wcsdupdbg"></a>_strdup_dbg、_wcsdup_dbg

バージョンの[_strdup、_wcsdup](strdup-wcsdup-mbsdup.md)のデバッグ バージョンを使用する**malloc**します。

## <a name="syntax"></a>構文

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*strSource*<br/>
NULL で終わる元の文字列。

*blockType*<br/>
要求されたメモリ ブロックの種類: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**します。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
割り当て操作が要求されたソース ファイルの数の行または**NULL**します。

## <a name="return-value"></a>戻り値

これらの関数の各コピーされた文字列の格納場所にポインターを返しますまたは**NULL**場合、記憶域を割り当てることができません。

## <a name="remarks"></a>Remarks

**_Strdup_dbg**と **_wcsdup_dbg**関数と同じ **_strdup**と **_wcsdup**する点を除いて、 **_デバッグ**が定義されている場合、これらの関数でのデバッグ バージョンを使用**malloc**、 **_malloc_dbg**、複製された文字列のメモリを割り当てられません。 デバッグ機能について **_malloc_dbg**を参照してください[_malloc_dbg](malloc-dbg.md)します。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 フラグを定義する代わりに、 **_CRTDBG_MAP_ALLOC**します。 ときに **_CRTDBG_MAP_ALLOC**が定義されている、呼び出し **_strdup**と **_wcsdup**にマップし直され **_strdup_dbg**と **_wcsdup_dbg**をそれぞれで、 *blockType*設定 **_NORMAL_BLOCK**します。 したがって、としてヒープ ブロックをマークする場合、これらの関数を明示的に呼び出す必要はない **_CLIENT_BLOCK**します。 ブロック型の詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_strdup_dbg**、 **_wcsdup_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのデバッグ バージョン。

## <a name="see-also"></a>関連項目

[文字列操作](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup、_wcsdup、_mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
