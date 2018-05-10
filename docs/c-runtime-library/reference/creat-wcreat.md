---
title: _creat、_wcreat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _creat
- _wcreat
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 341ffb176a82845ec515e2ab2ff9a6d19b7773ea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="creat-wcreat"></a>_creat、_wcreat

新しいファイルを作成します。 **_creat**と **_wcreat**が推奨されていません。 使用[_sopen_s、_wsopen_s](sopen-s-wsopen-s.md)代わりにします。

## <a name="syntax"></a>構文

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
新しいファイルの名前。

*pmode*<br/>
アクセス許可の設定。

## <a name="return-value"></a>戻り値

これらの関数は正常に実行された場合、作成されたファイルにファイル記述子を返します。 関数が-1 を返しますそれ以外の場合、設定と**errno**次の表に示すようにします。

|**errno**設定|説明|
|---------------------|-----------------|
|**EACCES**|*filename*既存の読み取り専用ファイルを指定するか、ファイルではなくディレクトリを指定します。|
|**EMFILE**|ファイル記述子をこれ以上使用できません。|
|**ENOENT**|指定されたファイルが見つかりませんでした。|

場合*filename* null、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**し、-1 を返します。

リターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Creat**関数新しいファイルを作成または開き、既存のものを切り捨てます。 **_wcreat**のワイド文字バージョンは、 **_creat**以外の場合は、 *filename*に渡す引数 **_wcreat**ワイド文字列です。 **_wcreat**と **_creat**それ以外の場合の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

ファイルが指定された場合*filename*が存在しない新しいファイルが指定されたアクセス許可を設定して作成し、書き込み用に開きます。 ファイルが既に存在し、その設定が書き込み許可、 **_creat**ファイルを長さ 0 で、以前の内容の破棄によってが切り捨てられ、書き込み用に開きます。 アクセス許可の設定、 *pmode*、新しく作成されたファイルのみに適用されます。 新しいファイルは、最初に閉じた後に、指定されたアクセス許可設定を受け取ります。 整数型の式*pmode*マニフェスト定数の一方または両方を含む **_S_IWRITE**と **_S_IREAD**sys \stat.h で定義されている。 両方の定数を指定する場合は結合、ビットごとの or 演算子 ( **&#124;** )。 *Pmode*パラメーターは、次の値のいずれかに設定します。

|[値]|定義|
|-----------|----------------|
|**_S_IWRITE**|書き込みが許可されます。|
|**_S_IREAD**|読み取りが許可されます。|
|**_S_IREAD** &AMP;#124; **_S_IWRITE**|読み取りと書き込みが許可されます。|

書き込みアクセス許可が与えられない場合、ファイルは読み取り専用になります。 ファイルはすべて常に読み取り可能です。書き込みのみのアクセス許可を与えることはできません。 モード **_S_IWRITE**と **_S_IREAD** | **_S_IWRITE**は同等になります。 使用して開かれたファイル **_creat**は常に、互換性モードで開く (を参照してください[_sopen](sopen-wsopen.md)) と **_SH_DENYNO**です。

**_creat**を現在のファイルのアクセス許可マスクを適用*pmode*アクセス許可を設定する前に (を参照してください[_umask](umask.md))。 **_creat**は以前のライブラリとの互換性のため、主に提供します。 呼び出し **_open**で **_O_CREAT**と **_O_TRUNC**で、 *oflag*パラメーターは **_creat**し、新しいコードをお勧めします。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|
|**_wcreat**|\<io.h> または \<wchar.h>|\<sys/types.h>、\<sys/stat.h>、\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup、_dup2](dup-dup2.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_sopen、_wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
