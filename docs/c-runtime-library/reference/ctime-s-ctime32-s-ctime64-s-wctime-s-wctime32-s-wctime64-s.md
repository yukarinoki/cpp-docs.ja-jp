---
title: ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s
ms.date: 4/2/2020
api_name:
- _ctime64_s
- _wctime32_s
- ctime_s
- _wctime64_s
- _ctime32_s
- _wctime_s
- _o__ctime32_s
- _o__ctime64_s
- _o__wctime32_s
- _o__wctime64_s
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
- ctime64_s
- _ctime32_s
- _tctime32_s
- _ctime64_s
- _wctime_s
- _tctime_s
- _tctime64_s
- ctime_s
- ctime32_s
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
ms.openlocfilehash: d5121c795ed27c22d20087868f798a4b7f5f5b02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348165"
---
# <a name="ctime_s-_ctime32_s-_ctime64_s-_wctime_s-_wctime32_s-_wctime64_s"></a>ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s

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
26 文字を収納できる大きさが必要です。 文字列の結果への**ポインター。**

- *sourceTime*は、1970 年 1 月 1 日の午前 0 時より前の UTC 日付を表します。

- **_ctime32_s**または **_wctime32_s**を使用し *、sourceTime*が 2038 年 1 月 18 日 23:59:59 以降の日付を表す場合は UTC です。

- **_ctime64_s**または **_wctime64_s**を使用し *、sourceTime*は 23:59:59、3000、UTC の 12 月 31 日以降の日付を表します。

- **_ctime_s**または **_wctime_s**を使用する場合、これらの関数は前の関数のラッパーです。 「解説」を参照してください。

*要素の数*<br/>
バッファーのサイズ。

*ソースタイム*<br/>
格納されている時刻へのポインター。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。 無効なパラメーターに起因して障害が発生した場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます。 実行を継続できる場合は、エラー コードが返されます。 エラー コードは ERRNO.H で定義されます。これらのエラーの一覧については、[errno](../../c-runtime-library/errno-constants.md) を参照してください。 各エラー条件に対してスローされる実際のエラー コードを、次の表に示します。

## <a name="error-conditions"></a>エラー条件

|*バッファー*|*要素の数*|*ソースタイム*|戻り値|*バッファ*内の値|
|--------------|------------------------|------------|------------|-----------------------|
|**NULL**|any|any|**Einval**|変更されない|
|**NULL**でない (有効なメモリを指す)|0|any|**Einval**|変更されない|
|**NULL**ではありません|0< サイズ < 26|any|**Einval**|空の文字列|
|**NULL**ではありません|>= 26|NULL|**Einval**|空の文字列|
|**NULL**ではありません|>= 26|< 0|**Einval**|空の文字列|

## <a name="remarks"></a>解説

**ctime_s**関数は[、time_t](../../c-runtime-library/standard-types.md)構造体として格納された時刻値を文字列に変換します。 *sourceTime*値は、通常、午前 0 時 (00:00:00) 1970 年 1 月 1 日の世界協定時刻 (UTC) から経過した秒数を返す[time](time-time32-time64.md)の呼び出しから取得されます。 戻り値には厳密に 26 文字が含まれ、次の形式になります。

`Wed Jan 02 02:03:55 1980\n\0`

24 時間制が使用されます。 すべてのフィールドには一定の幅があります。 文字列の最後の 2 つの位置には、改行文字 ('\n') と null 文字 ('\0') が入ります。

変換された文字列も、ローカル タイム ゾーンの設定に従って調整されます。 タイム ゾーン環境とグローバル変数の定義については、ローカル時刻の構成と[_tzset](tzset.md)関数の詳細については[、「time](time-time32-time64.md) [、_ftime、](ftime-ftime32-ftime64.md)[およびlocaltime32_s](localtime-s-localtime32-s-localtime64-s.md)関数」を参照してください。

**_wctime32_s**と **_wctime64_s**は **、_ctime32_s**と **_ctime64_s**のワイド文字バージョンです。ワイド文字列へのポインタを返します。 それ以外 **_ctime64_s、**、 **_wctime32_s**、および **_wctime64_s**は **_ctime32_s**と同じように動作します。

**ctime_s**は **、_ctime64_s**に評価され **、time_t**が **__time64_t**と同等のインライン関数です。 コンパイラが古い 32 ビット**time_t**として**time_t**を解釈するようにする必要がある場合は、 **_USE_32BIT_TIME_T**を定義できます。 これを行うと **、ctime_s**が **_ctime32_s**に評価されます。 この方法はお勧めしません。2038 年 1 月 18 日より後にアプリケーションがエラーになる可能性があり、また、64 ビット プラットフォームでは使用できないためです。

C++ では、テンプレートのオーバーロードによってこれらの関数を簡単に使用できます。オーバーロードでは、バッファー長を自動的に推論できるため、サイズ引数を指定する必要がなくなります。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tctime_s**|**ctime_s**|**ctime_s**|**_wctime_s**|
|**_tctime32_s**|**_ctime32_s**|**_ctime32_s**|**_wctime32_s**|
|**_tctime64_s**|**_ctime64_s**|**_ctime64_s**|**_wctime64_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ctime_s**, **_ctime32_s**, **_ctime64_s**|\<time.h>|
|**_wctime_s**, **_wctime32_s**, **_wctime64_s**|\<time.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
