---
title: _strdate_s、_wstrdate_s
description: _strdate_sと_wstrdate_sは、現在の日付をバッファーに入れる_strdateおよび_wstrdate関数のセキュアな CRT バージョンです。
ms.date: 4/2/2020
api_name:
- _strdate_s
- _wstrdate_s
- _o__strdate_s
- _o__wstrdate_s
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
- _strdate_s
- wstrdate_s
- _wstrdate_s
- strdate_s
- _tstrdate_s
helpviewer_keywords:
- dates, copying
- tstrdate_s function
- wstrdate_s function
- _tstrdate_s function
- strdate_s function
- copying dates
- _strdate_s function
- _wstrdate_s function
ms.assetid: d41d8ea9-e5ce-40d4-864e-1ac29b455991
ms.openlocfilehash: b4d977ba3546eae17218c63b1786fd26c784d340
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359831"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s、_wstrdate_s

現在のシステム日付をバッファーにコピーします。 これらの機能は _strdate のバージョン[で、](strdate-wstrdate.md)セキュリティが強化された_wstrdate、CRT[のセキュリティ機能で](../../c-runtime-library/security-features-in-the-crt.md)説明されています。

## <a name="syntax"></a>構文

```C
errno_t _strdate_s(
   char *buffer,
   size_t size
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t size
);
template <size_t size>
errno_t _strdate_s(
   char (&buffer)[size]
); // C++ only
template <size_t size>
errno_t _wstrdate_s(
   wchar_t (&buffer)[size]
); // C++ only
```

### <a name="parameters"></a>パラメーター

*バッファー*\
書式設定された日付文字列を格納するバッファーへのポインター。

*サイズ*\
文字単位でのバッファーのサイズ。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。 エラーが発生した場合、戻り値はエラー コードです。 エラー コードは ERRNO.H で定義されます。この関数によって生成される正確なエラーについては、下記の表をご覧ください。 エラー コードの詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」をご覧ください。

## <a name="error-conditions"></a>エラー条件

|*バッファー*|*サイズ*|戻り値|*バッファ*の内容|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(任意)|**Einval**|変更されない|
|**NULL**でない (有効なバッファを指す)|0|**Einval**|変更されない|
|**NULL**でない (有効なバッファを指す)|0 <*サイズ*< 9|**Einval**|空の文字列|
|**NULL**でない (有効なバッファを指す)|*サイズ*>= 9|0|コメントで指定されている書式設定の、現在の日付|

## <a name="security-issues"></a>セキュリティの問題

*バッファ*に対して無効な NULL 以外の値を渡すと *、size*パラメータが 9 より大きい場合にアクセス違反が発生します。

*バッファー*の実際の*サイズ*より大きいサイズの値を渡すと、バッファー オーバーランが生じます。

## <a name="remarks"></a>解説

これらの関数は、より安全なバージョンの **_strdate**と **_wstrdate**を提供します。 **_strdate_s**関数は、現在のシステム日付を*buffer*が指すバッファーにコピーします。 2`mm/dd/yy`桁の月は`mm`、2 桁の日`dd`、`yy`年の最後の 2 桁の数字です。 たとえば、文字列 `12/05/99` は、1999 年 12 月 5 日を表します。 バッファーは、9 文字以上でなければなりません。

**_wstrdate_s**は **、_strdate_s**のワイド文字バージョンです。**_wstrdate_s**の引数と戻り値はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

*buffer*が**NULL**ポインターであるか、*サイズ*が 9 文字未満の場合は、無効なパラメーター・ハンドラーが呼び出されます。 この説明については、「[パラメーターの検証 」を参照](../../c-runtime-library/parameter-validation.md)してください。 実行を続行できる場合、これらの関数は -1 を返します。 バッファーが**NULL の**場合、または*size*が 0 以下の場合は **、errno**を**EINVAL**に設定します。 または、*サイズ*が 9 より小さい場合は**errno**を**ERANGE**に設定します。

C++ では、これらの関数の使用は、テンプレートのオーバーロードによって簡略化されます。 オーバーロードはバッファ長を自動的に推論できるため *、size*引数を指定する必要がなくなります。 また、セキュリティで保護されていない関数を、より新しい、より安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

これらの関数のデバッグ ライブラリ バージョンは、まずバッファーに 0xFE を設定します。 この動作を無効にするには、[_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチン マッピング:

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> または \<wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>例

[time](time-time32-time64.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)\
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)\
[ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)\
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)\
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)\
[mktime, _mktime32, _mktime64](mktime-mktime32-mktime64.md)\
[時間, _time32, _time64](time-time32-time64.md)\
[_tzset](tzset.md)
