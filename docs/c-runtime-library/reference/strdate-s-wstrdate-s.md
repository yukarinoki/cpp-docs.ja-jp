---
title: _strdate_s、_wstrdate_s
ms.date: 11/04/2016
api_name:
- _strdate_s
- _wstrdate_s
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
ms.openlocfilehash: fadd30ec81cff59d675212e59c8513656c7b2f35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940750"
---
# <a name="_strdate_s-_wstrdate_s"></a>_strdate_s、_wstrdate_s

現在のシステム日付をバッファーにコピーします。 これらは、「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) の説明にあるとおり、セキュリティが強化されたバージョンの [_strdate、_wstrdate](strdate-wstrdate.md) です。

## <a name="syntax"></a>構文

```C
errno_t _strdate_s(
   char *buffer,
   size_t numberOfElements
);
errno_t _wstrdate_s(
   wchar_t *buffer,
   size_t numberOfElements
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

*バッファー*<br/>
書式設定された日付文字列が格納されるバッファーへのポインター。

*numberOfElements*<br/>
バッファーのサイズ。

## <a name="return-value"></a>戻り値

正常終了した場合は 0。 障害が発生した場合、戻り値はエラー コードを示します。 エラー コードは ERRNO.H で定義されます。この関数によって生成される正確なエラーについては、下記の表をご覧ください。 エラー コードの詳細については、「[errno 定数](../../c-runtime-library/errno-constants.md)」をご覧ください。

## <a name="error-conditions"></a>エラー条件

|*バッファー*|*numberOfElements*|Return|*バッファー*の内容|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(任意)|**EINVAL**|変更されない|
|Not **NULL** (有効なバッファーを指す)|0|**EINVAL**|変更されない|
|Not **NULL** (有効なバッファーを指す)|0 < *Numberofelements* < 9|**EINVAL**|空の文字列|
|Not **NULL** (有効なバッファーを指す)|*Numberofelements* > = 9|0|コメントで指定されている書式設定の、現在の日付|

## <a name="security-issues"></a>セキュリティ上の問題

*Numberofelements*パラメーターが9よりも大きい場合、バッファーに無効な**NULL**以外の値を渡すとアクセス違反になります。

*バッファー*の実際のサイズより大きいサイズの値を渡すと、バッファーオーバーランが発生します。

## <a name="remarks"></a>Remarks

これらの関数は、より安全なバージョンの **_strdate**と **_wstrdate**を提供します。 **_Strdate_s**関数は、現在のシステム日付を*バッファー*によってポイントされたバッファーにコピーします ( **mm**/**dd**/**yy**形式)。ここで、 **mm**は月を表す2桁、 **dd**は、1日を表す2桁の数字で、 **yy**は年の最後の2桁です。 たとえば、文字列**12/05/99**は1999年12月5日を表します。 バッファーの長さは 9 文字以上でなければなりません。

**_wstrdate_s**は、 **_strdate_s**のワイド文字バージョンです。 **_wstrdate_s**の引数と戻り値はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

*Buffer*が**NULL**ポインターの場合、または*numberofelements*が9文字未満の場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、これらの関数は-1 を返します。また、バッファーが**NULL**であるか、 *numberofelements*が0以下の場合は**errno**を**EINVAL**に設定し、numberofelements の場合は**errno**を**ERANGE**に設定します。が9未満です。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

### <a name="generic-text-routine-mapping"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstrdate_s**|**_strdate_s**|**_strdate_s**|**_wstrdate_s**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_strdate**|\<time.h>|
|**_wstrdate**|\<time.h> または \<wchar.h>|
|**_strdate_s**|\<time.h>|

## <a name="example"></a>例

[time](time-time32-time64.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[時間管理](../../c-runtime-library/time-management.md)<br/>
[asctime_s、_wasctime_s](asctime-s-wasctime-s.md)<br/>
[ctime_s、_ctime32_s、_ctime64_s、_wctime_s、_wctime32_s、_wctime64_s](ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)<br/>
[gmtime_s、_gmtime32_s、_gmtime64_s](gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s、_localtime32_s、_localtime64_s](localtime-s-localtime32-s-localtime64-s.md)<br/>
[mktime、_mktime32、_mktime64](mktime-mktime32-mktime64.md)<br/>
[time、_time32、_time64](time-time32-time64.md)<br/>
[_tzset](tzset.md)<br/>
