---
title: _futime、_futime32、_futime64
ms.date: 11/04/2016
apiname:
- _futime64
- _futime32
- _futime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: f21e394acdcc7fbf8a91c5450a4c04daa050db21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332677"
---
# <a name="futime-futime32-futime64"></a>_futime、_futime32、_futime64

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

*fd*<br/>
開いているファイルのファイル記述子。

*filetime*<br/>
新しい変更日を含む構造体へのポインター。

## <a name="return-value"></a>戻り値

処理が正常に終了した場合は 0 を返します。 エラーが発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は-1 を返しますと**errno**に設定されている**EBADF**、無効なファイル記述子を示すまたは**EINVAL**無効なことを示すパラメーター。

## <a name="remarks"></a>Remarks

**_Futime**ルーチンに関連付けられている開いているファイルの変更日とアクセス時間を設定する*fd*します。 **_futime**ヲェヒェケェ ・ [_utime](utime-utime32-utime64-wutime-wutime32-wutime64.md)の引数は、開いているファイルのファイル記述子ではなく、ファイルまたはファイルへのパスの名前を点が異なります。 **_Utimbuf**構造体には新しい変更日とアクセス時刻のフィールドが含まれています。 両方のフィールドに、有効な値が含まれている必要があります。 **_utimbuf32**と **_utimbuf64**と同じ **_utimbuf**それぞれを除くの 32 ビットおよび 64 ビットの時刻型を使用します。 **_futime**と **_utimbuf** 64 ビット時刻型を使用し、 **_futime**動作と同じ **_futime64**。 以前の動作を強制する必要がある場合は、定義 **_USE_32BIT_TIME_T**します。 これにより **_futime**動作と同じでなければ **_futime32**により、 **_utimbuf** と同じですので、32ビット時刻型を使用する構造体 **__utimbuf32**します。

**_futime64**、使用、 **_ _utimbuf64**構造体を読み取り、変更は UTC 3000 年 12 月 31 日 23時 59分: 59 秒までの日付のファイルへの呼び出し **_futime32**場合は、ファイルの日付が失敗しました。2038 年 1 月 18 日 23時 59分: 59 までよりも後。 これらの関数の日付範囲の下限は、1970 年 1 月 1 日の午前 0 時です。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**_futime**|\<sys/utime.h>|\<errno.h>|
|**_futime32**|\<sys/utime.h>|\<errno.h>|
|**_futime64**|\<sys/utime.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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

### <a name="input-crtfutimecinput"></a>Input: crt_futime.c_input

```Input
Arbitrary file contents.
```

### <a name="sample-output"></a>出力例

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
