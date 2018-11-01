---
title: _chsize
ms.date: 03/29/2018
apiname:
- _chsize
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
- _chsize
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
ms.openlocfilehash: 5c60f3aa08a405eb9a83dc6ba8636cd316a32925
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600643"
---
# <a name="chsize"></a>_chsize

ファイル サイズを変更します。 セキュリティが強化されたバージョンについては、「[_chsize_s](chsize-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _chsize(
   int fd,
   long size
);
```

### <a name="parameters"></a>パラメーター

*fd*<br/>
開いているファイルを参照するファイル記述子。

*size*<br/>
バイト単位のファイルの新しい長さ。

## <a name="return-value"></a>戻り値

**_chsize**ファイル サイズが正常に変更された場合、値 0 を返します。 戻り値-1 はエラーを示します: **errno**に設定されている**EACCES**指定したファイルが読み取り専用か、指定したファイルがアクセスに対してにロックされている**EBADF**場合、記述子が有効でない**ENOSPC** 、デバイス上の領域が残っていない場合または**EINVAL**場合*サイズ*0 未満です。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**_Chsize**関数の拡張またはに関連付けられているファイルを切り捨てます*fd*で指定された長さに*サイズ*します。 ファイルは、書き込みを許可するモードで開かれている必要があります。 ファイルが拡張される場合は、null 文字 ('\0') が追加されます。 ファイルが切り捨てられる場合、短くなったファイルの末尾からファイルの元の長さまでのすべてのデータは失われます。

この関数は、パラメーターを検証します。 場合*サイズ*が 0 未満または*fd*が正しくないファイル記述子で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_chsize**|\<io.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_chsize.c
// This program uses _filelength to report the size
// of a file before and after modifying it with _chsize.

#include <io.h>
#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <share.h>

int main( void )
{
   int fh, result;
   unsigned int nbytes = BUFSIZ;

   // Open a file
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,
                 _S_IREAD | _S_IWRITE ) == 0 )
   {
      printf( "File length before: %ld\n", _filelength( fh ) );
      if( ( result = _chsize( fh, 329678 ) ) == 0 )
         printf( "Size successfully changed\n" );
      else
         printf( "Problem in changing the size\n" );
      printf( "File length after:  %ld\n", _filelength( fh ) );
      _close( fh );
   }
}
```

```Output
File length before: 0
Size successfully changed
File length after:  329678
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_close](close.md)<br/>
[_sopen、_wsopen](sopen-wsopen.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
