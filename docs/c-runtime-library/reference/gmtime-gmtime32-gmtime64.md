---
title: gmtime、_gmtime32、_gmtime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _gmtime32
- gmtime
- _gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
dev_langs:
- C++
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28ce8b8e2367e1d4dd26672206557867c07827e5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403961"
---
# <a name="gmtime-gmtime32-gmtime64"></a>gmtime、_gmtime32、_gmtime64

変換、 **time_t**時刻の値を**tm**構造体。 これらの関数のセキュリティを強化したバージョンを使用できます。「[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>パラメーター

*sourceTime*<br/>
格納されている時刻へのポインター。 時刻は、世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位) を表します。

## <a name="return-value"></a>戻り値

型 [tm](../../c-runtime-library/standard-types.md) 構造体へのポインター。 返された構造体のフィールドの評価値を保持する、 *sourceTime*引数を現地時刻ではなく UTC でします。 型の構造体のフィールドの各は**int**、次のようにします。

|フィールド|説明|
|-|-|
|**tm_sec**|秒 (0 ~ 59)。|
|**未満**|分 (0 ~ 59)。|
|**tm_hour**|午前 0 時からの経過時間 (0 ~ 23)。|
|**tm_mday**|(1 ~ 31) の月の日です。|
|**表します。**|月 (0 ~ 11 です。年 1 月 = 0) です。|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|
|**tm_wday**|曜日 (0 ~ 6 です。日曜日 = 0) です。|
|**tm_yday**|年の日付 (0 ~ 365 です。1 月 1 日 = 0) です。|
|**tm_isdst**|常に 0 の**gmtime**です。|

32 ビットおよび 64 ビット バージョンの両方**gmtime**、 [mktime](mktime-mktime32-mktime64.md)、 [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md)、および[localtime](localtime-localtime32-localtime64.md)共通の 1 つを使用してすべて**tm**変換のスレッドあたりの構造体。 これらの関数を呼び出すたびに、前の呼び出しの結果は破棄されます。 場合*sourceTime*午前 0 時、1970 年 1 月 1 日より前に、の日付を表す**gmtime**返します**NULL**です。 エラーの戻り値はありません。

**_gmtime64**が使用される、 **_ _time64_t**構造体を UTC で 3000 年 12 月 31 日 23時 59分: 59 秒を表現する日付を有効に対し、 **_gmtime32**のみ 23時 59分: 59 までの日付を表すUTC の 2038 年 1 月 18 日です。 これらの関数の日付範囲の下限は、どちらも 1970 年 1 月 1 日の午前 0 時です。

**gmtime**に評価されるインライン関数は、 **_gmtime64**、および**time_t**は等価 **_ _time64_t**しない限り、 **_USE_32BIT_TIME_T**が定義されています。 場合は、コンパイラを解釈を強制する必要があります**time_t**古い 32 ビットとして**time_t**を定義できます **_USE_32BIT_TIME_T**、そのため、 **gmtime**をインラインである **_gmtime32**と**time_t**として定義する **_time32_t**です。 この方法は使用しないことをお勧めします。これは 64 ビット プラットフォームでは使用できず、また 2038 年 1 月 18 日以降はアプリケーションでエラーが発生する可能性があるためです。

これらの関数では、パラメーターの検証が行われます。 場合*sourceTime*が null ポインターの場合は、 *sourceTime*値が負の値、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 関数を返すかどうかは、引き続き実行が許可された、 **NULL**設定と**errno**に**EINVAL**です。

## <a name="remarks"></a>コメント

**_Gmtime32**関数は分割し、 *sourceTime*値し、型の静的に割り当てられている構造体に格納**tm**時間内に定義されている。H. 値*sourceTime*への呼び出しは通常、[時間](time-time32-time64.md)関数。

> [!NOTE]
> ほとんどの場合は、対象の環境で夏時間が有効かどうかを確認してください。 C ランタイム ライブラリでは、夏時間 (DST) の計算にアメリカ合衆国の規則が使用されていることを前提とします。

## <a name="requirements"></a>要件

|ルーチン|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**gmtime**、 **_gmtime32**、 **_gmtime64**|\<time.h>|\<ctime > または\<time.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_gmtime.c
// compile with: /W3
// This program uses _gmtime64 to convert a long-
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm *newtime;
   __int64 ltime;
   char buff[80];

   _time64( &ltime );

   // Obtain coordinated universal time:
   newtime = _gmtime64( &ltime ); // C4996
   // Note: _gmtime64 is deprecated; consider using _gmtime64_s
   asctime_s( buff, sizeof(buff), newtime );
   printf( "Coordinated universal time is %s\n", buff );
}
```

```Output
Coordinated universal time is Tue Feb 12 23:11:31 2002
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime、_mkgmtime32、_mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime、_mktime32、_mktime64](mktime-mktime32-mktime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
