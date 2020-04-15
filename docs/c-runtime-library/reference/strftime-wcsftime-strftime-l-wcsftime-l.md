---
title: strftime、wcsftime、_strftime_l、_wcsftime_l
ms.date: 4/2/2020
api_name:
- strftime
- _wcsftime_l
- _strftime_l
- wcsftime
- _o__strftime_l
- _o__wcsftime_l
- _o_strftime
- _o_wcsftime
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
ms.openlocfilehash: 5da2c128c54fd88bb874b360f5a966f17b14a935
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350013"
---
# <a name="strftime-wcsftime-_strftime_l-_wcsftime_l"></a>strftime、wcsftime、_strftime_l、_wcsftime_l

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

*最も多くの人*<br/>
出力する文字列。

*Maxsize*<br/>
*strDest*バッファのサイズ (**文字**または**wchar_t)** を文字数で指定します。

*形式*<br/>
書式指定文字列。

*timeptr*<br/>
**tm**データ構造。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strftime は** *strDest*に入れられた文字数を戻し **、wcsftime**は対応するワイド文字の数を返します。

終端の NULL を含む文字の総数が*maxsize*を超える場合は **、strftime**と**wcsftime**の両方が 0 を返し *、strDest*の内容は不確定です。

*strDest*の文字数は、書式指定コードを使用して*書式*に追加できる文字と同様に、*書式*内のリテラル文字の数と同じです。 文字列の終端の NULL は戻り値にはカウントされません。

## <a name="remarks"></a>解説

**strftime**関数と**wcsftime**関数は、指定されたフォーマット引数に従って*timeptr*の**tm**時間値を*フォーマット*し、その結果をバッファー *strDest*に格納します。 最大*サイズ*の文字は、文字列に最大で配置されます。 *タイムプター*構造のフィールドの説明については、 [asctime](asctime-wasctime.md)を参照してください。 **wcsftime**は **、strftime**のワイド文字に相当します。その文字列ポインタ引数はワイド文字列を指します。 それ以外では、これらの関数の動作は同じです。

この関数は、パラメーターを検証します。 *strDest* *、format*、または*timeptr*が null ポインターである場合、または*timeptr*によってアドレス指定された**tm**データ構造体が無効な場合 (たとえば、時刻または日付の範囲外の値が含まれている場合)、または*書式*指定文字列に無効な書式コードが含まれている場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、関数は 0 を返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsftime**|**strftime**|**strftime**|**wcsftime**|

*format*引数は 1 つ以上のコードで構成されます。**printf**のように、フォーマットコードの前にはパーセント記号 ( )**%** が付きます。 で**%** 始まっていない文字は、変更されずに*strDest*にコピーされます。 現在のロケールの**LC_TIME**カテゴリは **、 strftime**の出力フォーマットに影響を与えます。 (LC_TIMEの詳細については**LC_TIME**、 [setlocale](setlocale-wsetlocale.md)を参照してください。**strftime**関数と**wcsftime**関数は、現在設定されているロケールを使用します。 これらの関数の **_strftime_l**バージョンと **_wcsftime_l**バージョンは、ロケールをパラメーターとして受け取り、現在設定されているロケールの代わりにそれを使用する点を除いて、同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**strftime**関数は、次のフォーマットコードをサポートします。

|||
|-|-|
|コード|置換文字列|
|**%a**|ロケールでの曜日の省略名|
|**%A**|ロケール内の完全な曜日名|
|**%b**|ロケール内の省略された月名|
|**%B**|ロケール内の完全な月名|
|**%c**|ロケールに合った日付と時刻の表記|
|**%c**|年を 100 で除算し、整数に切り捨てる (00-99)|
|**%d**|10 進数で表した日 (01 ~ 31)|
|**%d**|**%m/%d/%y に**相当|
|**%e**|1 桁の前にスペースが付く 10 進数 (1 から 31) の月の日|
|**%f**|**%Y-%m-%dに**相当|
|**%g**|ISO 8601 週ベースの年の下 2 桁を 10 進数 (00 から 99)|
|**%g**|ISO 8601 週ベースの年を 10 進数で表す|
|**%h**|省略された月名 **(%b**と同じ)|
|**%H**|24 時間形式の時間 (00 ~ 23)|
|**%i**|12 時間形式の時間 (01 ~ 12)|
|**%j**|年の日を 10 進数で表す (001 ~ 366)|
|**%m**|10 進数で月 (01 - 12)|
|**%M**|10 進数としての分 (00 から 59)|
|**%n**|改行文字 (**\n**)|
|**%p**|ロケールの A.M./P.M. 12時間時計用のインジケータ|
|**%r**|ロケールの 12 時間制時刻|
|**%r**|**%H:%M に**相当|
|**%S**|2 番目の 10 進数 (00 から 59)|
|**%t**|水平タブ文字 (**\t**)|
|**%t**|**%H:%M:%S**に相当する、ISO 8601 時間形式|
|**%u**|ISO 8601 の曜日を 10 進数 (1 ~ 7;月曜日は1です)|
|**%u**|10 進数 (00 ~ 53) で、第 1 日曜日が第 1 週の最初の曜日である年の週番号|
|**%V**|ISO 8601 週番号を 10 進数 (00 ~ 53)|
|**%w**|10 進数 (0 ~ 6;日曜日は0です)|
|**%W**|10 進数 (00 ~ 53) で、最初の月曜日が週 1 の最初の曜日である年の週番号|
|**%x**|ロケールの日付表現|
|**%x**|ロケールの時間表現|
|**%y**|世紀のない年、10 進数 (00 ~ 99)|
|**%y**|世紀を付けた 10 進数の年|
|**%z**|ISO 8601 形式の UTC からのオフセット。タイム ゾーンが不明の場合は文字なし|
|**%z**|レジストリ設定に応じて、ロケールのタイムゾーン名またはタイムゾーンの省略形のいずれか。タイム ゾーンが不明の場合は文字なし|
|**%%**|パーセント記号|

**printf**関数と同様に、**#** フラグは任意のフォーマット コードの前に置く場合があります。 その場合、書式コードの説明は次のように変更します。

|[書式コード]|意味|
|-----------------|-------------|
|**%#a**%#a、%#A、%#b、%#B、%#g、%#G、%#h、#n%#w、%#p%、%#t、%#u、%#w、%#X、%#z、%#Z 、 **%#A** **%#b** **%#B** **%#g** **%#G** **%#h** **%#n** **%#p** **%#t** **%#u** **%#w** **%#X** **%#z** **%#Z****%#%**|**#** フラグは無視されます。|
|**%#c**|ロケールに適した長い日付と時刻の表現。 たとえば、"Tuesday, March 14, 1995, 12:41:29" です。|
|**%#x**|ロケールに適した長い日付表現。 たとえば、"Tuesday, March 14, 1995" です。|
|**%#d**%#d%#D、#e%#j、%#F、%#H、%#I、%#j、%#m **%#D** **%#I** **%#j** **%#H** **%#F** **%#e** **%#m**#j、%#M、%#r、%#R、%#S、%#T、%#U、%#V、%#W、%#y、%#Y **%#M** **%#r** **%#R** **%#S** **%#T** **%#U** **%#V** **%#W** **%#y** **%#Y**|先行するゼロまたはスペース (存在する場合) を削除します。|

**%V、%g、%G**によって生産される ISO 8601 週 **%G**と週ベースの年は月曜日に始まる週を使用します。 **%g** 年の最初の月曜日が第 2、第 3、または第 4 日の場合、前の曜日は前の年の最後の週の一部です。 その日の **%V**は 53 に置き換えられ **、%g**と **%G**の両方が前の年の数字に置き換えられます。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strftime**|\<time.h>|
|**wcsftime**|\<time.h> または \<wchar.h>|
|**_strftime_l**|\<time.h>|
|**_wcsftime_l**|\<time.h> または \<wchar.h>|

**_strftime_l**および **_wcsftime_l**機能は、マイクロソフト固有のものです。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[time](time-time32-time64.md) の例を参照してください。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md) <br/>
[時間管理](../../c-runtime-library/time-management.md) <br/>
[文字列操作](../../c-runtime-library/string-manipulation-crt.md) <br/>
[localeconv](localeconv.md) <br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md) <br/>
[関数](../../c-runtime-library/strcoll-functions.md) <br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
