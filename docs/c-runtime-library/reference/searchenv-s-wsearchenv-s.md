---
title: _searchenv_s、_wsearchenv_s
ms.date: 11/04/2016
apiname:
- _wsearchenv_s
- _searchenv_s
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
- _searchenv_s
- _wsearchenv_s
- wsearchenv_s
- searchenv_s
helpviewer_keywords:
- tsearchenv_s function
- files [C++], finding
- buffers [C++], buffer overruns
- environment paths, searching for files
- wsearchenv_s function
- searchenv_s function
- _tsearchenv_s function
- buffer overruns
- buffers [C++], avoiding overruns
- _wsearchenv_s function
- _searchenv_s function
- environment paths
ms.assetid: 47f9fc29-250e-4c09-b52e-9e9f0ef395ca
ms.openlocfilehash: 40c2d0c42a3d61f84db78015388eba19742af06e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505678"
---
# <a name="searchenvs-wsearchenvs"></a>_searchenv_s、_wsearchenv_s

環境のパスを使用してファイルを検索します。 これらの [_searchenv および _wsearchenv](searchenv-wsearchenv.md) のバージョンは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」(CRT のセキュリティ機能) で説明されているように、セキュリティが強化されています。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char *pathname,
   size_t numberOfElements
);
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t *pathname,
   size_t numberOfElements
);
template <size_t size>
errno_t _searchenv_s(
   const char *filename,
   const char *varname,
   char (&pathname)[size]
); // C++ only
template <size_t size>
errno_t _wsearchenv_s(
   const wchar_t *filename,
   const wchar_t *varname,
   wchar_t (&pathname)[size]
); // C++ only
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
検索するファイルの名前。

*varname*<br/>
検索する環境。

*pathname*<br/>
完全パスを格納するバッファー。

*numberOfElements*<br/>
サイズ、 *pathname*バッファー。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

場合*filename*空の文字列には、戻り値は**ENOENT**します。

### <a name="error-conditions"></a>エラー条件

|*ファイル名*|*varname*|*pathname*|*numberOfElements*|戻り値|内容*パス名*|
|----------------|---------------|----------------|------------------------|------------------|----------------------------|
|任意|任意|**NULL**|任意|**EINVAL**|N/A|
|**NULL**|任意|任意|任意|**EINVAL**|変更されない|
|任意|任意|任意|<= 0|**EINVAL**|変更されない|

上記のいずれかのエラー条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラ―が呼び出されます。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**戻って**EINVAL**します。

## <a name="remarks"></a>Remarks

**_Searchenv_s**日常的な指定したドメインでターゲット ファイルを検索します。 *Varname*変数が指定できる任意の環境またはユーザー定義の変数などのディレクトリのパスの一覧を示す**パス**、 **LIB**、および**インクルード**. **_Searchenv_s**と小文字は区別*varname*環境変数の大文字と小文字が一致する必要があります。 場合*varname*プロセスの環境で定義されている環境変数の名前と一致しません、関数は 0 を返します、 *pathname*変数は変更されません。

このルーチンは最初に現在の作業ディレクトリでファイルを検索します。 ファイルが見つからなかった場合、環境変数で指定されている次のディレクトリを検索します。 新しく作成されたパスをコピーする場合は、対象のファイルは、これらのディレクトリのいずれかでは、 *pathname*します。 場合、 *filename*ファイルが見つからない*pathname* null で終わる空の文字列が含まれています。

*Pathname*バッファーは以上である必要があります **_MAX_PATH**作成されるパス名の長さを格納します。 それ以外の場合、 **_searchenv_s**オーバーランの可能性があります、 *pathname*予期しない動作のバッファー。

**_wsearchenv_s**のワイド文字バージョンは、 **_searchenv_s**; 引数 **_wsearchenv_s**はワイド文字列です。 **_wsearchenv_s**と **_searchenv_s**動作は同じです。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tsearchenv_s**|**_searchenv_s**|**_searchenv_s**|**_wsearchenv_s**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_searchenv_s**|\<stdlib.h>|
|**_wsearchenv_s**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_searchenv_s.c
/* This program searches for a file in
* a directory specified by an environment variable.
*/

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char pathbuffer[_MAX_PATH];
   char searchfile[] = "CL.EXE";
   char envvar[] = "PATH";
   errno_t err;

   /* Search for file in PATH environment variable: */
   err = _searchenv_s( searchfile, envvar, pathbuffer, _MAX_PATH );
   if (err != 0)
   {
      printf("Error searching the path. Error code: %d\n", err);
   }
   if( *pathbuffer != '\0' )
      printf( "Path for %s:\n%s\n", searchfile, pathbuffer );
   else
      printf( "%s not found\n", searchfile );
}
```

```Output
Path for CL.EXE:
C:\Program Files\Microsoft Visual Studio 2010\VC\BIN\CL.EXE
```

## <a name="see-also"></a>関連項目

[ディレクトリ制御](../../c-runtime-library/directory-control.md)<br/>
[_searchenv、_wsearchenv](searchenv-wsearchenv.md)<br/>
[getenv、 _wgetenv](getenv-wgetenv.md)<br/>
[_putenv、_wputenv](putenv-wputenv.md)<br/>
