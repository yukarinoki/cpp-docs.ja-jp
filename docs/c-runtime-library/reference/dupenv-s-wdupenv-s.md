---
title: _dupenv_s、_wdupenv_s
ms.date: 4/2/2020
api_name:
- _dupenv_s
- _wdupenv_s
- _o__dupenv_s
- _o__wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
ms.openlocfilehash: f65f1da3e8cef077df04d0bdb7eb2aaf75afd9fa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348057"
---
# <a name="_dupenv_s-_wdupenv_s"></a>_dupenv_s、_wdupenv_s

現在の環境から値を取得します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _dupenv_s(
   char **buffer,
   size_t *numberOfElements,
   const char *varname
);
errno_t _wdupenv_s(
   wchar_t **buffer,
   size_t *numberOfElements,
   const wchar_t *varname
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
変数の値を格納するバッファー。

*要素の数*<br/>
*バッファ*のサイズ :

*ヴァルネーム*<br/>
環境変数名。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

これらの関数は、パラメーターを検証します。*buffer*または*varname*が**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

これらの関数が十分なメモリを割り当てられない場合は、*バッファ*を**NULL**に設定し、*数の要素を*0 に設定し **、ENOMEM**を返します。

## <a name="remarks"></a>解説

**_dupenv_s**関数は環境変数のリストから*varname*を検索します。 変数が見つかった場合 **、_dupenv_s**はバッファを割り当て、変数の値をバッファにコピーします。 バッファーのアドレスと長さは、*バッファー*と*数 OfElements*で返されます。 バッファ自体を割り当てることで **、_dupenv_sgetenv_s**に代わるより便利な代替手段[_wgetenv_s](getenv-s-wgetenv-s.md)提供します。

> [!NOTE]
> [free](free.md) の呼び出しによるメモリの解放は、呼び出し元プログラムが行います。

変数が見つからない場合 *、buffer*が**NULL**に設定され *、numberOfElements*は 0 に設定され、この状況はエラー条件と見なされないため、戻り値は 0 になります。

バッファのサイズに興味がない場合は、*数値の要素*に**NULL**を渡すことができます。

**_dupenv_s**は、Windows オペレーティング システムでは大文字と小文字が区別されません。 **_dupenv_s**は、グローバル変数 **_environ**が指す環境のコピーを使用して環境にアクセスします。 **_environ**の詳細については[、getenv_s](getenv-s-wgetenv-s.md)の_wgetenv_sの解説を参照してください。

*バッファー*内の値は、環境変数の値のコピーです。変更しても環境に影響はありません。 環境変数の値を変更するには、[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md) 関数を使います。

**_wdupenv_s**はワイド文字の **_dupenv_s**です。**_wdupenv_s**の引数はワイド文字列です。 **_wenviron**グローバル変数は、 _environ のワイド文字バージョン**です**。 **_wenviron**の詳細については[、getenv_sの「解説」_wgetenv_s](getenv-s-wgetenv-s.md)を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_dupenv_s.c
#include  <stdlib.h>

int main( void )
{
   char *pValue;
   size_t len;
   errno_t err = _dupenv_s( &pValue, &len, "pathext" );
   if ( err ) return -1;
   printf( "pathext = %s\n", pValue );
   free( pValue );
   err = _dupenv_s( &pValue, &len, "nonexistentvariable" );
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
[_dupenv_s_dbg、_wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md)<br/>
