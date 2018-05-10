---
title: _fdopen、_wfdopen | Microsoft ドキュメント
ms.custom: ''
ms.date: 12/12/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _fdopen
- _wfdopen
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
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs:
- C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 21bd849d5ce9560fae356869291d6764d613f0a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="fdopen-wfdopen"></a>_fdopen、_wfdopen

ストリームを前回下位入出力で開いたファイルに関連付けます。

## <a name="syntax"></a>構文

```C
FILE *_fdopen(
   int fd,
   const char *mode
);
FILE *_wfdopen(
   int fd,
   const wchar_t *mode
);
```

### <a name="parameters"></a>パラメーター

*fd*開いているファイルのファイル記述子。

*モード*ファイル アクセスの種類。

## <a name="return-value"></a>戻り値

これらの各関数は、開いているストリームへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 続けるには、実行が許可された場合**errno**に設定されているいずれかの**EBADF**、無効なファイル記述子を示すまたは**EINVAL**、ことを示します*モード*が null ポインターでした。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Fdopen**関数では関連付けますによって識別されるファイルの I/O ストリーム*fd*、できるので、低レベルの i/o バッファーおよびフォーマットが開かれているファイル。 **_wfdopen**のワイド文字バージョンは、 **_fdopen**;*モード*に渡す引数 **_wfdopen**ワイド文字列です。 **_wfdopen**と **_fdopen**それ以外の場合、動作は同じです。

ファイル記述子に渡された **_fdopen**が所有するによって、返された**ファイル&#42;** ストリーム。 場合 **_fdopen**が成功すると、呼び出すことはありません[\_閉じる](close.md)ファイル記述子。 呼び出す[fclose](fclose-fcloseall.md)で返された**ファイル&#42;** もファイル記述子を閉じます。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|\_UNICODE と\_MBCS が定義されていません|\_MBCS の定義|\_UNICODE の定義|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*モード*文字の文字列をファイルに、要求のファイル アクセスの種類を指定します。

|*モード*|アクセス|
|-|-|
**"r"**|読み取り用に開きます。 ファイルが存在しないかを検出できない場合、 **fopen**呼び出しは失敗します。
**"w"**|書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。
**"a"**|(追加モード) ファイルの末尾に書き込み用に開きます。 ファイルが存在しない場合は、作成します。
**"r+"**|読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。
**"w+"**|読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。
**"a+"**|読み取りと追加の両方のモードでファイルを開きます。 ファイルが存在しない場合は、作成します。

使用するファイルを開くと、 **"a"** または**「a +」**アクセスの種類、すべての書き込み操作、ファイルの末尾から行われます。 使用して、ファイル ポインターの位置を変更できる[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)が、常に戻さファイルの末尾には、書き込み操作の前にします。したがって、既存のデータは上書きされません。 ときに、 **「r +」**、 **「w +」**、または**「a +」**アクセスの種類を指定すると、読み取りと書き込みの両方が許可されている (ファイルは「更新」開いていると考えられます)。 ただし、読み取りと書き込みを切り替えるときに存在する必要があります、介在する[fflush](fflush.md)、 [fsetpos](fsetpos.md)、 [fseek](fseek-fseeki64.md)、または[巻き戻し](rewind.md)操作。 現在位置を指定することができます、 [fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)する場合は、操作します。

上記の値に加え、次の文字含めることもできますで*モード*改行文字の変換モードを指定します。

|*モード*修飾子|動作|
|-|-|
**t**|ファイルをテキスト (変換) モードで開きます。 このモードでは、復帰と改行 (CR-LF) の組み合わせは入力時に 1 つの改行 (LF) 文字に変換され、LF 文字は出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。
**b**|バイナリ (無変換) モードで開きます。 すべての翻訳が**t**モードが抑制されます。
**c**|関連付けられたのコミット フラグを有効にする*filename*ファイル バッファーの内容がいずれかのディスクに直接書き込まれるように**fflush**または **_flushall**と呼びます。
**n**|関連付けられたのコミット フラグをリセット*filename*を「コミットなし」。 既定値です。 プログラムを Commode.obj とリンクする場合は、グローバル コミット フラグもオーバーライドします。プログラムを明示的に Commode.obj とリンクしない場合、グローバル コミット フラグの既定の設定は "コミットなし" です。

**T**、 **c**、および**n** *モード*オプションは、Microsoft 拡張機能**fopen**と **_fdopen**です。 ANSI の移植性を維持する場合には使用しないでください。

場合**t**または**b**には、指定しない*モード*、既定の変換モードがグローバル変数によって定義されている[ \_fmode](../../c-runtime-library/fmode.md)です。 場合**t**または**b**は引数の先頭に、その関数は失敗し、NULL を返します。 テキスト モードと binary モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

有効な文字、*モード*で使用される文字列**fopen**と **_fdopen**に対応している*oflag*で使用される引数[\_開く](open-wopen.md)と[ \_sopen](sopen-wsopen.md)次の表に示すように、します。

|内の文字*モード*文字列|等価*oflag*値 **_open**と **_sopen**|
|---------------------------------|---------------------------------------------------|
|**a**|**\_O\_WRONLY &#124; \_O\_APPEND** (通常 **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_APPEND**)|
|**+**|**\_O\_RDWR &#124; \_O\_APPEND** (通常 **\_O\_RDWR &#124; \_O\_APPEND &#124; \_O\_CREAT** )|
|**r**|**\_O\_RDONLY**|
|**r +**|**\_O\_RDWR**|
|**w**|**\_O\_WRONLY** (通常 **\_O\_WRONLY &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**w +**|**\_O\_RDWR** (通常 **\_O\_RDWR &#124; \_O\_CREAT &#124; \_O\_TRUNC**)|
|**b**|**\_O\_バイナリ**|
|**t**|**\_O\_TEXT**|
|**c**|なし|
|**n**|なし|

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```c
// crt_fdopen.c
// This program opens a file by using low-level
// I/O, then uses _fdopen to switch to stream
// access. It counts the lines in the file.

#include <stdlib.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>
#include <share.h>

int main( void )
{
   FILE *stream;
   int  fd, count = 0;
   char inbuf[128];

   // Open a file.
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )
      exit( 1 );

   // Get stream from file descriptor.
   if( (stream = _fdopen( fd, "r" )) == NULL )
      exit( 1 );

   while( fgets( inbuf, 128, stream ) != NULL )
      count++;

   // After _fdopen, close by using fclose, not _close.
   fclose( stream );
   printf( "Lines in file: %d\n", count );
}
```

### <a name="input-crtfdopentxt"></a>入力: crt_fdopen.txt

```Input
Line one
Line two
```

### <a name="output"></a>出力

```Output
Lines in file: 2
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[\_dup、 \_dup2](dup-dup2.md)<br/>
[fclose、 \_fcloseall](fclose-fcloseall.md)<br/>
[fopen、 \_wfopen](fopen-wfopen.md)<br/>
[freopen、 \_wfreopen](freopen-wfreopen.md)<br/>
[\_開くには、 \_wopen](open-wopen.md)<br/>
