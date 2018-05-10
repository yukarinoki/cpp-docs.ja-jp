---
title: ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
dev_langs:
- C++
helpviewer_keywords:
- _wctime32_s function
- ctime64_s function
- _tctime64_s function
- _wctime_s function
- tctime_s function
- _wctime64_s function
- ctime_s function
- ctime32_s function
- _ctime64_s function
- tctime64_s function
- wctime64_s function
- wctime_s function
- _tctime_s function
- tctime32_s function
- wctime32_s function
- time, converting
- _ctime32_s function
- _tctime32_s function
ms.assetid: 36ac419a-8000-4389-9fd8-d78b747a009b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3f9c5e6d9d6f0d910decae904cbbd75d995a6c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="ctimes-ctime32s-ctime64s-wctimes-wctime32s-wctime64s"></a>ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s

時刻値を文字列に変換し、ローカルの時間帯設定に合わせて調整します。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [ctime、_ctime64、_wctime、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md) です。

## <a name="syntax"></a>構文

```C
errno_t ctime_s(
   char* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _ctime32_s(
   char* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _ctime64_s(
   char* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime )
;
errno_t _wctime_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const time_t *sourceTime
);
errno_t _wctime32_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time32_t *sourceTime
);
errno_t _wctime64_s(
   wchar_t* buffer,
   size_t numberOfElements,
   const __time64_t *sourceTime
);
```

```cpp
template <size_t size>
errno_t _ctime32_s(
   char (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _ctime64_s(
   char (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime32_s(
   wchar_t (&buffer)[size],
   const __time32_t *sourceTime
); // C++ only
template <size_t size>
errno_t _wctime64_s(
   wchar_t (&buffer)[size],
   const __time64_t *sourceTime
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
26 文字を収納できる大きさが必要です。 文字の文字列の結果へのポインターまたは**NULL**場合。

- *sourceTime* UTC の午前 0 時、1970 年 1 月 1 日より前に、の日付を表します。

- 使用する場合 **_ctime32_s**または **_wctime32_s**と*sourceTime* 23時 59分: 59 2038 年 1 月 18 日 (utc) より後の日付を表します。

- 使用する場合 **_ctime64_s**または **_wctime64_s**と*sourceTime* UTC 3000 年 12 月 31 日 23時 59分: 59 秒後に日付を表します。

- 使用する場合 **_ctime_s**または **_wctime_s**、これらの関数は前の関数のラッパー。 「解説」を参照してください。

*numberOfElements*<br/>
バッファーのサイズ。

*sourceTime*<br/>
格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0。 無効なパラメーターに起因して障害が発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、エラー コードが返されます。 エラー コードは ERRNO.H で定義されます。これらのエラーの一覧については、[errno](../../c-runtime-library/errno-constants.md) を参照してください。 各エラー条件に対してスローされる実際のエラー コードを、次の表に示します。

## <a name="error-conditions"></a>エラー条件

|*バッファー*|*numberOfElements*|*sourceTime*|Return|値で*バッファー*|
|--------------|------------------------|------------|------------|-----------------------|
|**NULL**|任意|任意|**EINVAL**|変更されない|
|いない**NULL** (有効なメモリが指す)|0|任意|**EINVAL**|変更されない|
|いない**NULL**|0< サイズ < 26|任意|**EINVAL**|空の文字列|
|いない**NULL**|>= 26|NULL|**EINVAL**|空の文字列|
|いない**NULL**|>= 26|< 0|**EINVAL**|空の文字列|

## <a name="remarks"></a>コメント

**Ctime_s**関数として格納されている時刻の値を変換する、 [time_t](../../c-runtime-library/standard-types.md)文字の文字列に構造体。 *SourceTime*への呼び出しから値が取得した通常[時間](time-time32-time64.md)、午前 0 時から経過した秒数を返します (00: 00:00)、世界協定時刻 (UTC) 1970 年 1 月 1 日です。 戻り値には厳密に 26 文字が含まれ、次の形式になります。

`Wed Jan 02 02:03:55 1980\n\0`

24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字 ('\n') と null 文字 ('\0') が入ります。

変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 参照してください、[時間](time-time32-time64.md)、 [_ftime](ftime-ftime32-ftime64.md)、および[localtime32_s](localtime-s-localtime32-s-localtime64-s.md)関数のローカル時刻を構成する方法について、 [_tzset](tzset.md)については、タイム ゾーンの環境とグローバル変数を定義する関数。

**_wctime32_s**と **_wctime64_s**のワイド文字バージョンは、 **_ctime32_s**と **_ctime64_s**; ワイド文字の文字列にポインターを返します。 それ以外の場合、 **_ctime64_s**、 **_wctime32_s**、および **_wctime64_s**と同様に動作 **_ctime32_s**です。

**ctime_s**に評価されるインライン関数は、 **_ctime64_s**と**time_t**は等価 **_ _time64_t**です。 強制的に、コンパイラを解釈する必要がある場合**time_t**古い 32 ビットとして**time_t**を定義できます **_USE_32BIT_TIME_T**です。 これにより、その**ctime_s**を評価する **_ctime32_s**です。 ただし、この方法は推奨されません。2038 年 1 月 18 日以降にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ctime_s**、 **_ctime32_s**、 **_ctime64_s**|\<time.h>|
|**_wctime_s**、 **_wctime32_s**、 **_wctime64_s**|\<time.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_wctime_s.c
// This program gets the current
// time in time_t form and then uses _wctime_s to
// display the time in string form.

#include <time.h>
#include <stdio.h>

#define SIZE 26

int main( void )
{
   time_t ltime;
   wchar_t buf[SIZE];
   errno_t err;

   time( &ltime );

   err = _wctime_s( buf, SIZE, &ltime );
   if (err != 0)
   {
      printf("Invalid Arguments for _wctime_s. Error Code: %d\n", err);
   }
   wprintf_s( L"The time is %s\n", buf );
}
```

```Output
The time is Fri Apr 25 13:03:39 2003
```

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime、_ctime32、_ctime64、_wctime、_wctime32、_wctime64](ctime-ctime32-ctime64-wctime-wctime32-wctime64.md)<br/>
[_ftime、_ftime32、_ftime64](ftime-ftime32-ftime64.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
