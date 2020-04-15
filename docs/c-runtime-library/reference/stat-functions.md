---
title: _stat、_stat32、_stat64、_stati64、_stat32i64、_stat64i32、_wstat、_wstat32、_wstat64、_wstati64、_wstat32i64、_wstat64i32
ms.date: 4/2/2020
api_name:
- _wstat64
- _stati64
- _stat32
- _stat32i64
- _stat
- _wstati64
- _wstat32
- _wstat64i32
- _wstat
- _stat64
- _stat64i32
- _wstat32i64
- _o__stat32
- _o__stat32i64
- _o__stat64
- _o__stat64i32
- _o__wstat32
- _o__wstat32i64
- _o__wstat64
- _o__wstat64i32
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
- tstat32
- tstat
- _tstat64i32
- tstati64
- _wstat64
- _wstat32
- wstati64
- tstat64
- _stati64
- _wstat
- wstat64i32
- stat32i64
- tstat32i64
- _tstat
- _wstati64
- _tstati64
- _wstat32i64
- wstat32
- _wstat64i32
- _stat
- _tstat32
- stat64i32
- wstat64
- stat
- _stat32i64
- _stat32
- stati64
- wstat
- _stat64i32
- stat32
- _tstat32i64
- tstat64i32
- _tstat64
- _stat64
- stat/_stat
- stat/_stat32
- stat/_stat64
- stat/_stati64
- stat/_stat32i64
- stat/_stat64i32
- stat/_wstat
- stat/_wstat32
- stat/_wstat64
- stat/_wstati64
- stat/_wstat32i64
- stat/_wstat64i32
helpviewer_keywords:
- files [C++], status information
- _stat function
- _wstat function
- _stat64i32 function
- tstat function
- _tstat64i32 function
- _stati64 function
- _stat64 function
- tstati64 function
- wstati64 function
- wstat64 function
- _wstat64i32 function
- _tstat32i64 function
- _stat32i64 function
- stat function
- status of files
- _tstat32 function
- tstat64 function
- _wstat64 function
- _tstat function
- _stat32 function
- wstat function
- _wstat32i64 function
- _tstati64 function
- _wstat32 function
- stat64 function
- stati64 function
- _wstati64 function
- _tstat64 function
- files [C++], getting status information
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
ms.openlocfilehash: 32a96a93eb8a18e366ac7a075b414dbca732fb61
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355410"
---
# <a name="_stat-_stat32-_stat64-_stati64-_stat32i64-_stat64i32-_wstat-_wstat32-_wstat64-_wstati64-_wstat32i64-_wstat64i32"></a>_stat、_stat32、_stat64、_stati64、_stat32i64、_stat64i32、_wstat、_wstat32、_wstat64、_wstati64、_wstat32i64、_wstat64i32

ファイルのステータス情報を取得します。

## <a name="syntax"></a>構文

```C
int _stat(
   const char *path,
   struct _stat *buffer
);
int _stat32(
   const char *path,
   struct __stat32 *buffer
);
int _stat64(
   const char *path,
   struct __stat64 *buffer
);
int _stati64(
   const char *path,
   struct _stati64 *buffer
);
int _stat32i64(
   const char *path,
   struct _stat32i64 *buffer
);
int _stat64i32(
   const char *path,
   struct _stat64i32 *buffer
);
int _wstat(
   const wchar_t *path,
   struct _stat *buffer
);
int _wstat32(
   const wchar_t *path,
   struct __stat32 *buffer
);
int _wstat64(
   const wchar_t *path,
   struct __stat64 *buffer
);
int _wstati64(
   const wchar_t *path,
   struct _stati64 *buffer
);
int _wstat32i64(
   const wchar_t *path,
   struct _stat32i64 *buffer
);
int _wstat64i32(
   const wchar_t *path,
   struct _stat64i32 *buffer
);
```

### <a name="parameters"></a>パラメーター

*path*<br/>
既存のファイルやディレクトリのパスを含む文字列へのポインター。

*バッファー*<br/>
結果を格納する構造体へのポインター。

## <a name="return-value"></a>戻り値

これらの各関数は、ファイルのステータス情報が取得されると、0 を返します。 戻り値 -1 はエラーを示し、その場合**errno**は**ENOENT**に設定され、ファイル名またはパスが見つからなかったことを示します。 **EINVAL**の戻り値は、無効なパラメーターを示します。この場合 **、errno**も**EINVAL**に設定されます。

このコード、およびその他の戻りコードの詳細については[、_doserrno、errno、_sys_errlist、および_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)を参照してください。

ファイルの日付スタンプは、1970 年 1 月 1 日の午前 0 時より遅く、23:59:59、3000 年 12 月 31 日 **、_wstat32** **_stat32** UTC **_USE_32BIT_TIME_T**の前に表すことができます。

## <a name="remarks"></a>解説

**_stat**関数は *、path*で指定されたファイルまたはディレクトリに関する情報を取得し、 *buffer*が指す構造体に格納します。 **_stat**は、マルチバイト文字の文字列引数を適切に処理し、現在使用中のマルチバイト コード ページに従ってマルチバイト文字シーケンスを認識します。

**_wstat**はワイド文字の **_stat**です。**_wstat**への*パス*引数はワイド文字ストリングです。 **_wstat**と **_stat**は **、_wstat**がマルチバイト文字文字列を処理しないことを除いて、同じように動作します。

これらの関数のバリエーションは、32 ビットや 64 ビットの時刻型と、32 ビットや 64 ビットのファイル長をサポートします。 最初の数値接尾部 (**32**または**64**) は、使用する時間タイプのサイズを示します。2 番目の接尾部は**i32**または**i64**で、ファイル・サイズが 32 ビットまたは 64 ビット整数のどちらで表されるかを示します。

**_stat**は **_stat64i32**と同じで、**構造体****_stat**には 64 ビットの時刻が含まれます。 これは **、_USE_32BIT_TIME_T**が定義されていない限り、その場合は古い動作が有効です。**_stat**は 32 ビット時間を使用し、**構造体****_stat**には 32 ビットの時刻が含まれます。 同じことが **_stati64**にも当てはまります。

> [!NOTE]
> **_wstat**は、Windows Vista シンボリック リンクでは動作しません。 このような場合 **、_wstat**は常にファイル サイズ 0 を報告します。 **シン**ボリックリンクでは_statが正しく機能します。

この関数は、パラメーターを検証します。 *パス*または*バッファー*のいずれかが**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="time-type-and-file-length-type-variations-of-_stat"></a>_stat の時刻型とファイル長型のバリエーション

|関数|_USE_32BIT_TIME_T が定義されているか|時刻型|ファイル長型|
|---------------|------------------------------------|---------------|----------------------|
|**_stat**, **_wstat**|未定義|64 ビット|32 ビット|
|**_stat**, **_wstat**|定義済み|32 ビット|32 ビット|
|**_stat32**, **_wstat32**|マクロ定義の影響を受けない|32 ビット|32 ビット|
|**_stat64**, **_wstat64**|マクロ定義の影響を受けない|64 ビット|64 ビット|
|**_stati64**, **_wstati64**|未定義|64 ビット|64 ビット|
|**_stati64**, **_wstati64**|定義済み|32 ビット|64 ビット|
|**_stat32i64** **,_wstat32i64**|マクロ定義の影響を受けない|32 ビット|64 ビット|
|**_stat64i32**, **_wstat64i32**|マクロ定義の影響を受けない|64 ビット|32 ビット|

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstat**|**_stat**|**_stat**|**_wstat**|
|**_tstat64**|**_stat64**|**_stat64**|**_wstat64**|
|**_tstati64**|**_stati64**|**_stati64**|**_wstati64**|
|**_tstat32i64**|**_stat32i64**|**_stat32i64**|**_wstat32i64**|
|**_tstat64i32**|**_stat64i32**|**_stat64i32**|**_wstat64i32**|

SYS\STAT で定義されている **_stat**構造。Hは、以下のフィールドを含む。

|フィールド||
|-|-|
| **st_gid** | ファイル (UNIX 固有) を所有するグループの数値 ID。Windows システムでは、このフィールドは常に 0 になります。 リダイレクトされたファイルは、Windows ファイルとして分類されます。 |
| **st_atime** | ファイルに最後にアクセスした時刻。 NTFS では有効ですが、FAT 形式のディスク ドライブでは無効です。 |
| **st_ctime** | ファイルの作成時刻。 NTFS では有効ですが、FAT 形式のディスク ドライブでは無効です。 |
| **st_dev** | ファイルを含むディスクのドライブ番号 **(st_rdev**と同じ)。 |
| **st_ino** | ファイルの情報ノード **(inode)** の番号 (UNIX 固有) UNIX ファイルシステムでは **、inode**はファイルの日付と時刻のスタンプ、アクセス権、およびコンテンツを記述します。 ファイルが互いにハードリンクされている場合、それらは同じ**inode**を共有します。 **inode**、つまり**st_ino**は、FAT、HPFS、またはNTFSファイルシステムでは意味を持ちません。 |
| **St_mode** | ファイル モード情報のビット マスク。 *パス*がディレクトリを指定している場合は **、_S_IFDIR**ビットが設定されます。*path*が通常のファイルまたはデバイスを指定する場合は **、_S_IFREG**ビットが設定されます。 ユーザーの読み取り/書き込みビットは、ファイルのアクセス許可モードに応じて設定されます。ユーザー実行ビットは、ファイル名の拡張子に応じて設定されます。 |
| **st_mtime** | ファイルの最終変更時刻。 |
| **st_nlink** | 非 NTFS ファイル システムでは常に 1 です。 |
| **st_rdev** | ファイルを含むディスクのドライブ番号 **(st_dev**と同じ)。 |
| **st_size** | ファイルのサイズ (バイト単位)。**i64**サフィックスを持つバリエーションの 64 ビット整数。 |
| **st_uid** | ファイルを所有するユーザーの数値識別子 (UNIX 固有)。 Windows システムでは、このフィールドは常に 0 です。 リダイレクトされたファイルは、Windows ファイルとして分類されます。 |

*path*がデバイスを参照する場合 **、_stat**構造の**st_size**、さまざまな時刻フィールド **、st_dev、** および**st_rdev**フィールドは意味を持ちません。 STAT.H は TYPES.H で定義されている [_dev_t](../../c-runtime-library/standard-types.md) 型を使用するため、コードで STAT.H の前に TYPES.H を組み込む必要があります。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_stat**, **_stat32**, **_stat64**, **_stati64**, **_stat32i64**, **_stat64i32**|\<sys/types.h>、その後に \<sys/stat.h>|\<errno.h>|
|**_wstat**, **_wstat32**, **_wstat64**, **_wstati64** **,** **_wstat32i64**, _wstat64i32|\<sys/types.h>、その後に \<sys/stat.h> または \<wchar.h>|\<errno.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_stat.c
// This program uses the _stat function to
// report information about the file named crt_stat.c.

#include <time.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
   struct _stat buf;
   int result;
   char timebuf[26];
   char* filename = "crt_stat.c";
   errno_t err;

   // Get data associated with "crt_stat.c":
   result = _stat( filename, &buf );

   // Check if statistics are valid:
   if( result != 0 )
   {
      perror( "Problem getting information" );
      switch (errno)
      {
         case ENOENT:
           printf("File %s not found.\n", filename);
           break;
         case EINVAL:
           printf("Invalid parameter to _stat.\n");
           break;
         default:
           /* Should never be reached. */
           printf("Unexpected error in _stat.\n");
      }
   }
   else
   {
      // Output some of the statistics:
      printf( "File size     : %ld\n", buf.st_size );
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );
      err = ctime_s(timebuf, 26, &buf.st_mtime);
      if (err)
      {
         printf("Invalid arguments to ctime_s.");
         exit(1);
      }
      printf( "Time modified : %s", timebuf );
   }
}
```

```Output
File size     : 732
Drive         : C:
Time modified : Thu Feb 07 14:39:36 2002
```

## <a name="see-also"></a>関連項目

[ファイル処理](../../c-runtime-library/file-handling.md)<br/>
[_access、_waccess](access-waccess.md)<br/>
[_fstat、_fstat32、_fstat64、_fstati64、_fstat32i64、_fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_setmbcp](setmbcp.md)<br/>
