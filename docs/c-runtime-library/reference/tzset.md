---
title: _tzset
ms.date: 11/04/2016
apiname:
- _tzset
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
- _tzset
helpviewer_keywords:
- _tzset function
- time environment variables
- environment variables, setting time
ms.assetid: 3f6ed537-b414-444d-b272-5dd377481930
ms.openlocfilehash: 6312297e6daa9b4790674bd26d21812d5bee34c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385194"
---
# <a name="tzset"></a>_tzset

時間環境変数を設定します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
void _tzset( void );
```

## <a name="remarks"></a>Remarks

**_Tzset**関数は、環境変数の現在の設定を使用して**TZ** 3 つのグローバル変数に値を割り当てる: **_daylight**、 **_timezone**、および **_tzname**します。 これらの変数を使用して、 [_ftime](ftime-ftime32-ftime64.md)と[localtime](localtime-localtime32-localtime64.md)関数を現地時刻と世界協定時刻 (UTC) から修正を行う、[時間](time-time32-time64.md)関数システム時刻から UTC を計算します。 次の構文を使用して、設定、 **TZ**環境変数。

> **TZ 設定 =**_tzn_ \[ **+** &#124; **-**]*hh* \[ **:**_mm_\[**:**_ss_] [*dzn*]

|パラメーター|説明|
|-|-|
| *tzn* | PST など、3 文字のタイム ゾーンの名前。 現地時刻から UTC への適切なオフセットを指定する必要があります。 |
| *hh* | UTC と現地時刻の時差。 正の値のための符号 (+) オプション。 |
| *mm* | 分。 分離*hh*コロン (**:**)。 |
| *ss* | 秒。 分離*mm*コロン (**:**)。 |
| *dzn* | PDT など、3 文字の夏時間のタイム ゾーン。 夏時間が有効で、局所性にされてない場合は、設定**TZ**の値がない*dzn*します。 C ランタイム ライブラリでは、アメリカ合衆国の規則を前提に夏時間 (DST) を計算します。 |

> [!NOTE]
> 計算時には時差の符号に注意してください。 時差は現地時刻から UTC に変換する場合のオフセットである (逆ではない) であるため、符号は直感的に考えるものとは逆である場合があります。 UTC より早いタイム ゾーンの場合、時差は負になります。UTC より遅い場合、時差は正になります。

たとえば、設定するため、 **TZ**ドイツでは、現在のタイム ゾーンに対応する環境変数は、コマンドラインで、次を入力してください。

> **TZ 設定 GST 1GDT を =**

このコマンドは、GST によってドイツの標準時刻であることを示し、UTC がドイツの時刻よりも 1 時間遅い (またはドイツは UTC より 1 時間早い) と想定し、さらにドイツでは夏時間が採用されていると想定しています。

場合、 **TZ**値が設定されていない **_tzset**オペレーティング システムで指定されたタイム ゾーン情報を使用します。 Windows オペレーティング システムの場合、この情報は [コントロール パネル] の [日付/時刻] で指定します。 場合 **_tzset** 、この情報を取得できない既定では、太平洋標準時ゾーン PST8PDT が使用されます。

に基づいて、 **TZ**環境変数の値では、次の値がグローバル変数に割り当てられている **_daylight**、 **_timezone**、および **_tzname**とき **_tzset**が呼び出されます。

|グローバル変数|説明|既定値|
|---------------------|-----------------|-------------------|
|**_daylight**|0 以外の値に夏時間のタイム ゾーンが指定されている場合**TZ** ; の設定は 0。|1|
|**_timezone**|現地時刻と UTC の秒単位での時差。|28800 (28800 秒は 8 時間に相当)|
|**_tzname**[0]|タイム ゾーン名の文字列値**TZ**環境変数に空の場合**TZ**が設定されていません。|PST|
|**_tzname**[1]|夏時間のタイム ゾーンの文字列値夏時間のタイム ゾーンが省略されている場合は、空**TZ**環境変数。|PDT|

前の表に示すように既定値 **_daylight**と **_tzname**配列は"PST8PDT"に対応。 DST のゾーンがから省略した場合、 **TZ**環境変数の値は、 **_daylight** 0 は、および[_ftime](ftime-ftime32-ftime64.md)、 [gmtime](gmtime-gmtime32-gmtime64.md)と[localtime](localtime-localtime32-localtime64.md)関数は、それぞれの DST フラグに対して 0 を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_tzset**|\<time.h>|

**_Tzset**関数は、Microsoft に固有です。 詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
