---
title: _dupenv_s、_wdupenv_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _dupenv_s
- _wdupenv_s
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
- api-ms-win-crt-environment-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tdupenv_s
- _dupenv_s
- wdupenv_s
- dupenv_s
- _tdupenv_s
- _wdupenv_s
dev_langs:
- C++
helpviewer_keywords:
- _dupenv_s function
- _tdupenv_s function
- _wdupenv_s function
- environment variables
- wdupenv_s function
- dupenv_s function
- tdupenv_s function
ms.assetid: b729ecc2-a31d-4ccf-92a7-5accedb8f8c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5a918b866b0b43fb0e6b31e2deb5d9861dabe9a2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="dupenvs-wdupenvs"></a>_dupenv_s、_wdupenv_s

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

*numberOfElements*<br/>
サイズ*バッファー*です。

*varname*<br/>
環境変数名。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

これらの関数は、パラメーターを検証します。場合*バッファー*または*varname*は**NULL**、」の説明に従って、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、この関数が設定**errno**に**EINVAL**返す**EINVAL**です。

これらの関数は、十分なメモリを割り当てることはできません、入れもの*バッファー*に**NULL**と*numberOfElements* 0 であり、戻り値に**ENOMEM**です。

## <a name="remarks"></a>コメント

**_Dupenv_s**関数は、環境変数の一覧を検索*varname*です。 見つかった場合は、変数は、 **_dupenv_s**バッファーを割り当てられ、バッファーに変数の値をコピーします。 バッファーのアドレスと長さがで返される*バッファー*と*numberOfElements*です。 自体は、バッファーを割り当てることによって **_dupenv_s**する方が便利な代替手段[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)です。

> [!NOTE]
> [free](free.md) の呼び出しによるメモリの解放は、呼び出し元プログラムが行います。

変数が見つからない場合、し*バッファー*に設定されている**NULL**、 *numberOfElements*を 0 に設定されていると、このような状況がエラーであると見なされないために、戻り値は 0条件です。

バッファーのサイズを考慮していない場合は、渡す**NULL**の*numberOfElements*です。

**_dupenv_s** Windows オペレーティング システムで大文字小文字は区別されません。 **_dupenv_s**グローバル変数が指す環境のコピーを使用して **_environ**環境にアクセスします。 「解説」を参照してください[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)のについて **_environ**です。

値*バッファー*環境変数の値のコピーであることを変更しても環境への影響はありません。 環境変数の値を変更するには、[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md) 関数を使います。

**_wdupenv_s**のワイド文字バージョンは、 **_dupenv_s**; の引数 **_wdupenv_s**ワイド文字列です。 **_Wenviron**グローバル変数のワイド文字バージョンは、 **_environ**です。 「解説」を参照してください[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)について **_wenviron**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tdupenv_s**|**_dupenv_s**|**_dupenv_s**|**_wdupenv_s**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_dupenv_s**|\<stdlib.h>|
|**_wdupenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[環境定数](../../c-runtime-library/environmental-constants.md)<br/>
[_dupenv_s_dbg、_wdupenv_s_dbg](dupenv-s-dbg-wdupenv-s-dbg.md)<br/>
[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)<br/>
[_putenv_s、_wputenv_s](putenv-s-wputenv-s.md)<br/>
