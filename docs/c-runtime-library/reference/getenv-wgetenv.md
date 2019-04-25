---
title: getenv、_wgetenv
ms.date: 11/04/2016
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
helpviewer_keywords:
- getenv function
- tgetenv function
- wgetenv function
- environment values
- environment variables
- _tgetenv function
- _wgetenv function
ms.assetid: 3b9cb9ab-a126-4e0e-a44f-6c5a7134daf4
ms.openlocfilehash: 79c685fef8d6a4b966c53bb7d94b423d16971976
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157670"
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

含む環境テーブル エントリのポインターを返します*varname*します。 返されたポインターを使用して環境変数の値を変更することは安全ではありません。 使用して、 [_putenv](putenv-wputenv.md)環境変数の値を変更する関数。 戻り値は**NULL**場合*varname*環境テーブルに含まれていません。

## <a name="remarks"></a>Remarks

**Getenv**関数用の環境変数の一覧を検索する*varname*します。 **getenv** Windows オペレーティング システムで大文字小文字は区別されません。 **getenv**と **_putenv**グローバル変数が指す環境のコピーを使用して **_environ**環境にアクセスします。 **getenv**と環境「セグメント」は、オペレーティング システムによって、プロセスの作成ではなく、ランタイム ライブラリにアクセスできるデータ構造でのみ動作します。 そのため、プログラムを使用する、 *envp*引数[メイン](../../cpp/main-program-startup.md)または[wmain](../../cpp/main-program-startup.md)無効な情報を取得することがあります。

場合*varname*は**NULL**、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**返します**NULL**します。

**_wgetenv**のワイド文字バージョンは、 **getenv**; の引数と戻り値 **_wgetenv**はワイド文字列です。 **_Wenviron**グローバル変数はワイド文字バージョンの **_environ**します。

(たとえば、SBCS ASCII プログラム) での MBCS プログラムで **_wenviron**が最初に**NULL**環境がマルチバイト文字の文字列で構成されるためです。 その後、最初の呼び出し  [_wputenv](putenv-wputenv.md)、または最初の呼び出しで **_wgetenv** (MBCS) 環境が既に存在する場合、対応するワイド文字列環境が作成され、でし指し示されます **_wenviron**します。

同様に、Unicode (**_wmain**) プログラム、 **_environ**が最初に**NULL**環境がワイド文字の文字列で構成されているためです。 その後、最初の呼び出し  **_putenv**、または最初の呼び出しで**getenv** (Unicode) 環境が既に存在する場合、対応する MBCS 環境が作成され、しを指しています **_environ**します。

2 つの環境のコピー (MBCS および Unicode) がプログラムに同時に存在する場合、ランタイム システムは、両方のコピーを保持する必要があるため、実行時間が長くなります。 たとえば、呼び出したとき **_putenv**への呼び出し **_wputenv** 2 つの環境文字列が対応できるように自動的に実行されてもします。

> [!CAUTION]
> まれに、ランタイム システムが Unicode 環境とマルチバイト環境の両方を保持している場合、これら 2 つの環境が正確に対応しないことがあります。 これは、一意のマルチバイト文字列はすべて一意の Unicode 文字列に対応していますが、一意の Unicode 文字列は必ずしも一意のマルチバイト文字列に対応していないためです。 詳細については、「[_environ、_wenviron](../../c-runtime-library/environ-wenviron.md)」をご覧ください。

> [!NOTE]
> **_Putenv**と**系**系関数はスレッド セーフではされません。 **_putenv**中に文字列ポインターを返すことができます **_putenv**がランダムにエラーの原因と、文字列を変更します。 これらの関数の呼び出しが同期されていることを確認する必要があります。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tgetenv**|**getenv**|**getenv**|**_wgetenv**|

確認するかの値を変更する、 **TZ**環境変数を使用して**getenv**、 **_putenv**と **_tzset**に応じて。 詳細については**TZ**を参照してください[_tzset](tzset.md)と[_daylight、timezone、_tzname](../../c-runtime-library/daylight-dstbias-timezone-and-tzname.md)します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
