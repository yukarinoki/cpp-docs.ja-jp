---
description: '詳細については、次を参照してください: _dupenv_s_dbg、_wdupenv_s_dbg'
title: _dupenv_s_dbg、_wdupenv_s_dbg
ms.date: 11/04/2016
api_name:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
ms.openlocfilehash: a12e5adc55cd69b8336b3f9f50d982f80ec1b070
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332897"
---
# <a name="_dupenv_s_dbg-_wdupenv_s_dbg"></a>_dupenv_s_dbg、_wdupenv_s_dbg

現在の環境から値を取得します。  追加のデバッグ情報を提供するために [_malloc_dbg](malloc-dbg.md) でメモリを割り当てる、[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md) のバージョン。

## <a name="syntax"></a>構文

```C
errno_t _dupenv_s_dbg(
   char **buffer,
   size_t *numberOfElements,
   const char *varname,
   int blockType,
   const char *filename,
   int linenumber
);
errno_t _wdupenv_s_dbg(
   wchar_t **buffer,
   size_t * numberOfElements,
   const wchar_t *varname,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*格納*<br/>
変数の値を格納するバッファー。

*numberOfElements*<br/>
*バッファー* のサイズ。

*varname*<br/>
環境変数名。

*blockType*<br/>
要求されたメモリブロックの種類: **_CLIENT_BLOCK** または **_NORMAL_BLOCK**。

*filename*<br/>
ソースファイルの名前へのポインター、または **NULL**。

*linenumber*<br/>
ソースファイル内の行番号または **NULL**。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

これらの関数は、パラメーターを検証します。 *buffer* または *varname* が **NULL** の場合、「 [パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、関数は **errno** を **einval** に設定し、 **einval** を返します。

これらの関数が十分なメモリを割り当てられない場合、 *buffer* を **NULL** に設定し、 *numberofelements* を0に設定して、 **ENOMEM** を返します。

## <a name="remarks"></a>解説

**_Dupenv_s_dbg** 関数と **_wdupenv_s_dbg** 関数は **_dupenv_s** および **_wdupenv_s** と同じですが、 **_DEBUG** が定義されている場合、これらの関数は、デバッグバージョンの [malloc](malloc.md)、 [_malloc_dbg](malloc-dbg.md)を使用して、環境変数の値にメモリを割り当てます。 **_Malloc_dbg** のデバッグ機能の詳細については、「 [_malloc_dbg](malloc-dbg.md)」を参照してください。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 代わりに、フラグ **_CRTDBG_MAP_ALLOC** を定義できます。 **_CRTDBG_MAP_ALLOC** が定義されている場合、 **_dupenv_s** と **_wdupenv_s** の呼び出しは、それぞれ **_dupenv_s_dbg** および **_wdupenv_s_dbg** に再マップされ、 *blocktype* が **_NORMAL_BLOCK** に設定されます。 したがって、ヒープブロックを **_CLIENT_BLOCK** としてマークする場合を除き、これらの関数を明示的に呼び出す必要はありません。 ブロック型の詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<crtdbg.h>|
|**_wdupenv_s_dbg**|\<crtdbg.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_dupenv_s_dbg.c
#include  <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",
      _NORMAL_BLOCK, __FILE__, __LINE__ );
   if ( err ) return -1;
   printf( "nonexistentvariable = %s\n", pValue );
   free( pValue ); // It's OK to call free with NULL
}
```

```Output
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl
nonexistentvariable = (null)
```

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[環境定数](../../c-runtime-library/environmental-constants.md)<br/>
[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md)<br/>
