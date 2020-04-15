---
title: _fdopen、_wfdopen
ms.date: 4/2/2020
api_name:
- _fdopen
- _wfdopen
- _o__fdopen
- _o__wfdopen
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
ms.openlocfilehash: 82a7e891e8bd6031ebbf761534b6df7cd8488d36
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347385"
---
# <a name="_fdopen-_wfdopen"></a>_fdopen、_wfdopen

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

*Fd*<br/>
開いているファイルのファイル記述子。

*モード*<br/>
ファイル アクセスの種類。

## <a name="return-value"></a>戻り値

これらの各関数は、開いているストリームへのポインターを返します。 エラーが発生すると、NULL のポインター値を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合 **、errno**は、無効なファイル記述子を示す**EBADF**に設定されるか **、EINVAL**に設定され、この*モード*がヌル・ポインターであったことを示します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_fdopen**関数は *、i/O*ストリームを fd で識別されるファイルに関連付けるため、低レベル I/O 用にオープンされたファイルをバッファーおよびフォーマットできます。 **_wfdopen**は **、_fdopen**のワイド文字バージョンです。**_wfdopen**する*モード*引数はワイド文字ストリングです。 **_wfdopen**と **_fdopen**それ以外の場合は同じように動作します。

**_fdopen**に渡されるファイル記述子は、返される**FILE &#42;** ストリームによって所有されます。 **_fdopen**成功した場合は、ファイル記述子で[\_close](close.md)を呼び出しません。 返された**FILE &#42;** で[fclose](fclose-fcloseall.md)を呼び出すと、ファイル記述子もクローズされます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|Tchar.h のルーチン|\_ユニコードと\_MBCS が定義されていません|\_定義された MBCS|\_ユニコードが定義されています|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfdopen**|**_fdopen**|**_fdopen**|**_wfdopen**|

*mode*文字列は、ファイルに要求されたファイル アクセスの種類を指定します。

| *モード* | アクセス |
|--------|--------|
| **"r"** | 読み取り用に開きます。 ファイルが存在しないか、見つからない場合 **、fopen**呼び出しは失敗します。 |
| **"w"** | 書き込み用に空のファイルを開きます。 指定したファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a"** | ファイルの末尾に書き込み用に開きます (追加)。 ファイルが存在しない場合は、作成します。 |
| **"r+"** | 読み取りと書き込みの両方のモードで開きます。 ファイルが存在している必要があります。 |
| **"w+"** | 読み取りと書き込みの両方のモードで空のファイルを開きます。 そのファイルが既に存在すると、そのファイルの内容は破棄されます。 |
| **"a+"** | 読み取りと追加の両方のモードでファイルを開きます。 ファイルが存在しない場合は、作成します。 |

**"a" または "a+"** **"a+"** アクセス タイプでファイルを開くと、すべての書き込み操作はファイルの最後に実行されます。 ファイル ポインタは[fseek](fseek-fseeki64.md)または[巻き戻し](rewind.md)を使用して再配置できますが、書き込み操作が実行される前に、常にファイルの末尾に戻されます。したがって、既存のデータを上書きすることはできません。 **"r+"** **、"w+"、** または **"a+"** アクセスタイプが指定されている場合、読み取りと書き込みの両方が許可されます (ファイルは"更新"用に開かれていると言われます)。 ただし、読み取りと書き込みを切り替える場合は[、fflush](fflush.md) [、fsetpos](fsetpos.md) [、fseek](fseek-fseeki64.md)、または[巻き戻し](rewind.md)操作が介入する必要があります。 必要に応じて[、fsetpos](fsetpos.md)または[fseek](fseek-fseeki64.md)操作の現在位置を指定できます。

上記の値に加えて、次の文字を*mode*に含めて改行文字の変換モードを指定することもできます。

| *モード*修飾子 | 動作 |
|-----------------|----------|
| **T** | ファイルをテキスト (変換) モードで開きます。 このモードでは、復帰と改行 (CR-LF) の組み合わせは入力時に 1 つの改行 (LF) 文字に変換され、LF 文字は出力時に CR-LF の組み合わせに変換されます。 また、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 |
| **B** | バイナリ (無変換) モードで開きます。 **t**モードからの変換は抑制されます。 |
| **C** | **fflush**または **_flushall**が呼び出された場合にファイル・バッファーの内容がディスクに直接書き込まれるように、関連する*ファイル名*のコミット・フラグを使用可能にします。 |
| **n** | 関連付けられた*ファイル名*のコミット フラグを "no-commit" にリセットします。 これは既定値です。 また、プログラムを Commode.obj にリンクする場合は、グローバル コミット フラグもオーバーライドされます。プログラムを Commode.obj に明示的にリンクしない限り、グローバル コミット フラグの既定値は "コミットなし" です。 |

**t**、 **c**、**および n** *の各モード*のオプションは **、fopen**および **_fdopen**用の Microsoft 拡張です。 ANSI の移植性を維持する場合には使用しないでください。

**t**または**b**が*mode*で指定されていない場合、デフォルトの変換モードはグローバル変数[\_fmode](../../c-runtime-library/fmode.md)によって定義されます。 **t**または**b**が引数の前に付く場合、関数は失敗し、NULL を返します。 テキスト モードとバイナリ モードの詳細については、「[テキスト モードとバイナリ モードのファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)」を参照してください。

**fopen**および **_fdopen**で使用される*モード*文字列の有効な文字は、次の表に示すように[\_、open](open-wopen.md)および[\_sopen](sopen-wsopen.md)で使用される*oflag*引数に対応します。

|*モード*文字列の文字|**_open**と **_sopen***の同等のラグ*値|
|---------------------------------|---------------------------------------------------|
|**A**|**\_O\_WRONLY \_\_&#124; O APPEND** (通常**\_は\_、O CREAT \_&#124;\_ \_O\_APPEND ) を&#124;します**。|
|**a+**|**\_O\_RDWR \_\_&#124; O APPEND** (通常**\_は\_O\_\_RDWR \_&#124; O\_APPEND &#124; O CREAT** )|
|**R**|**\_O\_RDONLY**|
|**r+**|**\_O\_RDWR**|
|**W**|**\_O\_WRONLY** (通常**\_\_、O \_\_WRONLY \_&#124;\_O CREAT &#124; O TRUNC**)|
|**w+**|**\_O\_RDWR** (通常**\_は\_ \_O\_RDWR \_\_&#124; O CREAT &#124; O TRUNC**)|
|**B**|**\_O\_バイナリー**|
|**T**|**\_O\_テキスト**|
|**C**|なし|
|**n**|なし|

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fdopen**|\<stdio.h>|
|**_wfdopen**|\<stdio.h> または \<wchar.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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

### <a name="input-crt_fdopentxt"></a>入力: crt_fdopen.txt

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
[\_dup, \_dup2](dup-dup2.md)<br/>
[ファミリ、\_ファミリオール](fclose-fcloseall.md)<br/>
[ファオープン, \_wfopen](fopen-wfopen.md)<br/>
[フレオープン, \_wfreopen](freopen-wfreopen.md)<br/>
[\_開く\_, 開く](open-wopen.md)<br/>
