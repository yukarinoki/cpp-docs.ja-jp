---
title: getenv_s、_wgetenv_s
ms.date: 11/04/2016
apiname:
- getenv_s
- _wgetenv_s
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
ms.openlocfilehash: eac3c036e2f4f271c7bc2d77c8ae82bec28d3617
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546521"
---
# <a name="getenvs-wgetenvs"></a>getenv_s、_wgetenv_s

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

*pReturnValue*<br/>
必要なバッファー サイズ。変数が見つからない場合は 0。

*バッファー*<br/>
環境変数の値を格納するバッファー。

*numberOfElements*<br/>
サイズ*バッファー*します。

*varname*<br/>
環境変数名。

## <a name="return-value"></a>戻り値

正常に終了した場合は 0 を返し、それ以外の場合は失敗に関するエラー コードを返します。

### <a name="error-conditions"></a>エラー条件

|*pReturnValue*|*バッファー*|*numberOfElements*|*varname*|戻り値|
|--------------------|--------------|------------------------|---------------|------------------|
|**NULL**|任意|任意|任意|**EINVAL**|
|任意|**NULL**|>0|任意|**EINVAL**|
|任意|任意|任意|**NULL**|**EINVAL**|

これらのいずれかのエラー条件の場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」(パラメーターの検証) で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数が設定**errno**に**EINVAL**戻って**EINVAL**します。

また、バッファーが小さすぎる場合は、これらの関数を返す**ERANGE**します。 無効なパラメーター ハンドラーは呼び出されません。 出力で必要なバッファー サイズ*pReturnValue*、し、それによってより大きなバッファーを使用して関数を呼び出すプログラムを有効にします。

## <a name="remarks"></a>Remarks

**Getenv_s**関数用の環境変数の一覧を検索する*varname*します。 **getenv_s** Windows オペレーティング システムで大文字小文字は区別されません。 **getenv_s**と[_putenv_s](putenv-s-wputenv-s.md)グローバル変数によってポイントされている環境のコピーを使用して **_environ**環境にアクセスします。 **getenv_s**と「セグメント」プロセスのオペレーティング システムによって作成される環境ではなく、ランタイム ライブラリにアクセスできるデータ構造でのみ動作します。 そのため、プログラムを使用する、 *envp*引数[メイン](../../cpp/main-program-startup.md)または[wmain](../../cpp/main-program-startup.md)無効な情報を取得する可能性があります。

**_wgetenv_s**のワイド文字バージョンは、 **getenv_s**; の引数と戻り値 **_wgetenv_s**はワイド文字列です。 **_Wenviron**グローバル変数はワイド文字バージョンの **_environ**します。

(たとえば、SBCS ASCII プログラム) での MBCS プログラムで **_wenviron**が最初に**NULL**環境がマルチバイト文字の文字列で構成されるためです。 その後、最初の呼び出し  [_wputenv](putenv-wputenv.md)、または最初の呼び出しで **_wgetenv_s**、対応するワイド文字列環境が作成され、しを指しています (MBCS) 環境が既に存在する場合 **_wenviron**します。

同様に、Unicode (**_wmain**) プログラム、 **_environ**が最初に**NULL**環境がワイド文字の文字列で構成されているためです。 その後、最初の呼び出し  [_putenv](putenv-wputenv.md)、または最初の呼び出しで**getenv_s** (Unicode) 環境が既に存在する場合、対応する MBCS 環境が作成され、しを指しています **_environ**します。

2 つの環境のコピー (MBCS および Unicode) がプログラムに同時に存在する場合、ランタイム システムは、両方のコピーを保持する必要があるため、実行時間が長くなります。 たとえば、呼び出す **_putenv**への呼び出し **_wputenv**も自動的に実行、2 つの環境文字列が対応できるようにします。

> [!CAUTION]
> まれに、ランタイム システムが Unicode 環境とマルチバイト環境の両方を保持している場合、これら 2 つの環境が正確に対応しないことがあります。 これは、一意のマルチバイト文字列はすべて一意の Unicode 文字列に対応していますが、一意の Unicode 文字列は必ずしも一意のマルチバイト文字列に対応していないために発生します。 詳細については、「[_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」をご覧ください。

> [!NOTE]
> **_Putenv_s**と **_getenv_s**系関数はスレッド セーフではされません。 **_getenv_s**中に文字列ポインターを返すことができます **_putenv_s**文字列を変更して、ランダムにエラーの原因になります。 これらの関数の呼び出しが同期されていることを確認する必要があります。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv_s**|**getenv_s**|**getenv_s**|**_wgetenv_s**|

確認するかの値を変更する、 **TZ**環境変数を使用して**getenv_s**、 **_putenv**、および **_tzset**必要があります。 詳細については**TZ**を参照してください[_tzset](tzset.md)と[_daylight、_dstbias、_timezone、_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**getenv_s**|\<stdlib.h>|
|**_wgetenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[環境定数](../../c-runtime-library/environmental-constants.md)<br/>
[_putenv、_wputenv](putenv-wputenv.md)<br/>
[_dupenv_s、_wdupenv_s](dupenv-s-wdupenv-s.md)<br/>
