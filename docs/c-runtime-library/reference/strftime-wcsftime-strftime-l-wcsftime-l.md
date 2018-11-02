---
title: strftime、wcsftime、_strftime_l、_wcsftime_l
ms.date: 03/22/2018
apiname:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
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
- _tcsftime
- strftime
- wcsftime
- _strftime_l
- _wcsftime_l
helpviewer_keywords:
- _strftime_l function
- strftime function
- tcsftime function
- _wcsftime_l function
- wcsftime function
- _tcsftime function
- time strings
ms.assetid: 6330ff20-4729-4c4a-82af-932915d893ea
ms.openlocfilehash: 932a7827ef61a5e111f86f8bc44291827843b76e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505665"
---
# <a name="strftime-wcsftime-strftimel-wcsftimel"></a>strftime、wcsftime、_strftime_l、_wcsftime_l

時刻の文字列の書式を指定します。

## <a name="syntax"></a>構文

```C
size_t strftime(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr
);
size_t _strftime_l(
   char *strDest,
   size_t maxsize,
   const char *format,
   const struct tm *timeptr,
   _locale_t locale
);
size_t wcsftime(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr
);
size_t _wcsftime_l(
   wchar_t *strDest,
   size_t maxsize,
   const wchar_t *format,
   const struct tm *timeptr,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*strDest*<br/>
出力する文字列。

*maxsize*<br/>
サイズ、*追加される文字*文字数単位のバッファー (**char**または**wchar_t**)。

*format*<br/>
書式指定文字列。

*timeptr*<br/>
**tm**データ構造体。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strftime**内の文字の数を返します*追加される文字*と**wcsftime**対応するワイド文字数を返します。

場合は、終端の null 文字の合計数は複数の*maxsize*の両方を**strftime**と**wcsftime** 0 とのコンテンツを返す*追加される文字*は不確定です。

文字数*追加される文字*は内のリテラル文字の数と等しく*形式*に追加できる任意の文字と*形式*書式設定コードを使用して。 文字列の終端の NULL は戻り値にはカウントされません。

## <a name="remarks"></a>Remarks

**Strftime**と**wcsftime**関数形式、 **tm**時刻の値*timeptr*に従って、指定された*形式*引数およびバッファー内の結果ストア*追加される文字*します。 多くて、 *maxsize*文字の文字列に配置されます。 内のフィールドの説明について、 *timeptr*構造体は、「 [asctime](asctime-wasctime.md)します。 **wcsftime**のワイド文字と同じ**strftime**; その文字列ポインター引数はワイド文字の文字列を指します。 それ以外では、これらの関数の動作は同じです。

この関数は、パラメーターを検証します。 場合*追加される文字*、*形式*、または*timeptr*が null ポインターの場合は、 **tm**によってアドレス指定されたデータ構造体*timeptr* (たとえば、値が範囲外の時間または日付が含まれる場合)、有効でない場合は、*形式*文字列に無効な書式設定コードが含まれている、無効なパラメーター ハンドラーが呼び出される」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続、関数の戻り値 0 とセットが許可された場合**errno**に**EINVAL**します。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*形式*引数は、コードを 1 つまたは複数の; とで構成されます。 **printf**、書式設定コードの前にパーセント記号 (**%**)。 文字で始まらない**%** をそのままコピーされます*追加される文字*します。 **LC_TIME** 、現在のロケールのカテゴリは、の出力の書式に影響が**strftime**します。 (詳細について**LC_TIME**を参照してください[setlocale](setlocale-wsetlocale.md))。**Strftime**と**wcsftime**関数を使用して、現在設定されているロケール。 **_Strftime_l**と **_wcsftime_l**実行ロケールをパラメーターとして、現在設定されているのではなくを使用する点を除いて、これらの関数バージョンが同じロケール。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**Strftime**関数では、これらのコードの書式指定をサポートします。

|||
|-|-|
|コード|置換文字列|
|**%a**|ロケールで曜日の省略名|
|**%A**|ロケールで曜日の正式な名前|
|**%b**|ロケールでの月の省略名|
|**%B**|ロケールでの月の正式名|
|**%c**|ロケールに合った日付と時刻の表記|
|**%C**|年が 100 で割った値し、10 進数 (00−99) として、整数に切り捨てられます|
|**%d**|10 進数 (01 ~ 31) の月の日|
|**%D**|等価 **%m/%d/%y**|
|**%e**|1 桁の数字、スペースを付けた 10 進数 (1 ~ 31)、月の日|
|**%F**|等価 **%y-%m-%d**|
|**%g**|10 進数の ISO 8601 週に基づく西暦の最後の 2 つの桁 (00 ~ 99)|
|**%G**|10 進数として、ISO 8601 週に基づく年|
|**%h**|月の省略名 (に相当 **%b**)|
|**%H**|24 時間制で時間 (00 ~ 23)|
|**%I**|12 時間形式 (01 ~ 12)|
|**%j**|10 進数 (001 ~ 366) の年の通算日|
|**%m**|1 か月間 10 進数 (01 ~ 12)|
|**%M**|10 進数の分 (00 - 59)|
|**%n**|改行文字 (**\n**)|
|**%p**|ロケールの標識します。 12 時間制のインジケーター|
|**%r**|ロケールの 12 時間制の時間|
|**%R**|等価 **% %m: %m:**|
|**%S**|10 進数として 2 つ目 (00 - 59)|
|**%t**|水平タブ文字 (**\t**)|
|**%T**|等価 **%h: %m: %s**、ISO 8601 時刻の形式|
|**%u**|ISO 8601 曜日の 10 進数 (1 ~ 7 です。月曜日には 1 です)|
|**%U**|10 進数の年の週番号 (00 ~ 53)、最初の日曜日は第 1 週の最初の日|
|**%V**|ISO 8601 週の数を 10 進数 (00 ~ 53)|
|**%w**|10 進数の曜日 (0 ~ 6 です。日曜日は 0 です)|
|**%W**|10 進数の年の週番号 (00 ~ 53)、最初の月曜日は第 1 週の最初の日|
|**%x**|ロケールの形式の日付形式|
|**%X**|ロケールの時刻の表現|
|**%y**|世紀を省いた 10 進数の年 (00 ~ 99)|
|**%Y**|世紀を付けた 10 進数の年|
|**%z**|ISO 8601 形式では、UTC からのオフセット文字がないタイム ゾーンが不明の場合|
|**%Z**|ロケールのタイム ゾーンの名前または; のレジストリ設定に応じて、タイム ゾーンの略称文字がないタイム ゾーンが不明の場合|
|**%%**|パーセント記号|

**Printf**関数の場合、 **#** フラグは、書式コード プレフィックス可能性があります。 その場合、書式コードの説明は次のように変更します。

|[書式コード]|説明|
|-----------------|-------------|
|**% #a**、 **%#A**、 **%#b**、 **%#B**、 **%#g**、 **%#G**、 **%#h**、 **%#n**、 **%#p**、 **%#t**、 **%#u**、 **%#w**、 **%#X**、 **%#z**、 **%#Z**、 **%#%**|**#** フラグは無視されます。|
|**%#c**|時間の長い日付と時刻形式、ロケールに対応します。 たとえば、"Tuesday, March 14, 1995, 12:41:29" です。|
|**%#x**|長い日付形式、ロケールに適切です。 たとえば、"Tuesday, March 14, 1995" です。|
|**%#d**、 **%#D**、 **%#e**、 **%#F**、 **%#H**、 **% #I**、 **%#j**、 **%#m**、 **%#M**、 **%#r**、 **%#R**、 **%#S**、 **%#T**、 **%#U**、 **%#V**、 **%#W**、 **%#y**、 **%#Y**|先頭のゼロまたは空白 (ある場合) を削除します。|

によって生成された、ISO 8601 曜日と年の週に基づく **%V**、 **%g**、および **%G**、第 1 週の曜日を含む年 1 月 4 日、これは、最初が始まりを月曜日を週の使用含む、少なくとも 4 日、年の週。 年の最初の月曜日が 2 番目の場合は、3 番目、または第 4、前の日の一部である前の年の最後の週。 この日の間の **%V** 53 と置き換え **%g**と **%G**は前の年の桁の数字によって置き換えられます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> または \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> または \<wchar.h>|

**_Strftime_l**と **_wcsftime_l**関数は、Microsoft に固有です。 互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[time](time-time32-time64.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md) <br/>
[時間管理](../../c-runtime-library/time-management.md) <br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md) <br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
