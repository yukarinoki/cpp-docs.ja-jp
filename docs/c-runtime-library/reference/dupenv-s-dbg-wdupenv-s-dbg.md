---
title: _dupenv_s_dbg、_wdupenv_s_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _dupenv_s_dbg
- _wdupenv_s_dbg
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
- _tdupenv_s_dbg
- _dupenv_s_dbg
- _wdupenv_s_dbg
dev_langs:
- C++
helpviewer_keywords:
- _tdupenv_s_dbg function
- dupenv_s_dbg function
- _wdupenv_s_dbg function
- environment variables
- tdupenv_s_dbg function
- wdupenv_s_dbg function
- _dupenv_s_dbg function
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef129cec096734c23e911a5dc77bf3bd0b2df03
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404306"
---
# <a name="dupenvsdbg-wdupenvsdbg"></a>_dupenv_s_dbg、_wdupenv_s_dbg

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

*バッファー*<br/>
変数の値を格納するバッファー。

*numberOfElements*<br/>
サイズ*バッファー*です。

*varname*<br/>
環境変数名。

*blockType*<br/>
要求されたメモリ ブロックの型: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
ソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
ソース ファイルの数の行または**NULL**です。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

これらの関数は、パラメーターを検証します。場合*バッファー*または*varname*は**NULL**、」の説明に従って、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数が設定**errno**に**EINVAL**返す**EINVAL**です。

これらの関数は、十分なメモリを割り当てることはできません、入れもの*バッファー*に**NULL**と*numberOfElements* 0 であり、戻り値に**ENOMEM**です。

## <a name="remarks"></a>コメント

**_Dupenv_s_dbg**と **_wdupenv_s_dbg**関数と同じ **_dupenv_s**と **_wdupenv_s**する点を除いて、 **_DEBUG**が定義されている場合、これらの関数を使用してデバッグ バージョンの[malloc](malloc.md)、 [_malloc_dbg](malloc-dbg.md)メモリ、環境変数の値を割り当てられません。 デバッグ機能について **_malloc_dbg**を参照してください[_malloc_dbg](malloc-dbg.md)です。

多くの場合、これらの関数を明示的に呼び出す必要はありません。 フラグを定義する代わりに、 **_CRTDBG_MAP_ALLOC**です。 ときに **_CRTDBG_MAP_ALLOC**が定義されているを呼び出す **_dupenv_s**と **_wdupenv_s**に再マップ **_dupenv_s_dbg**と **_wdupenv_s_dbg**をそれぞれに、 *blockType* 'éý' **_NORMAL_BLOCK**です。 したがって、必要はありません、ヒープ ブロックとしてマークする場合を除き、これらの関数を明示的に呼び出す **_CLIENT_BLOCK**です。 ブロック型の詳細については、[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)に関する記事をご覧ください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s_dbg**|**_dupenv_s_dbg**|**_dupenv_s_dbg**|**_wdupenv_s_dbg**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_dupenv_s_dbg**|\<crtdbg.h>|
|**_wdupenv_s_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[環境定数](../../c-runtime-library/environmental-constants.md)<br/>
[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md)<br/>
