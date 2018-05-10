---
title: ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64 | Microsoft Doc
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30caa77fee7e15f91ff7c3f089f18fd51a34aa0b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64

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

*sourceTime*<br/>
変換する格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

文字列結果へのポインター。 **NULL**場合に返されます。

- *sourceTime* UTC の午前 0 時、1970 年 1 月 1 日より前に、の日付を表します。

- 使用する場合 **_ctime32**または **_wctime32**と*sourceTime* 23時 59分: 59 2038 年 1 月 18 日 (utc) より後の日付を表します。

- 使用する場合 **_ctime64**または **_wctime64**と*sourceTime* UTC 3000 年 12 月 31 日 23時 59分: 59 秒後に日付を表します。

**ctime**に評価されるインライン関数は、 **_ctime64**と**time_t**は等価 **_ _time64_t**です。 強制的に、コンパイラを解釈する必要がある場合**time_t**古い 32 ビットとして**time_t**を定義できます **_USE_32BIT_TIME_T**です。 これにより、その**ctime**を評価する **_ctime32**です。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

## <a name="remarks"></a>コメント

**Ctime**関数として格納されている時刻の値を変換する、 [time_t](../../c-runtime-library/standard-types.md)を文字列値です。 *SourceTime*への呼び出しから値が取得した通常[時間](time-time32-time64.md)、午前 0 時から経過した秒数を返します (00: 00:00)、世界協定時刻 (UTC) 1970 年 1 月 1 日です。 戻り値には厳密に 26 文字が含まれ、次の形式になります。

```Output
Wed Jan 02 02:03:55 1980\n\0
```

24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字 ('\n') と null 文字 ('\0') が入ります。

変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 参照してください、[時間](time-time32-time64.md)、 [_ftime](ftime-ftime32-ftime64.md)、および[localtime](localtime-localtime32-localtime64.md)関数のローカル時刻を構成する方法について、 [_tzset](tzset.md)の機能タイム ゾーンの環境とグローバル変数を定義する方法の詳細。

呼び出し**ctime**によって使用される 1 つの静的に割り当てられたバッファーの変更、 **gmtime**と**localtime**関数。 これらのルーチンを呼び出すたびに、前の呼び出しの結果は破棄されます。 **ctime**で静的バッファーを共有、 **asctime**関数。 したがってへの呼び出し**ctime**に、前の呼び出しの結果は破棄**asctime**、 **localtime**、または**gmtime**です。

**_wctime**と **_wctime64**のワイド文字バージョンは、 **ctime**と **_ctime64**; ワイド文字の文字列にポインターを返します。 それ以外の場合、 **_ctime64**、 **_wctime**、および **_wctime64**と同様に動作**ctime**です。

これらの関数では、パラメーターの検証が行われます。 場合*sourceTime*が null ポインターの場合は、 *sourceTime*値が負の値、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md). 関数を返すかどうかは、引き続き実行が許可された、 **NULL**設定と**errno**に**EINVAL**です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime**|**ctime**|**ctime**|**_wctime**|
|**_tctime32**|**_ctime32**|**_ctime32**|**_wctime32**|
|**_tctime64**|**_ctime64**|**_ctime64**|**_wctime64**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ctime**|\<time.h>|
|**_ctime32**|\<time.h>|
|**_ctime64**|\<time.h>|
|**_wctime**|\<time.h> または \<wchar.h>|
|**_wctime32**|\<time.h> または \<wchar.h>|
|**_wctime64**|\<time.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
