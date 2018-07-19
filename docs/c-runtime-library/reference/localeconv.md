---
title: localeconv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- localeconv
dev_langs:
- C++
helpviewer_keywords:
- lconv type
- localeconv function
- locales, getting information on
ms.assetid: 7ecdb1f2-88f5-4037-a0e7-c754ab003660
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe3cc75430dfa9bb2f4c5513f4b2ba5a2fd1c4c9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405251"
---
# <a name="localeconv"></a>localeconv

ロケールの設定に関する詳細情報を取得します。

## <a name="syntax"></a>構文

```C
struct lconv *localeconv( void );
```

## <a name="return-value"></a>戻り値

**localeconv** 、入力の型のオブジェクトへのポインターを返します[構造体 lconv](../../c-runtime-library/standard-types.md)です。 オブジェクトに含まれる値は、スレッド ローカル ストレージのロケール設定からコピーされ、後続の呼び出しによって上書きされること**localeconv**です。 このオブジェクトの値に加えられた変更は、ロケールの設定を変更しないでください。 呼び出す[setlocale、_wsetlocale](setlocale-wsetlocale.md)で*カテゴリ*値**LC_ALL**、 **LC_MONETARY**、または**LC_NUMERIC**構造体の内容を上書きします。

## <a name="remarks"></a>コメント

**Localeconv**関数は、現在のロケールの数値の書式設定に関する詳細情報を取得します。 この情報は、**lconv** 型の構造体で格納されます。 **lconv** 構造体は、LOCALE.H で定義され、次のメンバーが含まれます。

|フィールド|説明|
|-|-|
decimal_point、<br/>_W_decimal_point|小数点非金銭的数量の文字へのポインター。
thousands_sep、<br/>_W_thousands_sep|非金銭的数量の小数点の左側にある数字のグループを示す文字へのポインターに分離します。
グループ化|ポインター、 **char**-サイズが非金銭的数の数字の各グループのサイズを表す整数です。
端数、<br/>_W_int_curr_symbol|現在のロケールの国際通貨記号を指すポインター。 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。
通貨、<br/>_W_currency_symbol|現在のロケールの現地の通貨記号を指すポインター。
mon_decimal_point、<br/>_W_mon_decimal_point|小数点文字の通貨値へのポインター。
mon_thousands_sep、<br/>_W_mon_thousands_sep|通貨値で小数点の左側にある数字のグループの区切り文字へのポインター。
mon_grouping|ポインター、 **char**-サイズが通貨書式の数字の各グループのサイズを表す整数です。
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

指定したメンバーの場合を除き、 **lconv**構造を持つ`char *`と`wchar_t *`バージョンは、文字列へのポインター。 これらに相当する **""** (または**L""** の**wchar_t \*** ) 長さが 0 のいずれかまたは現在のロケールでサポートされていません。 なお**decimal_point**と **_W_decimal_point**は常にサポートされていると、長さが 0 以外のです。

**Char**構造体のメンバーは、文字ではなく、小さい負でない数値。 そのいずれかが **CHAR_MAX** に相当する場合は、現在のロケールではサポートされていません。

値**をグループ化**と**mon_grouping**は次の規則に従って解釈されます。

- **CHAR_MAX** -、さらにグループ化を実行できません。

- 0 - は、残りの各桁の直前の要素を使用します。

- *n* -現在のグループを構成する数字の数。 次の要素が調べられて、現在のグループの前にある次のグループのサイズが決定されます。

**int_curr_symbol** の値は、次の規則に従って解釈されます。

- 最初の 3 文字は、*ISO 4217 Codes for the Representation of Currency and Funds* 規格で定義されている英字の国際通貨記号を指定します。

- 4 文字目 (null 文字の直前) は、国際通貨記号と通貨の数量を区切ります。

**p_cs_precedes** と **n_cs_precedes** の値は、次の規則に従って解釈されます (かっこ内は **n_cs_precedes** 規則です)。

- 0 - 通貨記号には、負でない (負) 通貨値の値が次に示します。

- 1-通貨記号では、負でない (負) 通貨値の前に付きます。

**p_sep_by_space** と **n_sep_by_space** の値は、次の規則に従って解釈されます (かっこ内は **n_sep_by_space** 規則です)。

- 0 - 負でない (負) 通貨値をスペースで値から通貨記号が区切られます。

- 1 - 通貨記号と負でない (負) 通貨値の領域の分離はありません。

**p_sign_posn** と **n_sign_posn** の値は、次の規則に従って解釈されます。

- 0 - 数値と通貨記号をかっこで囲みます。

- 1-記号の文字列には、数値と通貨記号が前に付きます。

- 2-記号の文字列には、数値と通貨記号が次に示します。

- 3-記号の文字列には、通貨記号が前に記述します。

- 4-すぐに次のように通貨記号の記号文字列します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
