---
title: gmtime、_gmtime32、_gmtime64
ms.date: 4/2/2020
api_name:
- _gmtime32
- gmtime
- _gmtime64
- _o__gmtime32
- _o__gmtime64
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
- gmtime
- _gmtime32
- _gmtime64
helpviewer_keywords:
- gmtime32 function
- _gmtime64 function
- gmtime function
- time functions
- _gmtime32 function
- gmtime64 function
- time structure conversion
ms.assetid: 315501f3-477e-475d-a414-ef100ee0db27
ms.openlocfilehash: afa46e583437ebace8edd3a54a6d85e61e02854c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344102"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>gmtime、_gmtime32、_gmtime64

**time_t**時間の値を**tm**構造体に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>パラメーター

*ソースタイム*<br/>
格納されている時刻へのポインター。 時刻は、世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位) を表します。

## <a name="return-value"></a>戻り値

型 [tm](../../c-runtime-library/standard-types.md) 構造体へのポインター。 返された構造体のフィールドには *、sourceTime*引数の評価値が現地時間ではなく UTC で保持されます。 各構造フィールドの型は**int**です。

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
|**tm_isdst**|**gmtime**の場合は常に0.|

32 ビットバージョンと 64 ビットバージョンの**gmtime、mktime、mkgmtime、** および[localtime](localtime-localtime32-localtime64.md)の両方のバージョンでは、変換にスレッドごとに 1 つの共通**tm**構造体が使用されます。 [mktime](mktime-mktime32-mktime64.md) [mkgmtime](mkgmtime-mkgmtime32-mkgmtime64.md) これらの関数を呼び出すたびに、前の呼び出しの結果は破棄されます。 *sourceTime*が 1970 年 1 月 1 日の午前 0 時より前の日付を表す場合 **、gmtime**は**NULL**を返します。 エラーの戻り値はありません。

**_gmtime64**は **、__time64_t**構造を使用して、日付を 23:59:59、3000、3000 年 12 月 31 日 (UTC) まで表しますが **、_gmtime32**は 2038 年 1 月 18 日 (UTC) までの日付のみを表します。 これらの関数の日付範囲の下限は、どちらも 1970 年 1 月 1 日の午前 0 時です。

**gmtime**は _gmtime64**と評価**されるインライン関数で **、_USE_32BIT_TIME_T**定義されていない限り**time_t****は__time64_t**と同等です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するように強制する必要がある場合は **、_USE_32BIT_TIME_T**を定義できますが、その場合は**gmtime**が **_gmtime32**にインライン化され **、time_t__time32_t**として定義されます。 **time_t** この方法は使用しないことをお勧めします。これは 64 ビット プラットフォームでは使用できず、また 2038 年 1 月 18 日以降はアプリケーションでエラーが発生する可能性があるためです。

これらの関数では、パラメーターの検証が行われます。 *sourceTime*が null ポインターの場合、または*sourceTime*値が負の場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

## <a name="remarks"></a>解説

**_gmtime32**関数は *、sourceTime*値を分解し、TIME で定義された**tm**型の静的に割り当てられた構造体に格納します。H。 *sourceTime*の値は、通常、[時間](time-time32-time64.md)関数の呼び出しから取得されます。

> [!NOTE]
> ほとんどの場合は、対象の環境で夏時間が有効かどうかを確認してください。 C ランタイム ライブラリでは、夏時間 (DST) の計算にアメリカ合衆国の規則が使用されていることを前提とします。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**gmtime**, **_gmtime32**, **_gmtime64**|\<time.h>|\<ctime>\<または時間.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
