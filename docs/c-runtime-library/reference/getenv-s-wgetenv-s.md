---
title: getenv_s, _wgetenv_s
description: Microsoft C ランタイム ライブラリgetenv_sと_wgetenv_s関数について説明します。
ms.date: 4/2/2020
api_name:
- getenv_s
- _wgetenv_s
- _o__wgetenv_s
- _o_getenv_s
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
- getenv_s
- _tgetenv_s
- _wgetenv_s
helpviewer_keywords:
- _tgetenv_s function
- wgetenv_s function
- _wgetenv_s function
- getenv_s function
- environment variables
- tgetenv_s function
ms.assetid: c3ae1ffe-d4cd-4bae-bcb1-3afa754c613a
no-loc:
- getenv_s
- _wgetenv_s
- _putenv_s
- main
- wmain
- errno
- EINVAL
- ERANGE
- _environ
- _wenviron
- _putenv
- _wputenv
- _tgetenv_s
- _tzset
- _dupenv_s
- _wdupenv_s
ms.openlocfilehash: 17c4e001f7f4637f6f66f218c94378368976901f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344273"
---
# <a name="getenv_s-_wgetenv_s"></a>getenv_s、_wgetenv_s

現在の環境から値を取得します。 これらの [getenv および _wgetenvgets](getenv-wgetenv.md) のバージョンは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」(CRT のセキュリティ機能) で説明されているように、セキュリティが強化されています。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t getenv_s(
   size_t *pReturnValue,
   char* buffer,
   size_t numberOfElements,
   const char *varname
);
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t *buffer,
   size_t numberOfElements,
   const wchar_t *varname
);
template <size_t size>
errno_t getenv_s(
   size_t *pReturnValue,
   char (&buffer)[size],
   const char *varname
); // C++ only
template <size_t size>
errno_t _wgetenv_s(
   size_t *pReturnValue,
   wchar_t (&buffer)[size],
   const wchar_t *varname
); // C++ only
```

### <a name="parameters"></a>パラメーター

*値を返します。*<br/>
必要なバッファー サイズ。変数が見つからない場合は 0。

*バッファー*<br/>
環境変数の値を格納するバッファー。

*要素の数*<br/>
*バッファ*のサイズ :

*ヴァルネーム*<br/>
環境変数名。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合は失敗に関するエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*値を返します。*|*バッファー*|*要素の数*|*ヴァルネーム*|戻り値|
|--------------------|--------------|------------------------|---------------|------------------|
|**NULL**|any|any|any|**Einval**|
|any|**NULL**|>0|any|**Einval**|
|any|any|any|**NULL**|**Einval**|

これらのいずれかのエラー条件の場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

また、バッファが小さすぎる場合、これらの関数は**ERANGE**を返します。 無効なパラメーター ハンドラーは呼び出されません。 必要なバッファ サイズを*pReturnValue*に書き出し、それによって、より大きなバッファを使用してプログラムが関数を再度呼び出すことを可能にします。

## <a name="remarks"></a>解説

**getenv_s**関数は環境変数のリストから*varname*を検索します。 **getenv_s**は、Windows オペレーティング システムでは大文字と小文字が区別されません。 **getenv_s**と[_putenv_s](putenv-s-wputenv-s.md)は、環境にアクセスするために、グローバル変数 **_environ**によって指されている環境のコピーを使用します。 **getenv_s**は、ランタイム ライブラリにアクセスできるデータ構造に対してのみ動作し、オペレーティング システムによってプロセス用に作成された環境 "セグメント" では動作しません。 したがって[、main](../../cpp/main-function-command-line-args.md)または[wmain](../../cpp/main-function-command-line-args.md)に対して*envp*引数を使用するプログラムは、無効な情報を取得する可能性があります。

**_wgetenv_s**はワイド文字の**getenv_s**です。_wgetenv_sの引数と戻り**値はワイド**文字列です。 **_wenviron**グローバル変数は、 _environ のワイド文字バージョン**です**。

MBCS プログラム (例えば、SBCS ASCII プログラム) では、環境がマルチバイト文字ストリングで構成されているため **、_wenviron**は最初は**NULL**です。 次に[、_wputenv](putenv-wputenv.md)への最初の呼び出し、または **_wgetenv_s**への最初の呼び出しで 、(MBCS) 環境が既に存在する場合は、対応するワイド文字ストリング環境が作成され **、_wenviron**が指す。

同様に、Unicode (**_wmain**) プログラムでは、環境がワイド文字ストリングで構成されているため **、_environ**は最初は**NULL**です。 次に[、_putenv](putenv-wputenv.md)への最初の呼び出しで、または (Unicode) 環境が既に存在する場合に**getenv_s**する最初の呼び出しで、対応する MBCS 環境が作成され **、_environ**によってポイントされます。

2 つの環境のコピー (MBCS および Unicode) がプログラムに同時に存在する場合、ランタイム システムは、両方のコピーを保持する必要があるため、実行時間が長くなります。 たとえば、 **_putenv**呼び出すと **、_wputenv**の呼び出しも自動的に実行され、2 つの環境文字列が対応します。

> [!CAUTION]
> まれに、ランタイム システムが Unicode 環境とマルチバイト環境の両方を保持している場合、これら 2 つの環境が正確に対応しないことがあります。 これは、一意のマルチバイト文字列はすべて一意の Unicode 文字列に対応していますが、一意の Unicode 文字列は必ずしも一意のマルチバイト文字列に対応していないために発生します。 詳細については、「[_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」をご覧ください。

> [!NOTE]
> **_putenv_s**と **_getenv_s**関数ファミリはスレッドセーフではありません。 **_getenv_s**文字列を変更しているときに文字列ポインタを返 **_putenv_s、** ランダムなエラーを引き起こす可能性があります。 これらの関数の呼び出しが同期されていることを確認する必要があります。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

**TZ**環境変数の値を確認または変更するには、必要に応**じて**getenv_s **、_putenv、****および _tzset**を使用します。 **TZ**の詳細については[、「_tzset](tzset.md)と[_daylight、_dstbias、_timezone、および _tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_getenv_s.c
// This program uses getenv_s to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char* libvar;
   size_t requiredSize;

   getenv_s( &requiredSize, NULL, 0, "LIB");
   if (requiredSize == 0)
   {
      printf("LIB doesn't exist!\n");
      exit(1);
   }

   libvar = (char*) malloc(requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects
   // the environment variable of the current process. The command
   // processor's environment is not changed.
   _putenv_s( "LIB", "c:\\mylib;c:\\yourlib" );

   getenv_s( &requiredSize, NULL, 0, "LIB");

   libvar = (char*) realloc(libvar, requiredSize * sizeof(char));
   if (!libvar)
   {
      printf("Failed to allocate memory!\n");
      exit(1);
   }

   // Get the new value of the LIB environment variable.
   getenv_s( &requiredSize, libvar, requiredSize, "LIB" );

   printf( "New LIB variable is: %s\n", libvar );

   free(libvar);
}
```

```Output
Original LIB variable is: c:\vctools\lib;c:\vctools\atlmfc\lib;c:\vctools\PlatformSDK\lib;c:\vctools\Visual Studio SDKs\DIA Sdk\lib;c:\vctools\Visual Studio SDKs\BSC Sdk\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[環境定数](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv, _wputenv](putenv-wputenv.md)<br/>
[_dupenv_s, _wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
