---
title: _futime、_futime32、_futime64
ms.date: 4/2/2020
api_name:
- _futime64
- _futime32
- _futime
- _o__futime32
- _o__futime64
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- futime
- _futime
- futime64
- _futime64
helpviewer_keywords:
- _futime function
- futime32 function
- futime64 function
- file modification time [C++]
- _futime64 function
- futime function
- _futime32 function
ms.assetid: b942ce8f-5cc7-4fa8-ab47-de5965eded53
ms.openlocfilehash: 1f60bb3b366c48e3d53368f81ebc2528694794f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345499"
---
# <a name="_futime-_futime32-_futime64"></a>_futime、_futime32、_futime64

開いているファイルの変更時刻を設定します。

## <a name="syntax"></a>構文

```C
int _futime(
   int fd,
   struct _utimbuf *filetime
);
int _futime32(
   int fd,
   struct __utimbuf32 *filetime
);
int _futime64(
   int fd,
   struct __utimbuf64 *filetime
);
```

### <a name="parameters"></a>パラメーター

*Fd*<br/>
開いているファイルのファイル記述子。

*Filetime*<br/>
新しい変更日を含む構造体へのポインター。

## <a name="return-value"></a>戻り値

処理が正常に終了した場合は 0 を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行が続行できる場合、関数は -1 を返し **、errno**は**EBADF**に設定され、無効なファイル**記述子を示**します。

## <a name="remarks"></a>解説

**_futime**ルーチンは *、fd*に関連付けられたオープン・ファイルの変更日付とアクセス時刻を設定します。 **_futime**は[_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)と同じですが、その引数はファイル名やファイルへのパスではなく、オープン・ファイルのファイル記述子です。 **_utimbuf**構造には、新しい変更日時およびアクセス時刻のフィールドが含まれます。 両方のフィールドに、有効な値が含まれている必要があります。 **_utimbuf32**と **_utimbuf64**は、それぞれ 32 ビットおよび 64 ビットの時刻型を使用する点を除き **、_utimbuf**と同じです。 **_futime**と **_utimbuf**は 64 ビットの時刻型を使用し **、_futime**動作は **_futime64**と同じです。 以前の動作を強制する必要がある場合は、 **_USE_32BIT_TIME_T**を定義します。 これにより **、_futime****動作が_futime32**に同じになり **、_utimbuf**構造体が 32 ビットの時刻型を使用し **、__utimbuf32**と同等になります。

**_futime64**は **、__utimbuf64**構造を使用し、ファイルの日付を 23:59:59、3000、UTC の 12 月 31 日まで読み取りおよび変更できます。一方 **、_futime32**の呼び出しは、ファイルの日付が 2038 年 UTC 2038 年 1 月 18 日 23:59:59 より後の場合に失敗します。 これらの関数の日付範囲の下限は、1970 年 1 月 1 日の午前 0 時です。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_futime.c
// This program uses _futime to set the
// file-modification time to the current time.

#include <stdio.h>
#include <stdlib.h>
#include <fcntl.h>
#include <io.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/utime.h>
#include <share.h>

int main( void )
{
   int hFile;

   // Show file time before and after.
   system( "dir crt_futime.c_input" );

   _sopen_s( &hFile, "crt_futime.c_input", _O_RDWR, _SH_DENYNO, 0 );

   if( _futime( hFile, NULL ) == -1 )
      perror( "_futime failed\n" );
   else
      printf( "File time modified\n" );

   _close (hFile);

   system( "dir crt_futime.c_input" );
}
```

### <a name="input-crt_futimec_input"></a>Input: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>サンプル出力

```Output
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:40 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
Volume in drive Z has no label.
Volume Serial Number is 5C68-57C1

Directory of Z:\crt

03/25/2004  10:41 AM                24 crt_futime.c_input
               1 File(s)             24 bytes
               0 Dir(s)  24,268,476,416 bytes free
File time modified
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
