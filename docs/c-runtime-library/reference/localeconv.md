---
title: localeconv
ms.date: 11/04/2016
apiname:
- localeconv
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- localeconv
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
ms.openlocfilehash: bf26e4f7b7fb4f0334b57604fe5c4996312bd62a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628142"
---
# <a name="localeconv"></a>localeconv

ロケールの設定に関する詳細情報を取得します。

## <a name="syntax"></a>構文

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>戻り値

**localeconv**型の入力オブジェクトにポインターを返します[struct lconv](../../c-runtime-library/standard-types.md)します。 オブジェクトに含まれる値がスレッド ローカル記憶域のロケール設定からコピーされ、以降の呼び出しによって上書きできる**localeconv**します。 このオブジェクトの値に加えられた変更は、ロケールの設定を変更しないでください。 呼び出す[setlocale](setlocale-wsetlocale.md)で*カテゴリ*値**LC_ALL**、 **LC_MONETARY**、または**LC_NUMERIC**構造体の内容を上書きします。

## <a name="remarks"></a>Remarks

**Localeconv**関数は、現在のロケールの数値の書式設定に関する詳細情報を取得します。 この情報は、**lconv** 型の構造体で格納されます。 **lconv** 構造体は、LOCALE.H で定義され、次のメンバーが含まれます。

|フィールド|説明|
|-|-|
decimal_point、<br/>_W_decimal_point|小数点の通貨でない数量の文字へのポインター。
thousands_sep、<br/>_W_thousands_sep|通貨でない数量の小数点の左側にある数字のグループを示す文字へのポインターに分離します。
グループ化|ポインターを**char**-サイズの通貨でない数量の数字の各グループのサイズを含む整数です。
int_curr_symbol、<br/>_W_int_curr_symbol|現在のロケールの国際通貨記号へのポインター。 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。
通貨、<br/>_W_currency_symbol|現在のロケールの国内通貨記号へのポインター。
mon_decimal_point、<br/>_W_mon_decimal_point|小数点の通貨数量の文字へのポインター。
mon_thousands_sep、<br/>_W_mon_thousands_sep|通貨数量の小数点の左側にある数字のグループを区切る文字へのポインター。
mon_grouping|ポインターを**char**-通貨数量の数字の各グループのサイズを格納する整数のサイズします。
positive_sign、<br/>_W_positive_sign|負でない通貨数量の符号を示す文字列。
negative_sign、<br/>_W_negative_sign|負の通貨数量の符号を示す文字列。
する時|国際方式で書式化された通貨数量の小数点より右側の桁数。
frac_digits|書式化された通貨数量の小数点より右側の桁数。
p_cs_precedes|書式化された負でない通貨数量の値の前に通貨記号が付く場合は、1 に設定します。 値の後に記号が続く場合は、0 に設定します。
p_sep_by_space|書式化された負でない通貨数量の値と通貨記号をスペースで区切る場合は、1 に設定します。 スペースで区切らない場合は、0 に設定します。
n_cs_precedes|書式化された負の通貨数量の値の前に通貨記号が付く場合は、1 に設定します。 値の後に記号が続く場合は、0 に設定します。
n_sep_by_space|書式化された負の通貨数量の値と通貨記号をスペースで区切る場合は、1 に設定します。 スペースで区切らない場合は、0 に設定します。
p_sign_posn|書式化された負でない通貨数量での正符号の位置。
n_sign_posn|書式化された負の通貨数量での正符号の位置。

指定したメンバーのない限り、 **lconv**構造を持つ`char *`と`wchar_t *`バージョンは、文字列へのポインター。 これらに相当する **""** (または**L""** の**wchar_t** <strong>\*</strong>) が長さ 0 のいずれかまたは現在のサポートされていませんロケール。 なお**decimal_point**と **_W_decimal_point**は常にサポートされており、長さが 0 以外。

**Char**構造体のメンバーは、文字ではなく、小さい負でない数値。 そのいずれかが **CHAR_MAX** に相当する場合は、現在のロケールではサポートされていません。

値**グループ化**と**mon_grouping**は、次の規則に従って解釈されます。

- **CHAR_MAX** -以上グループ化は行いません。

- 0 - は、残りの桁ごとの直前の要素を使用します。

- *n* -現在のグループを構成する桁数。 次の要素が調べられて、現在のグループの前にある次のグループのサイズが決定されます。

**int_curr_symbol** の値は、次の規則に従って解釈されます。

- 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。

- 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。

**p_cs_precedes** と **n_cs_precedes** の値は、次の規則に従って解釈されます (かっこ内は **n_cs_precedes** 規則です)。

- 0 - 通貨記号は、負でない (負の) 通貨値の値に従います。

- 1-通貨記号は、負でない (負の) 通貨値の前にあります。

**p_sep_by_space** と **n_sep_by_space** の値は、次の規則に従って解釈されます (かっこ内は **n_sep_by_space** 規則です)。

- 0 - 負でない (負の) 通貨値をスペースでの値から通貨記号が区切られます。

- 1 - 通貨記号と負でない (負の) 通貨値の間をスペースで区切りませんはありません。

**p_sign_posn** と **n_sign_posn** の値は、次の規則に従って解釈されます。

- 0 - 数量と通貨記号をかっこで囲みます。

- 1-符号の文字列には、数量と通貨記号が先頭に付きます。

- 2-符号の文字列では、数量と通貨記号に従います。

- 3 - 通貨記号の直前に符号の文字列。

- 4-すぐに次のように通貨記号の記号文字列します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**localeconv**|\<locale.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="see-also"></a>関連項目

[ロケール](../../c-runtime-library/locale.md)<br/>
[setlocale](../../preprocessor/setlocale.md)<br/>
[strcoll 系関数](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime、wcsftime、_strftime_l、_wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
