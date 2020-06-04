---
title: _tzset
ms.date: 4/2/2020
api_name:
- _tzset
- _o__tzset
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
- _tzset
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: d5afc1b05f52d73228abc1a1e102c1578eb2d2dc
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912144"
---
# <a name="_tzset"></a>_tzset

時間環境変数を設定します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void _tzset( void );
```

## <a name="remarks"></a>解説

**_Tzset**関数は、環境変数**TZ**の現在の設定を使用して、 **_daylight**、 **_timezone**、および **_tzname**の3つのグローバル変数に値を割り当てます。 これらの変数は、世界協定時刻 (UTC) から現地時刻への修正や、システム時刻から UTC を計算するための[時間](time-time32-time64.md)関数によって、 [_ftime](ftime-ftime32-ftime64.md)関数と[localtime](localtime-localtime32-localtime64.md)関数によって使用されます。 **TZ**環境変数を設定するには、次の構文を使用します。

> **set TZ =**_tzn_ \[ **+**&#124;**-**]*hh*\[**:**_mm_\[**:**_ss_]] [*dzn*]

|パラメーター|説明|
|-|-|
| *tzn* | PST など、3 文字のタイム ゾーンの名前。 現地時刻から UTC への適切なオフセットを指定する必要があります。 |
| *hh* | UTC と現地時刻の時差。 正の値のための符号 (+) オプション。 |
| *mm* | 分。 *Hh*からコロン (**:**) で区切られます。 |
| *秒* | 秒。 *Mm*からコロン (**:**) で区切られます。 |
| *dzn* | PDT など、3 文字の夏時間のタイム ゾーン。 地域で夏時間が適用されない場合は、 *dzn*の値を指定せずに**TZ**を設定します。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間 (DST) を計算します。 |

> [!NOTE]
> 計算時には時差の符号に注意してください。 時差は現地時刻から UTC に変換する場合のオフセットである (逆ではない) であるため、符号は直感的に考えるものとは逆である場合があります。 UTC より早いタイム ゾーンの場合、時差は負になります。UTC より遅い場合、時差は正になります。

たとえば、 **TZ**環境変数をドイツの現在のタイムゾーンに対応するように設定するには、コマンドラインで次のように入力します。

> **set TZ = GST-1GDT**

このコマンドは、GST によってドイツの標準時刻であることを示し、UTC がドイツの時刻よりも 1 時間遅い (またはドイツは UTC より 1 時間早い) と想定し、さらにドイツでは夏時間が採用されていると想定しています。

**TZ**値が設定されていない場合、 **_tzset**はオペレーティングシステムで指定されたタイムゾーン情報を使用しようとします。 Windows オペレーティング システムの場合、この情報は [コントロール パネル] の [日付/時刻] で指定します。 **_Tzset**がこの情報を取得できない場合、既定では、太平洋標準時ゾーンを示す PST8PDT が使用されます。

**TZ**環境変数の値に基づいて、次の値がグローバル変数 **_daylight**、 **_timezone**、および **_tzname** **_tzset**の呼び出し時に割り当てられます。

|グローバル変数|説明|既定値|
|---------------------|-----------------|-------------------|
|**_daylight**|**TZ**設定で夏時間のタイムゾーンが指定されている場合は0以外の値それ以外の場合は0です。|1|
|**_timezone**|現地時刻と UTC の秒単位での時差。|28800 (28800 秒は 8 時間に相当)|
|**_tzname**[0]|**TZ**環境変数からのタイムゾーン名の文字列値です。**TZ**が設定されていない場合は空です。|PST|
|**_tzname**[1]|夏時間のタイムゾーンの文字列値。**TZ**環境変数から夏時間のタイムゾーンが省略されている場合は空です。|PDT|

上の表に示す **_daylight**および **_tzname**配列の既定値は、"PST8PDT" に対応しています。 DST ゾーンが**TZ**環境変数から省略された場合、 **_daylight**の値は0になり、 [_ftime](ftime-ftime32-ftime64.md)、 [gmtime](gmtime-gmtime32-gmtime64.md)、および[localtime](localtime-localtime32-localtime64.md)関数は、それぞれの dst フラグに対して0を返します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_tzset**|\<time.h>|

**_Tzset**関数は、Microsoft 固有の関数です。 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_tzset.cpp
// This program uses _tzset to set the global variables
// named _daylight, _timezone, and _tzname. Since TZ is
// not being explicitly set, it uses the system time.

#include <time.h>
#include <stdlib.h>
#include <stdio.h>

int main( void )
{
    _tzset();
    int daylight;
    _get_daylight( &daylight );
    printf( "_daylight = %d\n", daylight );
    long timezone;
    _get_timezone( &timezone );
    printf( "_timezone = %ld\n", timezone );
    size_t s;
    char tzname[100];
    _get_tzname( &s, tzname, sizeof(tzname), 0 );
    printf( "_tzname[0] = %s\n", tzname );
    exit( 0 );
}
```

```Output
_daylight = 1
_timezone = 28800
_tzname[0] = Pacific Standard Time
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_utime、_utime32、_utime64、_wutime、_wutime32、_wutime64](utime-utime32-utime64-wutime-wutime32-wutime64.md)<br/>
