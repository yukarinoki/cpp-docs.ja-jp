---
title: timespec_get、_timespec32_get、_timespec64_get1
ms.date: 4/2/2020
api_name:
- timespec_get
- _timespec32_get
- _timespec64_get
- _o__timespec32_get
- _o__timespec64_get
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: ca514c60945f25c3d335e0b02110e50ed14f9269
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82911817"
---
# <a name="timespec_get-_timespec32_get-_timespec64_get"></a>timespec_get、_timespec32_get、_timespec64_get

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

成功した場合は*base*の値。それ以外の場合は0を返します。

## <a name="remarks"></a>解説

**Timespec_get**関数は、 *time_spec*引数によって示される構造体の現在の時刻を設定します。 この構造体のすべてのバージョンには、 **tv_sec**と**tv_nsec**の2つのメンバーがあります。 **Tv_sec**値は、秒単位の整数に設定され、*ベース*で指定されたエポックの開始以降、システムクロックの解像度に丸められたナノ秒の整数値に**tv_nsec**ます。

**Microsoft 固有の仕様**

これらの関数では、*ベース*値として**TIME_UTC**のみがサポートされます。 これにより、 *time_spec*の値が、現地時刻 (UTC) のエポックの開始日午前0時 (UTC) から1970年1月1日深夜0時 (UTC) の秒数およびナノ秒数に設定されます。 **構造体** **_timespec32**では、 **tv_sec**は **__time32_t**値です。 **構造体** **_timespec64**では、 **tv_sec**は **__time64_t**値です。 **構造体**の**timespec**では、 **tv_sec**は**time_t**型です。これは、プリプロセッサマクロ _USE_32BIT_TIME_T が定義されているかどうかに応じて、32ビットまたは64ビットの長さになります。 **Timespec_get**関数は、_USE_32BIT_TIME_T が定義されている場合に **_timespec32_get**を呼び出すインライン関数です。それ以外の場合は、 **_timespec64_get**を呼び出します。

**End Microsoft 固有の仕様**

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**timespec_get**、 **_timespec32_get**、 **_timespec64_get**|C: \<time.h>、C++: \<ctime> または \<time.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
