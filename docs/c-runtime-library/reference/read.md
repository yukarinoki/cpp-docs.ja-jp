---
title: _read
ms.date: 4/2/2020
api_name:
- _read
- _o__read
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _read
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
ms.openlocfilehash: db3726b85bb4ba7c8e9a691bef3fb063ec5709c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338131"
---
# <a name="_read"></a>_read

ファイルからデータを読み取ります。

## <a name="syntax"></a>構文

```C
int _read(
   int const fd,
   void * const buffer,
   unsigned const buffer_size
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
開いているファイルを参照するファイル記述子。

*バッファー*<br/>
データの格納場所。

*buffer_size*<br/>
読み取る最大バイト数。

## <a name="return-value"></a>戻り値

**_read**は読み込んだバイト数を返しますが、ファイルに残っているバイト数が*buffer_size*未満の場合、またはファイルがテキスト モードで開かれた場合は *、buffer_size*未満になる可能性があります。 テキスト モードでは、各復帰改行のペア`\r\n`は 1 つの改行文字`\n`に置き換えられます。 戻り値には、単一の改行文字のみがカウントされます。 この置き換えは、ファイル ポインターには影響しません。

この関数はファイルの終わりで読み取りをすると、0 を返します。 *fd*が有効でない場合、ファイルが読み取り用に開かれていないか、ファイルがロックされている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」の説明に従って無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は -1 を返し **、errno**を**EBADF**に設定します。

*buffer*が**NULL**の場合、または*INT_MAXbuffer_size* > **INT_MAX**場合は、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は -1 を返し **、errno**は**EINVAL**に設定されます。

このリターン コードとその他のリターン コードの詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_read**関数は *、fd*に関連付けられたファイルから最大*buffer_size*バイトを*バッファー*に読み取ります。 読み取り操作は、指定されたファイルに関連付けられたファイル ポインターの現在の位置で開始されます。 読み取り操作後、ファイル ポインターは、次の未読の文字を指します。

ファイルがテキスト モードで開かれた場合、_readが Ctrl + Z 文字 (ファイル終了標識として扱われる)**を検出すると**、読み取りは終了します。 ファイルの終わりのインジケーターをクリアするには、[_lseek](lseek-lseeki64.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_read**|\<io.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_read.c
/* This program opens a file named crt_read.txt
* and tries to read 60,000 bytes from
* that file using _read. It then displays the
* actual number of bytes read.
*/

#include <fcntl.h>      /* Needed only for _O_RDWR definition */
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <share.h>

char buffer[60000];

int main( void )
{
   int fh, bytesread;
   unsigned int nbytes = 60000;

   /* Open file for input: */
   if ( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ))
   {
      perror( "open failed on input file" );
      exit( 1 );
   }

   /* Read in input: */
   if (( bytesread = _read( fh, buffer, nbytes )) <= 0 )
      perror( "Problem reading file" );
   else
      printf( "Read %u bytes from file\n", bytesread );

   _close( fh );
}
```

### <a name="input-crt_readtxt"></a>入力: crt_read.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
Read 19 bytes from file
```

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[_creat、_wcreat](creat-wcreat.md)<br/>
[fread](fread.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
[_write](write.md)<br/>
