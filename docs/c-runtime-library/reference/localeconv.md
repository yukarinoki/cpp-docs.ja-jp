---
title: localeconv
ms.date: 4/2/2020
api_name:
- localeconv
- _o_localeconv
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- localeconv
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
ms.openlocfilehash: a617980d60b3a12c06b30aab6cd457792a1aa770
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342144"
---
# <a name="localeconv"></a>localeconv

ロケールの設定に関する詳細情報を取得します。

## <a name="syntax"></a>構文

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>戻り値

**localeconv**は[、struct lconv](../../c-runtime-library/standard-types.md)型の塗りつぶされたオブジェクトへのポインタを返します。 オブジェクトに含まれる値は、スレッドローカルストレージのロケール設定からコピーされ **、localeconv**への後続の呼び出しによって上書きされる可能性があります。 このオブジェクトの値に変更を加えても、ロケール設定は変更されません。 LC_ALL **、** **LC_MONETARY、** または**LC_NUMERIC**の*カテゴリ*値を持つ[setlocale](setlocale-wsetlocale.md)を呼び出して、構造体の内容を上書きします。

## <a name="remarks"></a>解説

**localeconv**関数は、現在のロケールの数値フォーマットに関する詳細情報を取得します。 この情報は、**lconv** 型の構造体で格納されます。 **lconv** 構造体は、LOCALE.H で定義され、次のメンバーが含まれます。

|フィールド|意味|
|-|-|
decimal_point、<br/>_W_decimal_point|非金銭的な量の小数点文字へのポインタ。
thousands_sep、<br/>_W_thousands_sep|非金銭的な量の小数点の左に数字のグループを区切る文字へのポインタ。
グループ化|非金銭的な量の各桁のグループのサイズを含む**char-size**整数へのポインター。
int_curr_symbol、<br/>_W_int_curr_symbol|現在のロケールの国際通貨記号へのポインター。 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。
currency_symbol、<br/>_W_currency_symbol|現在のロケールのローカル通貨記号へのポインター。
mon_decimal_point、<br/>_W_mon_decimal_point|金額の小数点文字へのポインタ。
mon_thousands_sep、<br/>_W_mon_thousands_sep|金額の小数点以下の桁数のグループの区切り記号へのポインター。
mon_grouping|通貨の数値の各グループのサイズを含む**char-size**整数へのポインター。
positive_sign、<br/>_W_positive_sign|負でない通貨数量の符号を示す文字列。
negative_sign、<br/>_W_negative_sign|負の通貨数量の符号を示す文字列。
int_frac_digits|国際方式で書式化された通貨数量の小数点より右側の桁数。
frac_digits|書式化された通貨数量の小数点より右側の桁数。
p_cs_precedes|書式化された負でない通貨数量の値の前に通貨記号が付く場合は、1 に設定します。 値の後に記号が続く場合は、0 に設定します。
p_sep_by_space|書式化された負でない通貨数量の値と通貨記号をスペースで区切る場合は、1 に設定します。 スペースで区切らない場合は、0 に設定します。
n_cs_precedes|書式化された負の通貨数量の値の前に通貨記号が付く場合は、1 に設定します。 値の後に記号が続く場合は、0 に設定します。
n_sep_by_space|書式化された負の通貨数量の値と通貨記号をスペースで区切る場合は、1 に設定します。 スペースで区切らない場合は、0 に設定します。
p_sign_posn|書式化された負でない通貨数量での正符号の位置。
n_sign_posn|書式化された負の通貨数量での正符号の位置。

指定された場合を除き、バージョンと`char *``wchar_t *`を持つ**lconv**構造体のメンバーは、文字列へのポインターです。 <strong>\*</strong> **wchar_t**の**場合は""""(** または**L")に**等しいこれらのいずれも、長さがゼロであるか、現在のロケールではサポートされていません。 **decimal_point**と **_W_decimal_point**は常にサポートされており、長さが 0 以外であることに注意してください。

構造体の**char**メンバーは、文字ではなく、小さな負でない数です。 そのいずれかが **CHAR_MAX** に相当する場合は、現在のロケールではサポートされていません。

**グループ化**と**mon_grouping**の値は、次の規則に従って解釈されます。

- **CHAR_MAX** - これ以上グループ化を実行しません。

- 0 - 残りの各桁に前の要素を使用します。

- *n* - 現在のグループを構成する桁数。 次の要素が調べられて、現在のグループの前にある次のグループのサイズが決定されます。

**int_curr_symbol** の値は、次の規則に従って解釈されます。

- 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。

- 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。

**p_cs_precedes** と **n_cs_precedes** の値は、次の規則に従って解釈されます (かっこ内は **n_cs_precedes** 規則です)。

- 0 - 通貨記号は、負でない (負の) 通貨値の値に続きます。

- 1 - 通貨記号は、負でない (負の) 通貨値の前に置きます。

**p_sep_by_space** と **n_sep_by_space** の値は、次の規則に従って解釈されます (かっこ内は **n_sep_by_space** 規則です)。

- 0 - 通貨記号は、負でない (負の) 通貨値の場合は、値からスペースで区切られます。

- 1 - 通貨記号と、負でない (負の) 通貨値の間にスペースの区切りはありません。

**p_sign_posn** と **n_sign_posn** の値は、次の規則に従って解釈されます。

- 0 - 括弧で数量と通貨記号を囲みます。

- 1 - 符号文字列は、数量と通貨記号の前に表示されます。

- 2 - 符号文字列は、数量と通貨記号に続きます。

- 3 - 通貨記号の直前に符号文字列を指定します。

- 4 - 通貨記号の直後に符号文字列を指定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**localeconv**|\<locale.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
[Setlocale](../../preprocessor/setlocale.md)<br/>
[関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
