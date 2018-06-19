---
title: _tempnam_dbg、_wtempnam_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8509d9f4b8be5771abc7dfb3d4deacc9ae61494
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412050"
---
# <a name="tempnamdbg-wtempnamdbg"></a>_tempnam_dbg、_wtempnam_dbg

関数バージョン[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)のデバッグ バージョンを使用する**malloc**、 **_malloc_dbg**です。

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
によって返された名前の前に付けられる文字列 **_tempnam**です。

*blockType*<br/>
要求されたメモリ ブロックの型: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
割り当て操作が要求されたソース ファイルの数の行または**NULL**です。

## <a name="return-value"></a>戻り値

各関数が生成されるファイル名へのポインターを返しますまたは**NULL**障害が発生した場合。 TMP 環境変数で指定された無効なディレクトリ名がある場合、エラーが発生することができます、 *dir*パラメーター。

> [!NOTE]
> **空き**(または**free_dbg**) によって割り当てられたポインターに対して呼び出される必要は **_tempnam_dbg**と **_wtempnam_dbg**です。

## <a name="remarks"></a>コメント

**_Tempnam_dbg**と **_wtempnam_dbg**関数と同じ **_tempnam**と **_wtempnam**する点を除いて、 **_DEBUG**が定義されている場合、これらの関数を使用してデバッグ バージョンの**malloc**と **_malloc_dbg**、メモリを割り当てる場合**NULL**は最初のパラメーターとして渡されます。 詳細については、「[_malloc_dbg](malloc-dbg.md)」をご覧ください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 フラグを定義する代わりに、 **_CRTDBG_MAP_ALLOC**です。 ときに **_CRTDBG_MAP_ALLOC**が定義されているを呼び出す **_tempnam**と **_wtempnam**に再マップ **_tempnam_dbg**と **_wtempnam_dbg**をそれぞれに、 *blockType* 'éý' **_NORMAL_BLOCK**です。 したがって、必要はありません、ヒープ ブロックとしてマークする場合を除き、これらの関数を明示的に呼び出す **_CLIENT_BLOCK**です。 詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_tempnam_dbg**、 **_wtempnam_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[_tempnam、_wtempnam、tmpnam、_wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
