---
title: mktime、_mktime32、_mktime64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mktime32
- mktime
- _mktime64
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
- mktime
- _mktime64
dev_langs:
- C++
helpviewer_keywords:
- _mktime32 function
- mktime function
- time functions
- mktime64 function
- converting times
- mktime32 function
- _mktime64 function
- time, converting
ms.assetid: 284ed5d4-7064-48a2-bd50-15effdae32cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6d02ae8e38a0d3e3b56b5ae69ddd937ef99d76b2
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="mktime-mktime32-mktime64"></a>mktime、_mktime32、_mktime64

現地時刻をカレンダーの値に変換します。

## <a name="syntax"></a>構文

```C
time_t mktime(
   struct tm *timeptr
);
__time32_t _mktime32(
   struct tm *timeptr
);
__time64_t _mktime64(
   struct tm *timeptr
);
```

### <a name="parameters"></a>パラメーター

*timeptr*<br/>
時間構造体へのポインター。「[asctime](asctime-wasctime.md)」をご覧ください。

## <a name="return-value"></a>戻り値

**_mktime32**型の値としてエンコードされた指定されたカレンダー時間を返します[time_t](../../c-runtime-library/standard-types.md)です。 場合*timeptr*午前 0 時、1970 年 1 月 1 日より前に、の日付を参照して、カレンダー時間を表すことができない場合または **_mktime32**型にキャストする-1 を返します**time_t**です。 使用する場合 **_mktime32**場合*timeptr* 23時 59分: 59 2038 年 1 月 18 日世界協定時刻 (UTC) の後の日付を参照型にキャスト-1 を返す**time_t**です。

**_mktime64**型にキャスト-1 が返されます **_ _time64_t**場合*timeptr* UTC 3000 年 12 月 31 日 23時 59分: 59 秒後の日付を参照します。

## <a name="remarks"></a>コメント

**Mktime**、 **_mktime32**と **_mktime64**関数は、指定された時間の構造体 (不完全な可能性があります) によって示される、変換*timeptr*正規化された値を持つ完全に定義された構造体におよびに変換する、 **time_t**カレンダー時間値です。 変換された時間のエンコーディングは、[time](time-time32-time64.md) 関数によって返される値と同じエンコーディングになります。 元の値、 **tm_wday**と**tm_yday**のコンポーネント、 *timeptr*構造は無視され、他のコンポーネントの元の値は制限されていません通常の範囲です。

**mktime**と等価なインライン関数は、 **_mktime64**がない限り、 **_USE_32BIT_TIME_T**が定義されている場合と同じになります **_mktime32**.

UTC に調整した後 **_mktime32**ハンドル日午前 0 時、1970 年 1 月 1 日から 2038 年 1 月 18 日の 23時 59分: 59 (utc)。 **_mktime64**ハンドル日午前 0 時、1970 年 1 月 1 日の 23時 59分: 59 にから 3000 年 12 月 31 日です。 この調整がこれらの関数は-1 を返しますを発生する可能性があります (にキャスト**time_t**、 **_time32_t**または **_ _time64_t**) 場合でも、指定した日付が範囲内です。 たとえば、エジプトのカイロにいる場合は、UTC より 2 時間進んでいるので、*timeptr* で指定した日付から最初に 2 時間が差し引かれます。そのため、日付が範囲外になる可能性があります。

これらの関数は、tm 構造体の検証と値の設定に使用されることがあります。 かどうかは成功すると、これらの関数の値を設定**tm_wday**と**tm_yday**適切し設定を指定されたカレンダー時間を表すその他のコンポーネントが、正常に強制的に引き継ぐとその値範囲です。 最終値**tm_mday**までが設定されていない**表します。**と**tm_year**決定されます。 指定する場合、 **tm**時間構造体は、設定、 **tm_isdst**フィールドを。

- 標準時間が有効であることを示す場合はゼロ (0)。

- 夏時間が有効であることを示す場合は 0 より大きい値。

- 標準時間と夏時間のどちらが有効であるかを C ランタイム ライブラリ コードで計算する場合は 0 より小さい値。

C ランタイム ライブラリは、[TZ](tzset.md) 環境変数から夏時間の状態を判断します。 場合**TZ**が設定されていない Win32 API の呼び出し[GetTimeZoneInformation](http://msdn.microsoft.com/library/windows/desktop/ms724421.aspx)オペレーティング システムから夏時間の時間の情報を取得するために使用します。 これが失敗すると、ライブラリは、夏時間の計算の実装にアメリカ合衆国の規則が使用されると見なします。 **tm_isdst**フィールドは必須です。 設定しないと、その値は未定義になり、これらの関数からは予想外の値が返されます。 場合*timeptr*を指す、 **tm**を以前の呼び出しによって返される構造体[asctime](asctime-wasctime.md)、 [gmtime](gmtime-gmtime32-gmtime64.md)、または[localtime](localtime-localtime32-localtime64.md)(またはこれらの関数のバリアント)、 **tm_isdst**フィールドには、適切な値が含まれています。

なお**gmtime**と**localtime** (および **_gmtime32**、 **_gmtime64**、 **_localtime32**、および **_localtime64**) 変換に 1 つのスレッドの 1 つのバッファーを使用します。 このバッファーを指定する場合**mktime**、 **_mktime32**または **_mktime64**、以前の内容は破棄されます。

これらの関数では、パラメーターの検証が行われます。 *timeptr* が null ポインターである場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、関数は-1 を返します設定と**errno**に**EINVAL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mktime**|\<time.h>|
|**_mktime32**|\<time.h>|
|**_mktime64**|\<time.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_mktime.c
/* The example takes a number of days
* as input and returns the time, the current
* date, and the specified number of days.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   struct tm  when;
   __time64_t now, result;
   int        days;
   char       buff[80];

   time( &now );
   _localtime64_s( &when, &now );
   asctime_s( buff, sizeof(buff), &when );
   printf( "Current time is %s\n", buff );
   days = 20;
   when.tm_mday = when.tm_mday + days;
   if( (result = mktime( &when )) != (time_t)-1 ) {
      asctime_s( buff, sizeof(buff), &when );
      printf( "In %d days the time will be %s\n", days, buff );
   } else
      perror( "mktime failed" );
}
```

### <a name="sample-output"></a>出力例

```Output
Current time is Fri Apr 25 13:34:07 2003

In 20 days the time will be Thu May 15 13:34:07 2003
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[_mkgmtime、_mkgmtime32、_mkgmtime64](mkgmtime-mkgmtime32-mkgmtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
