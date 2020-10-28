---
title: gmtime、_gmtime32、_gmtime64
description: '`gmtime` `_gmtime32` `_gmtime64` 値を `time_t` 構造体に変換する `tm` 、、およびの API リファレンス。'
ms.date: 10/27/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: bb8bee6b752f64d85dfb0f8c9e5ba7acf204a76f
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907546"
---
# <a name="gmtime-_gmtime32-_gmtime64"></a>`gmtime`, `_gmtime32`, `_gmtime64`

`time_t`時刻値を `tm` 構造体に変換します。 これらの関数のセキュリティを強化したバージョンを使用できます。「 [」、「」を参照し `gmtime_s` てください。 `_gmtime32_s` `_gmtime64_s` ](gmtime-s-gmtime32-s-gmtime64-s.md)

## <a name="syntax"></a>構文

```C
struct tm *gmtime( const time_t *sourceTime );
struct tm *_gmtime32( const __time32_t *sourceTime );
struct tm *_gmtime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>パラメーター

*`sourceTime`*\
格納されている時刻へのポインター。 時刻は、世界協定時刻 (UTC: Coordinated Universal Time) の 1970 年 1 月 1 日の深夜 00:00:00 から経過した時間 (秒単位) を表します。

## <a name="return-value"></a>戻り値

型の構造体へのポインター [`tm`](../../c-runtime-library/standard-types.md) 。 返される構造体のフィールドには、引数の評価値が *`sourceTime`* 現地時刻ではなく UTC で格納されます。 構造体の各フィールドは `int` 型で、次のとおりです:

|フィールド|説明|
|-|-|
|`tm_sec`|秒後 (0-59)。|
|`tm_min`|分後 (0-59)。|
|`tm_hour`|深夜からの時間 (0-23)。|
|`tm_mday`|月の通算日 (1-31)。|
|`tm_mon`|月 (0-11;1月 = 0)。|
|`tm_year`|年 (実際の西暦から 1900 を引いた数)|
|`tm_wday`|曜日 (0-6;日曜日 = 0)。|
|`tm_yday`|年の通算日 (0-365;1月1日 = 0)。|
|`tm_isdst`|**Gmtime** の場合は常に0です。|

、、、およびの32ビットバージョンと64ビットバージョンは、いずれも、 **`gmtime`** [`mktime`](mktime-mktime32-mktime64.md) [`mkgmtime`](mkgmtime-mkgmtime32-mkgmtime64.md) [`localtime`](localtime-localtime32-localtime64.md) `tm` 変換のためにスレッドごとに1つの共通構造を使用します。 これらの関数を呼び出すたびに、前の呼び出しの結果は破棄されます。 が *`sourceTime`* 1970 年1月1日の午前0時より前の日付を表している場合、は **`gmtime`** を返し `NULL` ます。 エラーの戻り値はありません。

構造体を使用する **_gmtime64** では `__time64_t` 、23:59:59 年12月 31 3000 日の UTC で日付を表すことができます。 **`_gmtime32`** は、23:59:59 年1月 2038 18 日からまでの日付のみを表します。 これらの関数の日付範囲の下限は、どちらも 1970 年 1 月 1 日の午前 0 時です。

**`gmtime`** はに評価されるインライン関数であり、は **`_gmtime64`** `time_t` `__time64_t` が定義されている場合を除き、と同じです `_USE_32BIT_TIME_T` 。 コンパイラが古い32ビットとして解釈されるようにする必要がある場合は `time_t` `time_t` 、を定義できますが、これを行うと、がとして定義され、として `_USE_32BIT_TIME_T` 定義されるようになり **`gmtime`** **`_gmtime32`** `time_t` `__time32_t` ます。 64ビットプラットフォームでは許可されていないため、この方法はお勧めしません。 いずれの場合も、2038年1月18日以降、アプリケーションが失敗する可能性があります。

これらの関数では、パラメーターの検証が行われます。 *`sourceTime`* が null ポインターの場合、または *`sourceTime`* 値が負の場合、「パラメーターの [検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、これらの関数は無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、関数は `NULL` を返し、`errno` を `EINVAL` に設定します。

## <a name="remarks"></a>解説

関数は、 **`_gmtime32`** 値を分解 *`sourceTime`* し、 `tm` で定義されている型の静的に割り当てられた構造体に格納し `TIME.H` ます。 の値は、 *`sourceTime`* 通常、関数の呼び出しから取得され [`time`](time-time32-time64.md) ます。

> [!NOTE]
> ほとんどの場合は、対象の環境で夏時間が有効かどうかを確認してください。 C ランタイム ライブラリでは、夏時間 (DST) の計算にアメリカ合衆国の規則が使用されていることを前提とします。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須の C ヘッダー|必須の C++ ヘッダー|
|-------------|---------------------|-|
|**`gmtime`** , **`_gmtime32`** , **`_gmtime64`**|`<time.h>`| `<ctime>` または `<time.h>`|

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

int main(void)
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

[時間管理](../../c-runtime-library/time-management.md)\
[`asctime`, `_wasctime`](asctime-wasctime.md)\
[`ctime`, `_ctime32`, `_ctime64`, `_wctime`, `_wctime32`, `_wctime64`](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)\
[`_ftime`, `_ftime32`, `_ftime64`](ftime-ftime32-ftime64.md)\
[`gmtime_s`, `_gmtime32_s`, `_gmtime64_s`](gmtime-s-gmtime32-s-gmtime64-s.md)\
[`localtime`, `_localtime32`, `_localtime64`](localtime-localtime32-localtime64.md)\
[`_mkgmtime`, `_mkgmtime32`, `_mkgmtime64`](mkgmtime-mkgmtime32-mkgmtime64.md)\
[`mktime`, `_mktime32`, `_mktime64`](mktime-mktime32-mktime64.md)\
[`time`, `_time32`, `_time64`](time-time32-time64.md)
