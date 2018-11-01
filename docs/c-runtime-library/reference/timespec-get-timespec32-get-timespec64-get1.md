---
title: timespec_get、_timespec32_get、_timespec64_get1
ms.date: 11/04/2016
apiname:
- timespec_get
- _timespec32_get
- _timespec64_get
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
- timespec_get
- _timespec32_get
- _timespec64_get
- time/timespec_get
- time/_timespec32_get
- time/_timespec64_get
- timespec
- _timespec32
- _timespec64
helpviewer_keywords:
- timespec_get function
- _timespec32_get function
- _timespec64_get function
ms.assetid: ed757258-b4f2-4c1d-a91b-22ea6ffce4ab
ms.openlocfilehash: c1d0cbaf194060d816e31d397a9319ef47f75371
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638452"
---
# <a name="timespecget-timespec32get-timespec64get"></a>timespec_get、_timespec32_get、_timespec64_get

指定された時間の基準に基づいて、最初の引数が指す間隔を現在のカレンダーの時間に設定します。

## <a name="syntax"></a>構文

```C
int timespec_get(
    struct timespec* const time_spec,
    int const base
);
int _timespec32_get(
    struct _timespec32* const time_spec,
    int const base
);
int _timespec64_get(
    struct _timespec64* const time_spec,
    int const base
);

```

### <a name="parameters"></a>パラメーター

*time_spec*<br/>
エポックの開始以降の時間 (秒およびナノ秒単位) に設定される構造体へのポインター。

*base*<br/>
時間の基準を指定する実装固有の値 (0 以外)。

## <a name="return-value"></a>戻り値

値*基本*かどうか成功すると、それ以外の場合、0 を返します。

## <a name="remarks"></a>Remarks

**Timespec_get**関数によって示される構造体で、現在の時刻の設定、 *time_spec*引数。 この構造体のすべてのバージョンが 2 つのメンバーを持つ**tv_sec**と**tv_nsec**します。 **Tv_sec**秒の整数に値を設定し、 **tv_nsec** によって指定されるエポックの開始以降、システム時計の解像度に丸められますナノ秒の整数に、*基本*します。

**Microsoft 固有の仕様**

これらの関数のサポートのみ**TIME_UTC**として、*基本*値。 これにより設定、 *time_spec*秒およびナノ秒エポックの開始、世界協定時刻 (UTC) の 1970 年 1 月 1 日午前 0 時からの数の値。 **構造体** **_timespec32**、 **tv_sec**は、 **_ _time32_t**値。 **構造体** **_timespec64**、 **tv_sec**は、 **_ _time64_t**値。 **構造体** **timespec**、 **tv_sec**は、 **time_t**型で、32 ビットまたは 64 ビット長かどうかに応じて、プリプロセッサマクロ _USE_32BIT_TIME_T が定義されます。 **Timespec_get**関数がインライン関数を呼び出す **_timespec32_get** _USE_32BIT_TIME_T が定義されている場合は、それ以外の場合、呼び出し **_timespec64_get**します。

**END Microsoft 固有の仕様**

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**timespec_get**、 **_timespec32_get**、 **_timespec64_get**|C: \<time.h>、C++: \<ctime> または \<time.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
