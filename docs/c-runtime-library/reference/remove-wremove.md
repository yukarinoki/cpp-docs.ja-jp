---
description: 詳細については、「remove、_wremove」を参照してください。
title: remove、_wremove
ms.date: 4/2/2020
api_name:
- _wremove
- remove
- _o__wremove
- _o_remove
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- remove
- _wremove
- _tremove
helpviewer_keywords:
- tremove function
- _wremove function
- files [C++], deleting
- _tremove function
- files [C++], removing
- wremove function
- remove function
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
ms.openlocfilehash: c17215803e03e1e59df86b6049249a824d5615c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322512"
---
# <a name="remove-_wremove"></a>remove、_wremove

ファイルを削除します。

## <a name="syntax"></a>構文

```C
int remove(
   const char *path
);
int _wremove(
   const wchar_t *path
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
削除されるファイルのパス。

## <a name="return-value"></a>戻り値

ファイルが正常に削除された場合、これらの関数はそれぞれ 0 を返します。 それ以外の場合は、-1 を返し、 **errno** を **EACCES** に設定して、パスが読み取り専用ファイルを指定しているか、ディレクトリを指定しているか、ファイルが開いていることを示します。または、ファイル名またはパスが見つからなかったことを示すために **ENOENT** を設定します。

これらのリターンコードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 」を参照してください。

## <a name="remarks"></a>解説

**remove** 関数は、*path* によって指定されたファイルを削除します。 **_wremove** は **_remove** のワイド文字バージョンです。**_wremove** の *パス* 引数は、ワイド文字列です。 **_wremove** と **_remove** は同じように動作します。 ファイルを削除する前に、ファイルへのすべてのハンドルを閉じる必要があります。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tremove**|**remove**|**remove**|**_wremove**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**remove**|\<stdio.h> または \<io.h>|
|**_wremove**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_remove.c
/* This program uses remove to delete crt_remove.txt */

#include <stdio.h>

int main( void )
{
   if( remove( "crt_remove.txt" ) == -1 )
      perror( "Could not delete 'CRT_REMOVE.TXT'" );
   else
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );
}
```

### <a name="input-crt_removetxt"></a>入力: crt_remove.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>出力例

```Output
Deleted 'CRT_REMOVE.TXT'
```

## <a name="see-also"></a>関連項目

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[_unlink、_wunlink](unlink-wunlink.md)<br/>
