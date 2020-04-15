---
title: _fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32
ms.date: 4/2/2020
api_name:
- _fstat32
- _fstat64
- _fstati64
- _fstat
- _fstat64i32
- _fstat32i64
- _o__fstat32
- _o__fstat32i64
- _o__fstat64
- _o__fstat64i32
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _fstat32i64
- fstat
- fstat64i32
- _fstat64
- _fstati64
- fstat64
- _fstat32
- fstat32i64
- fstati64
- _fstat
- fstat32
- _fstat64i32
helpviewer_keywords:
- _fstat64 function
- fstati64 function
- _fstat64i32 function
- _fstat32i64 function
- _fstat32 function
- file information
- fstat64i32 function
- fstat32 function
- fstat function
- fstat64 function
- _fstat function
- _fstati64 function
- fstat32i64 function
ms.assetid: 088f5e7a-9636-4cf7-ab8e-e28d2aa4280a
ms.openlocfilehash: 02d297fec2ada545a8b693abacfecc7981149dae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345667"
---
# <a name="_fstat-_fstat32-_fstat64-_fstati64-_fstat32i64-_fstat64i32"></a>_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32

開いているファイルに関する情報を取得します。

## <a name="syntax"></a>構文

```C
int _fstat(
   int fd,
   struct _stat *buffer
);
int _fstat32(
   int fd,
   struct __stat32 *buffer
);
int _fstat64(
   int fd,
   struct __stat64 *buffer
);
int _fstati64(
   int fd,
   struct _stati64 *buffer
);
int _fstat32i64(
   int fd,
   struct _stat32i64 *buffer
);
int _fstat64i32(
   int fd,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
開いているファイルのファイル記述子。

*バッファー*<br/>
結果を格納する構造体へのポインター。

## <a name="return-value"></a>戻り値

ファイルのステータス情報が取得されると、0 を返します。 戻り値 -1 はエラーを示します。 ファイル記述子が無効であるか、*またはバッファー*が**NULL**の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合 **、errno**は無効なファイル記述子の場合は**EBADF**に設定され *、buffer*が**NULL**の場合は**EINVAL**に設定されます。

## <a name="remarks"></a>解説

**_fstat**関数は *、fd*に関連付けられたオープン・ファイルに関する情報を取得し、 *buffer*が指す構造体に保管します。 sys\Stat.h で定義されている **_stat**構造には、次のフィールドが含まれています。

|フィールド|意味|
|-|-|
| **st_atime** | ファイルの最後のアクセスの時間。 |
| **st_ctime** | ファイルの作成の時間。 |
| **st_dev** | デバイスの場合は *、fd;* それ以外の場合は 0。 |
| **St_mode** | ファイル モード情報のビット マスク。 *fd*がデバイスを参照する場合 **、_S_IFCHR**ビットが設定されます。 *fd*が通常のファイルを参照する場合 **、_S_IFREG**ビットが設定されます。 読み取り/書き込みのビットは、ファイルのアクセス許可モードに応じて設定されます。 **_S_IFCHR**およびその他の定数は、SYS\Stat.h で定義されます。 |
| **st_mtime** | ファイルの最終変更時刻。 |
| **st_nlink** | 非 NTFS ファイル システムでは常に 1 です。 |
| **st_rdev** | デバイスの場合は *、fd;* それ以外の場合は 0。 |
| **st_size** | ファイルのサイズ (バイト単位)。 |

*fd*がデバイスを参照する場合 **、st_atime**、 **st_ctime**、 **st_mtime**、および**st_size**フィールドは意味を持たない。

Stat.h は Types.h で定義される [_dev_t](../../c-runtime-library/standard-types.md) 型を使用するため、コードで Stat.h の前に Types.h を組み込む必要があります。

**_fstat64**は **、__stat64**構造を使用して、ファイル作成日を 23:59:59、3000 年 12 月 31 日、UTC まで表すことができます。一方、他の関数は 2038 年 UTC 23:59:59 までの日付のみを表します。 これらの関数の日付範囲の下限は、いずれも 1970 年 1 月 1 日の午前 0 時です。

これらの関数のバリエーションは、32 ビットや 64 ビットの時刻型と、32 ビットや 64 ビットのファイル長をサポートします。 最初の数値接尾部 (**32**または**64**) は、使用する時間タイプのサイズを示します。2 番目の接尾部は**i32**または**i64**で、ファイル・サイズが 32 ビットまたは 64 ビット整数のどちらで表されるかを示します。

**_fstat**は **_fstat64i32**と同等で、**構造体****_stat**には 64 ビットの時刻が含まれます。 これは **、_USE_32BIT_TIME_T**が定義されていない限り、その場合は古い動作が有効です。**_fstat**は 32 ビット時間を使用し、**構造体****_stat**には 32 ビットの時刻が含まれます。 **_fstati64**についても同じことが言えます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>_stat の時刻型とファイル長型のバリエーション

|関数|_USE_32BIT_TIME_T が定義されているか|時刻型|ファイル長型|
|---------------|------------------------------------|---------------|----------------------|
|**_fstat**|未定義|64 ビット|32 ビット|
|**_fstat**|定義済み|32 ビット|32 ビット|
|**_fstat32**|マクロ定義の影響を受けない|32 ビット|32 ビット|
|**_fstat64**|マクロ定義の影響を受けない|64 ビット|64 ビット|
|**_fstati64**|未定義|64 ビット|64 ビット|
|**_fstati64**|定義済み|32 ビット|64 ビット|
|**_fstat32i64**|マクロ定義の影響を受けない|32 ビット|64 ビット|
|**_fstat64i32**|マクロ定義の影響を受けない|64 ビット|32 ビット|

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_fstat**|\<sys/stat.h> と \<sys/types.h>|
|**_fstat32**|\<sys/stat.h> と \<sys/types.h>|
|**_fstat64**|\<sys/stat.h> と \<sys/types.h>|
|**_fstati64**|\<sys/stat.h> と \<sys/types.h>|
|**_fstat32i64**|\<sys/stat.h> と \<sys/types.h>|
|**_fstat64i32**|\<sys/stat.h> と \<sys/types.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_fstat.c
// This program uses _fstat to report
// the size of a file named F_STAT.OUT.

#include <io.h>
#include <fcntl.h>
#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <errno.h>
#include <share.h>

int main( void )
{
   struct _stat buf;
   int fd, result;
   char buffer[] = "A line to output";
   char timebuf[26];
   errno_t err;

   _sopen_s( &fd,
             "f_stat.out",
             _O_CREAT | _O_WRONLY | _O_TRUNC,
             _SH_DENYNO,
             _S_IREAD | _S_IWRITE );
   if( fd != -1 )
      _write( fd, buffer, strlen( buffer ) );

   // Get data associated with "fd":
   result = _fstat( fd, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      if (errno == EBADF)
        printf( "Bad file descriptor.\n" );
      else if (errno == EINVAL)
        printf( "Invalid argument to _fstat.\n" );
   }
   else
   {
      printf( "File size     : %ld\n", buf.st_size );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid argument to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
   _close( fd );
}
```

```Output
File size     : 16
Time modified : Wed May 07 15:25:11 2003
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_access、_waccess](access-waccess.md)<br/>
[_chmod、_wchmod](chmod-wchmod.md)<br/>
[_filelength、_filelengthi64](filelength-filelengthi64.md)<br/>
[_stat、_wstat 関数](stat-functions.md)<br/>
