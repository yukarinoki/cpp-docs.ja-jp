---
title: ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64
ms.date: 4/2/2020
api_name:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
- _o__wctime32
- _o__wctime64
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
ms.openlocfilehash: 6056ad8bac6561c0ce2902928364996b2be9ae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348249"
---
# <a name="ctime-_ctime32-_ctime64-_wctime-_wctime32-_wctime64"></a>ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64

時刻値を文字列に変換し、ローカルの時間帯設定に合わせて調整します。 これらの関数には、より安全なバージョンがあります。「[ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)」を参照してください。

## <a name="syntax"></a>構文

```C
char *ctime( const time_t *sourceTime );
char *_ctime32( const __time32_t *sourceTime );
char *_ctime64( const __time64_t *sourceTime );
wchar_t *_wctime( const time_t *sourceTime );
wchar_t *_wctime32( const __time32_t *sourceTime );
wchar_t *_wctime64( const __time64_t *sourceTime );
```

### <a name="parameters"></a>パラメーター

*ソースタイム*<br/>
変換する格納されている時間へのポインター。

## <a name="return-value"></a>戻り値

文字列結果へのポインター。 **NULL**は次の場合に返されます。

- *sourceTime*は、1970 年 1 月 1 日の午前 0 時より前の UTC 日付を表します。

- **_ctime32**または **_wctime32**を使用し *、sourceTime*は 2038 年 1 月 18 日 23:59:59 以降の日付を表します。

- **_ctime64**または **_wctime64**を使用し *、sourceTime*は 23:59:59、3000、UTC の 12 月 31 日以降の日付を表します。

**ctime**はインライン関数で **、_ctime64**と評価され **、time_t**は **__time64_t**と同等です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するようにする必要がある場合は、 **_USE_32BIT_TIME_T**を定義できます。 これを行うと **、ctime**が **_ctime32**に評価されます。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

## <a name="remarks"></a>解説

**ctime**関数は[、time_t](../../c-runtime-library/standard-types.md)値として格納された時刻値を文字列に変換します。 *sourceTime*値は、通常、午前 0 時 (00:00:00) 1970 年 1 月 1 日の世界協定時刻 (UTC) から経過した秒数を返す[time](time-time32-time64.md)の呼び出しから取得されます。 戻り値には厳密に 26 文字が含まれ、次の形式になります。

```Output
Wed Jan 02 02:03:55 1980\n\0
```

24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字 ('\n') と null 文字 ('\0') が入ります。

変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 タイム ゾーン環境とグローバル変数の定義の詳細については、ローカル時刻および[_tzset](tzset.md)関数の構成については[、time](time-time32-time64.md) [、_ftime、](ftime-ftime32-ftime64.md)および[localtime](localtime-localtime32-localtime64.md)関数を参照してください。

**ctime**の呼び出しは **、gmtime**関数と**localtime**関数で使用される単一の静的に割り当てられたバッファーを変更します。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。 **ctime**は **、asctime**関数と静的バッファーを共有します。 したがって **、ctime**の呼び出しは **、asctime**、 **localtime**、または**gmtime**に対する以前の呼び出しの結果を破棄します。

**_wctime**と **_wctime64**は **、ctime**と **_ctime64**のワイド文字バージョンです。ワイド文字列へのポインタを返します。 それ以外**の場合は、_ctime64**、 **_wctime**、**および _wctime64**は**ctime**と同じように動作します。

これらの関数では、パラメーターの検証が行われます。 *sourceTime*が null ポインターの場合、または*sourceTime*値が負の場合、これらの関数は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**ctime**|**ctime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ctime**|\<time.h>|
|**_ctime32**|\<time.h>|
|**_ctime64**|\<time.h>|
|**_wctime**|\<time.h> または \<wchar.h>|
|**_wctime32**|\<time.h> または \<wchar.h>|
|**_wctime64**|\<time.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_ctime64.c
// compile with: /W3
/* This program gets the current
* time in _time64_t form, then uses ctime to
* display the time in string form.
*/

#include <time.h>
#include <stdio.h>

int main( void )
{
   __time64_t ltime;

   _time64( &ltime );
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996
   // Note: _ctime64 is deprecated; consider using _ctime64_s
}
```

```Output
The time is Wed Feb 13 16:04:43 2002
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime、_wasctime](asctime-wasctime.md)<br/>
[ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime、_gmtime32、_gmtime64](gmtime-gmtime32-gmtime64.md)<br/>
[localtime、_localtime32、_localtime64](localtime-localtime32-localtime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
