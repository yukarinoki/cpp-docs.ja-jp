---
description: '詳細については、次を参照してください: _unlink、_wunlink'
title: _unlink、_wunlink
ms.date: 4/2/2020
api_name:
- _unlink
- _wunlink
- _o__unlink
- _o__wunlink
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
- _tunlink
- _unlink
- wunlink
- _wunlink
helpviewer_keywords:
- files [C++], deleting
- _wunlink function
- wunlink function
- unlink function
- _unlink function
- tunlink function
- files [C++], removing
- _tunlink function
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
ms.openlocfilehash: 742df45211b6e19314a3b3f89880d7f2cd83fb2f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205149"
---
# <a name="_unlink-_wunlink"></a>_unlink、_wunlink

ファイルを削除します。

## <a name="syntax"></a>構文

```C
int _unlink(
   const char *filename
);
int _wunlink(
   const wchar_t *filename
);
```

### <a name="parameters"></a>パラメーター

*filename*<br/>
削除するファイルの名前。

## <a name="return-value"></a>戻り値

正常に終了した場合、これらの各関数は 0 を返します。 それ以外の場合、この関数は-1 を返し、 **errno** を **EACCES** に設定します。これは、パスが読み取り専用のファイルまたはディレクトリを指定しているか、ファイルまたはパスが見つからないことを示す **ENOENT** に設定されていることを意味します。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Unlink** 関数は、 *filename* によって指定されたファイルを削除します。 **_wunlink** は **_unlink** のワイド文字バージョンです。**_wunlink** する *filename* 引数は、ワイド文字列です。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tunlink**|**_unlink**|**_unlink**|**_wunlink**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_unlink**|\<io.h> および \<stdio.h>|
|**_wunlink**|\<io.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="code-example"></a>コード例

このプログラムは、_unlink を使用して CRT_UNLINK.TXT を削除します。

```C
// crt_unlink.c

#include <stdio.h>

int main( void )
{
   if( _unlink( "crt_unlink.txt" ) == -1 )
      perror( "Could not delete 'CRT_UNLINK.TXT'" );
   else
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );
}
```

### <a name="input-crt_unlinktxt"></a>入力: crt_unlink.txt

```Input
This file will be deleted.
```

### <a name="sample-output"></a>出力例

```Output
Deleted 'CRT_UNLINK.TXT'
```

## <a name="see-also"></a>関連項目

[ファイルの処理](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[remove、_wremove](remove-wremove.md)<br/>
