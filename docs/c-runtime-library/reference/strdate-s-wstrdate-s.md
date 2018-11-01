---
title: _strdate_s、_wstrdate_s
ms.date: 11/04/2016
apiname:
- _strdate_s
- _wstrdate_s
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
ms.openlocfilehash: 85c9ab7dcad68f3aa4832236461cd38b07d4ae44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629009"
---
# <a name="strdates-wstrdates"></a>_strdate_s、_wstrdate_s

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

|*バッファー*|*numberOfElements*|Return|内容*バッファー*|
|--------------|------------------------|------------|--------------------------|
|**NULL**|(任意)|**EINVAL**|変更されない|
|いない**NULL** (有効なバッファーを指す)|0|**EINVAL**|変更されない|
|いない**NULL** (有効なバッファーを指す)|0 < *numberOfElements* < 9|**EINVAL**|空の文字列|
|いない**NULL** (有効なバッファーを指す)|*numberOfElements* > 9 を =|0|コメントで指定されている書式設定の、現在の日付|

## <a name="security-issues"></a>セキュリティ上の問題

無効な非を渡して**NULL**値の場合、バッファーが、アクセス違反になるが、 *numberOfElements*パラメーターが 9 よりも大きい。

実際のサイズより大きいサイズの値を渡すことは、*バッファー*バッファー オーバーランが発生します。

## <a name="remarks"></a>Remarks

これらの関数のセキュリティを強化バージョンの提供 **_strdate**と **_wstrdate**します。 **_Strdate_s**関数では、現在のシステム日付が指すバッファーにコピー*バッファー*、書式設定された**mm**/**dd** / **yy**ここで、 **mm** 、月を表す 2 桁の数字は、 **dd**は、日付を表す 2 桁の数字と**yy**西暦の最後の 2 つの桁が。 たとえば、文字列**9905/12/** 1999 年 12 月 5 日を表します。 バッファーの長さは 9 文字以上でなければなりません。

**_wstrdate_s**のワイド文字バージョンは、 **_strdate_s**; の引数と戻り値 **_wstrdate_s**はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

場合*バッファー*は、 **NULL**ポインター、または*numberOfElements* 9 文字未満で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、これらの関数は-1 を返し設定と**errno**に**EINVAL**バッファーが場合**NULL**場合*numberOfElements*が 0、またはセットに小さい**errno**に**ERANGE**場合*numberOfElements*が 9 より小さいです。

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
