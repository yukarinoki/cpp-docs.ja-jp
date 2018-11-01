---
title: _tempnam_dbg、_wtempnam_dbg
ms.date: 11/04/2016
apiname:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
ms.openlocfilehash: 804c8ad1f17c6ee1df563cafc69ee7aef494d1cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596458"
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg、_wtempnam_dbg

関数バージョン[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)のデバッグ バージョンを使用する**malloc**、 **_malloc_dbg**します。

## <a name="syntax"></a>構文

```C
char *_tempnam_dbg(
   const char *dir,
   const char *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wtempnam_dbg(
   const wchar_t *dir,
   const wchar_t *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*dir*<br/>
TMP 環境変数がない場合、または TMP が有効なディレクトリではない場合にファイル名で使用されるパス。

*prefix*<br/>
によって返された名前を付けたとなる文字列 **_tempnam**します。

*blockType*<br/>
要求されたメモリ ブロックの種類: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**します。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
割り当て操作が要求されたソース ファイルの数の行または**NULL**します。

## <a name="return-value"></a>戻り値

各関数は、生成された名前にポインターを返しますまたは**NULL**障害が発生した場合。 TMP 環境変数および指定されている、無効なディレクトリ名がある場合、エラーが発生することが、 *dir*パラメーター。

> [!NOTE]
> **無料**(または**free_dbg**) によって割り当てられたポインターに対して呼び出される必要がありますは **_tempnam_dbg**と **_wtempnam_dbg**します。

## <a name="remarks"></a>Remarks

**_Tempnam_dbg**と **_wtempnam_dbg**関数と同じ **_tempnam**と **_wtempnam**する点を除いて、 **_DEBUG**が定義されている場合、これらの関数でのデバッグ バージョンを使用**malloc**と **_malloc_dbg**場合に、メモリを割り当て、 **NULL**は最初のパラメーターとして渡されます。 詳細については、「[_malloc_dbg](malloc-dbg.md)」をご覧ください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 フラグを定義する代わりに、 **_CRTDBG_MAP_ALLOC**します。 ときに **_CRTDBG_MAP_ALLOC**が定義されている、呼び出し **_tempnam**と **_wtempnam**にマップし直され **_tempnam_dbg**と **_wtempnam_dbg**をそれぞれで、 *blockType*設定 **_NORMAL_BLOCK**します。 したがって、としてヒープ ブロックをマークする場合、これらの関数を明示的に呼び出す必要はない **_CLIENT_BLOCK**します。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_tempnam_dbg**、 **_wtempnam_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
