---
title: _ftime、_ftime32、_ftime64
ms.date: 11/04/2016
apiname:
- _ftime64
- _ftime
- _ftime32
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
- _ftime32
- _ftime
- _ftime64
- ftime64
- ftime
- ftime32
helpviewer_keywords:
- ftime64 function
- _ftime64 function
- current time
- _ftime function
- ftime function
- _ftime32 function
- ftime32 function
- time, getting current
ms.assetid: 96bc464c-3bcd-41d5-a212-8bbd836b814a
ms.openlocfilehash: 26178f8e559bddd3dafb7fa21edb822874244e93
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332717"
---
# <a name="ftime-ftime32-ftime64"></a>_ftime、_ftime32、_ftime64

現在の時刻を取得します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[_ftime_s、_ftime32_s、_ftime64_s](ftime-s-ftime32-s-ftime64-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void _ftime( struct _timeb *timeptr );
void _ftime32( struct __timeb32 *timeptr );
void _ftime64( struct __timeb64 *timeptr );
```

### <a name="parameters"></a>パラメーター

*timeptr*<br/>
ポインターを **_timeb**、 **__timeb32**、または **_ _timeb64**構造体。

## <a name="remarks"></a>Remarks

**_Ftime**関数は、現在の現地時刻を取得しが指す構造体に格納*timeptr*します。 **_Timeb**、 **__timeb32**、および **_ _timeb64**で構造が定義されている\<sys\\timeb.h >。 これらは、次の表に示す 4 つのフィールドを含んでいます。

|フィールド|説明|
|-|-|
|**dstflag**|ローカルのタイム ゾーンで夏時間が現在有効になっている場合は 0 以外の値です  (夏時間を判断する方法の詳細については、[_tzset](tzset.md) を参照してください)。|
|**millitm**|ミリ秒単位での秒の小数部。|
|**time**|世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位)。|
|**timezone**|西に移動するときの UTC と現地時刻の間の差 (分単位)。 値**タイムゾーン**グローバル変数の値から設定されている **_timezone** (を参照してください **_tzset**)。|

**_Ftime64**関数を使用して、 **_ _timeb64**構造体、ことができますを UTC; 3000 年 12 月 31 日 23時 59分: 59 秒を表すファイルの作成日 **_ftime32**のみの 2038 年 1 月 18 日 23時 59分: 59 までの日付を表します。 これらの関数の日付範囲の下限は、いずれも 1970 年 1 月 1 日の午前 0 時です。

**_Ftime**関数は等価 **_ftime64**、および **_timeb**しない限り、64 ビットの時刻が含まれています **_USE_32BIT_TIME_T**で、定義は、この場合、以前の動作が有効になります。**_ftime**は 32 ビットの時刻を使用し、 **_timeb** 32 ビットの時刻が含まれています。

**_ftime**パラメーターを検証します。 として null ポインターを渡された場合*timeptr*、」の説明に従って、関数は、無効なパラメーター ハンドラーを呼び出す[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は設定**errno**に**EINVAL**します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_ftime**|\<sys/types.h> と \<sys/timeb.h>|
|**_ftime32**|\<sys/types.h> と \<sys/timeb.h>|
|**_ftime64**|\<sys/types.h> と \<sys/timeb.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_ftime.c
// compile with: /W3
// This program uses _ftime to obtain the current
// time and then stores this time in timebuffer.

#include <stdio.h>
#include <sys/timeb.h>
#include <time.h>

int main( void )
{
   struct _timeb timebuffer;
   char timeline[26];
   errno_t err;
   time_t time1;
   unsigned short millitm1;
   short timezone1;
   short dstflag1;

   _ftime( &timebuffer ); // C4996
   // Note: _ftime is deprecated; consider using _ftime_s instead

   time1 = timebuffer.time;
   millitm1 = timebuffer.millitm;
   timezone1 = timebuffer.timezone;
   dstflag1 = timebuffer.dstflag;

   printf( "Seconds since midnight, January 1, 1970 (UTC): %I64d\n",
   time1);
   printf( "Milliseconds: %d\n", millitm1);
   printf( "Minutes between UTC and local time: %d\n", timezone1);
   printf( "Daylight savings time flag (1 means Daylight time is in "
           "effect): %d\n", dstflag1);

   err = ctime_s( timeline, 26, & ( timebuffer.time ) );
   if (err)
   {
       printf("Invalid argument to ctime_s. ");
   }
   printf( "The time is %.19s.%hu %s", timeline, timebuffer.millitm,
           &timeline[20] );
}
```

```Output
Seconds since midnight, January 1, 1970 (UTC): 1051553334
Milliseconds: 230
Minutes between UTC and local time: 480
Daylight savings time flag (1 means Daylight time is in effect): 1
The time is Mon Apr 28 11:08:54.230 2003
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
