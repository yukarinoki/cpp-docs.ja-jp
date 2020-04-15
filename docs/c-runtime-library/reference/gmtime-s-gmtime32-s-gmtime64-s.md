---
title: gmtime_s、_gmtime32_s、_gmtime64_s
ms.date: 4/2/2020
api_name:
- _gmtime32_s
- gmtime_s
- _gmtime64_s
- _o__gmtime32_s
- _o__gmtime64_s
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
- _gmtime_s
- gmtime64_s
- gmtime32_s
- _gmtime64_s
- gmtime_s
- _gmtime32_s
helpviewer_keywords:
- gmtime_s function
- gmtime32_s function
- time functions
- gmtime64_s function
- _gmtime64_s function
- time structure conversion
- _gmtime_s function
- _gmtime32_s function
ms.assetid: 261c7df0-2b0c-44ba-ba61-cb83efaec60f
ms.openlocfilehash: e73d2d3cca852b657631361d8271bec7f9c86ac5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344086"
---
# <a name="gmtime_s-_gmtime32_s-_gmtime64_s"></a>gmtime_s、_gmtime32_s、_gmtime64_s

時間値を**tm**構造体に変換します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md) です。

## <a name="syntax"></a>構文

```C
errno_t gmtime_s(
   struct tm* tmDest,
   const __time_t* sourceTime
);
errno_t _gmtime32_s(
   struct tm* tmDest,
   const __time32_t* sourceTime
);
errno_t _gmtime64_s(
   struct tm* tmDest,
   const __time64_t* sourceTime
);
```

### <a name="parameters"></a>パラメーター

*tmDest*<br/>
[tm](../../c-runtime-library/standard-types.md)構造体へのポインタ。 返された構造体のフィールドには、現地時間ではなく UTC で*タイマー*引数の評価値が保持されます。

*ソースタイム*<br/>
格納されている時刻へのポインター。 時刻は、世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位) を表します。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは Errno.h で定義されています。これらのエラーのリストについては、 [errno](../../c-runtime-library/errno-constants.md)を参照してください。

### <a name="error-conditions"></a>エラー条件

|*tmDest*|*ソースタイム*|戻り値|*tmDest の*値|
|-----------|------------|------------|--------------------|
|**NULL**|any|**Einval**|変更されません。|
|**NULL**でない (有効なメモリを指す)|**NULL**|**Einval**|すべてのフィールドが-1 に設定されます。|
|**NULL**ではありません|< 0|**Einval**|すべてのフィールドが-1 に設定されます。|

最初の 2 つのエラーの場合は、「[Parameter Validation](../../c-runtime-library/parameter-validation.md)」 (パラメーターの検証) に説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し **、EINVAL**を返します。

## <a name="remarks"></a>解説

**_gmtime32_s**関数は *、sourceTime*値を分解し、Time.h で定義された**tm**型の構造体に格納します。 構造体のアドレスは*tmDest*で渡されます。 *sourceTime*の値は、通常、[時刻](time-time32-time64.md)関数の呼び出しから取得されます。

> [!NOTE]
> 対象の環境によって、夏時間が有効かどうか判断されます。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間を計算します。

次の表に示すように、各構造体フィールドの型は**int**です。

|フィールド|説明|
|-|-|
|**tm_sec**|分の後の秒 (0 - 59)。|
|**tm_min**|時間後の分(0 - 59)。|
|**tm_hour**|真夜中から経過した時間 (0 - 23)。|
|**tm_mday**|月の日 (1 から 31)。|
|**tm_mon**|月 (0 - 11;1 月 = 0)。|
|**tm_year**|年 (実際の西暦から 1900 を引いた数)|
|**tm_wday**|曜日 (0 ~ 6;日曜日 = 0)。|
|**tm_yday**|年の日 (0 - 365;1月1日 = 0)。|
|**tm_isdst**|**gmtime_s**の場合は常に 0 です。|

**_gmtime64_s**は **、__time64_t**構造を使用し、日付を 23:59:59、3000、3000、UTC まで表すことができます。gmtime32_s**は**、2038年UTC23:59:59までの日付のみを表します。 これらの関数の日付範囲の下限は、どちらも 1970 年 1 月 1 日の午前 0 時です。

**gmtime_s**はインライン関数で **、_gmtime64_s**と評価され **、time_t**は **__time64_t**と同等です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するようにする必要がある場合は、 **_USE_32BIT_TIME_T**を定義できます。 これを行うと **、gmtime_s**が **_gmtime32_s**にインライン化されます。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**gmtime_s**, **_gmtime32_s**, **_gmtime64_s**|\<time.h>|\<ctime>\<または時間.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

```C
// crt_gmtime64_s.c
// This program uses _gmtime64_s to convert a 64-bit
// integer representation of coordinated universal time
// to a structure named newtime, then uses asctime_s to
// convert this structure to an output string.

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm newtime;
   __int64 ltime;
   char buf[26];
   errno_t err;

   _time64( &ltime );

   // Obtain coordinated universal time:
   err = _gmtime64_s( &newtime, &ltime );
   if (err)
   {
      printf("Invalid Argument to _gmtime64_s.");
   }

   // Convert to an ASCII representation
   err = asctime_s(buf, 26, &newtime);
   if (err)
   {
      printf("Invalid Argument to asctime_s.");
   }

   printf( "Coordinated universal time is %s\n",
           buf );
}
```

```Output
Coordinated universal time is Fri Apr 25 20:12:33 2003
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[_mkgmtime、_mkgmtime32、_mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[mktime、_mktime32、_mktime64](mktime-mktime32-mktime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
