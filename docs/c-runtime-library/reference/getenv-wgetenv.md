---
title: getenv、_wgetenv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- getenv
- _wgetenv
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
- _wgetenv
- getenv
- _tgetenv
dev_langs:
- C++
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a2e68ca55d9e33995df583719e4797a6880d34ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403987"
---
# <a name="getenv-wgetenv"></a>getenv、_wgetenv

現在の環境から値を取得します。 これらの関数にはセキュリティが強化されたバージョンがあります。「[getenv_s、_wgetenv_s](getenv-s-wgetenv-s.md)」をご覧ください。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *getenv(
   const char *varname
);
wchar_t *_wgetenv(
   const wchar_t *varname
);
```

### <a name="parameters"></a>パラメーター

*varname*<br/>
環境変数名。

## <a name="return-value"></a>戻り値

含む環境テーブル エントリのポインターを返します*varname*です。 返されたポインターを使用して環境変数の値を変更することは安全ではありません。 使用して、 [_putenv](putenv-wputenv.md)環境変数の値を変更する関数。 戻り値は**NULL**場合*varname*は環境のテーブルに存在しません。

## <a name="remarks"></a>コメント

**Getenv**関数は、環境変数の一覧を検索*varname*です。 **getenv** Windows オペレーティング システムで大文字小文字は区別されません。 **getenv**と **_putenv**グローバル変数が指す環境のコピーを使用して **_environ**環境にアクセスします。 **getenv**を対象とし、環境「セグメント」は、オペレーティング システムによって、プロセスの作成ではなく、ランタイム ライブラリにアクセスできるデータ構造でのみです。 そのため、プログラムを使用する、 *envp*引数[メイン](../../cpp/main-program-startup.md)または[wmain](../../cpp/main-program-startup.md)無効な情報を取得することがあります。

場合*varname*は**NULL**、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**NULL**です。

**_wgetenv**のワイド文字バージョンは、 **getenv**; の引数と戻り値 **_wgetenv**ワイド文字列です。 **_Wenviron**グローバル変数のワイド文字バージョンは、 **_environ**です。

MBCS プログラムで (たとえば、SBCS ASCII プログラム)、 **_wenviron**を最初に**NULL**環境がマルチバイト文字の文字列で構成されるためです。 その後、最初の呼び出し  [_wputenv](putenv-wputenv.md)、または最初の呼び出しで **_wgetenv**対応するワイド文字列環境が作成され、によって指されるし(MBCS)環境が既に存在する場合 **_wenviron**です。

同様に、Unicode (**_wmain**) プログラム、 **_environ**を最初に**NULL**環境がワイド文字の文字列で構成されるためです。 その後、最初の呼び出し  **_putenv**、または最初の呼び出しで**getenv** (Unicode) 環境が既に存在する場合、対応する MBCS 環境が作成され、によって指されるし **_environ**です。

2 つの環境のコピー (MBCS および Unicode) がプログラムに同時に存在する場合、ランタイム システムは、両方のコピーを保持する必要があるため、実行時間が長くなります。 たとえば、呼び出す場合 **_putenv**への呼び出し **_wputenv**も自動的に実行を 2 つの環境文字列が対応できるようにします。

> [!CAUTION]
> まれに、ランタイム システムが Unicode 環境とマルチバイト環境の両方を保持している場合、これら 2 つの環境が正確に対応しないことがあります。 これは、一意のマルチバイト文字列はすべて一意の Unicode 文字列に対応していますが、一意の Unicode 文字列は必ずしも一意のマルチバイト文字列に対応していないためです。 詳細については、「[_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」をご覧ください。

> [!NOTE]
> **_Putenv**と**系**系関数はスレッド セーフではありません。 **_putenv**中に文字列ポインターを返すことが **_putenv**はランダム エラーの原因、文字列を変更します。 これらの関数の呼び出しが同期されていることを確認する必要があります。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

確認するかの値を変更する、 **TZ**環境変数を使用して**getenv**、 **_putenv**と **_tzset**必要に応じて、します。 詳細については**TZ**を参照してください[_tzset](tzset.md)と[_daylight、timezone、_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**getenv**|\<stdlib.h>|
|**_wgetenv**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_getenv.c
// compile with: /W3
// This program uses getenv to retrieve
// the LIB environment variable and then uses
// _putenv to change it to a new value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *libvar;

   // Get the value of the LIB environment variable.
   libvar = getenv( "LIB" ); // C4996
   // Note: getenv is deprecated; consider using getenv_s instead

   if( libvar != NULL )
      printf( "Original LIB variable is: %s\n", libvar );

   // Attempt to change path. Note that this only affects the environment
   // variable of the current process. The command processor's
   // environment is not changed.
   _putenv( "LIB=c:\\mylib;c:\\yourlib" ); // C4996
   // Note: _putenv is deprecated; consider using putenv_s instead

   // Get new value.
   libvar = getenv( "LIB" ); // C4996

   if( libvar != NULL )
      printf( "New LIB variable is: %s\n", libvar );
}
```

```Output
Original LIB variable is: C:\progra~1\devstu~1\vc\lib
New LIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_putenv、_wputenv](putenv-wputenv.md)<br/>
[環境定数](../../c-runtime-library/environmental-constants.md)<br/>
