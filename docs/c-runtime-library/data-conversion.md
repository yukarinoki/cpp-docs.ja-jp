---
title: データ変換
ms.date: 03/21/2018
f1_keywords:
- c.conversions
helpviewer_keywords:
- data conversion routines [C++]
- converting data
ms.assetid: b15b5268-7467-49f1-bf95-5299b598f94c
ms.openlocfilehash: 94e6a8182e12ecd74f9d2cd5dddaa84a1e3eb847
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218768"
---
# <a name="data-conversion"></a>データ変換

これらのルーチンは、ある形式から別の形式にデータを変換します。 通常、これらのルーチンは、ユーザーが作成した変換より速く変換を実行します。 *to* プレフィックスで始まるルーチンは、それぞれ、関数およびマクロとして実装されます。 実装の使い分けについては、「[関数またはマクロの選択に関する推奨事項](../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)」を参照してください。

## <a name="data-conversion-routines"></a>データ変換ルーチン

|ルーチンによって返される値|用途|
|-------------|---------|
|[絶対](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|整数の絶対値を求める|
|[atof、_atof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|文字列をに変換する**`float`**|
|[atoi、_atoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|文字列をに変換する**`int`**|
|[_atoi64、_atoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|文字列をまたはに変換します。 **`__int64`****`long long`**|
|[atol、_atol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|文字列をに変換する**`long`**|
|[c16rtomb、c32rtomb](../c-runtime-library/reference/c16rtomb-c32rtomb1.md)|UTF-16 または UTF-32 文字を同等のマルチバイト文字に変換する|
|[_ecvt](../c-runtime-library/reference/ecvt.md)、[_ecvt_s](../c-runtime-library/reference/ecvt-s.md)|**`double`** 指定された長さの文字列に変換する|
|[_fcvt](../c-runtime-library/reference/fcvt.md)、[_fcvt_s](../c-runtime-library/reference/fcvt-s.md)|**`double`** 小数点の後に指定された桁数で文字列に変換します|
|[_gcvt](../c-runtime-library/reference/gcvt.md)、[_gcvt_s](../c-runtime-library/reference/gcvt-s.md)|**`double`** 数値を文字列に変換します。文字列をバッファーに格納します|
|[_itoa、_ltoa、_ultoa、_i64toa、_ui64toa、_itow、_ltow、ultow、_i64tow、_ui64tow](../c-runtime-library/reference/itoa-itow.md)、[_itoa_s、_ltoa_s、_ultoa_s、_i64toa_s、_ui64toa_s、_itow_s、_ltow_s、_ultow_s、_i64tow_s、_ui64tow_s](../c-runtime-library/reference/itoa-s-itow-s.md)|整数型を文字列に変換する|
|[labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|整数の絶対値を求める **`long`**|
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|整数の絶対値を求める **`long long`**|
|[_mbbtombc、_mbbtombc_l](../c-runtime-library/reference/mbbtombc-mbbtombc-l.md)|1 バイト マルチバイト文字を、対応する 2 バイト マルチバイト文字に変換する|
|[_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|日本工業標準 (JIS: Japan Industry Standard) 文字を Japan Microsoft (JMS) 文字に変換する|
|[_mbcjistojms、_mbcjistojms_l、_mbcjmstojis、_mbcjmstojis_l](../c-runtime-library/reference/mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)|JMS 文字を JIS 文字に変換する|
|[_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|マルチバイト文字を 1 バイトのひらがなコードに変換する|
|[_mbctohira、_mbctohira_l、_mbctokata、_mbctokata_l](../c-runtime-library/reference/mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)|マルチバイト文字を 1 バイト カタカナ コードに変換する|
|[_mbctombb、_mbctombb_l](../c-runtime-library/reference/mbctombb-mbctombb-l.md)|2 バイト マルチバイト文字を、対応する 1 バイト マルチバイト文字に変換する|
|[mbrtoc16、mbrtoc32](../c-runtime-library/reference/mbrtoc16-mbrtoc323.md)|マルチバイト文字を同等の UTF-16 または UTF-32 文字に変換する|
|[mbstowcs、_mbstowcs_l](../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)、[mbstowcs_s、_mbstowcs_s_l](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)|マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換|
|[mbtowc、_mbtowc_l](../c-runtime-library/reference/mbtowc-mbtowc-l.md)|マルチバイト文字を対応するワイド文字に変換|
|[strtod、_strtod_l、wcstod、_wcstod_l](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)|文字列をに変換する**`double`**|
|[strtol、wcstol、_strtol_l、_wcstol_l](../c-runtime-library/reference/strtol-wcstol-strtol-l-wcstol-l.md)|文字列を整数に変換する **`long`**|
|[strtoul、_strtoul_l、wcstoul、_wcstoul_l](../c-runtime-library/reference/strtoul-strtoul-l-wcstoul-wcstoul-l.md)|文字列を整数に変換する **`unsigned long`**|
|[strxfrm、wcsxfrm、_strxfrm_l、_wcsxfrm_l](../c-runtime-library/reference/strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)|ロケール固有の情報に基づいて、文字列を照合形式に変換します。|
|[toascii、__toascii](../c-runtime-library/reference/toascii-toascii.md)|文字を ASCII コードに変換する|
|[tolower、_tolower、towlower、_tolower_l、_towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)、[_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|文字を調べ、現在大文字の場合は小文字に変換する|
|[tolower、_tolower、towlower、_tolower_l、_towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md)|文字を無条件に小文字に変換する|
|[toupper、_toupper、towupper、_toupper_l、_towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)、[_mbctolower、_mbctolower_l、_mbctoupper、_mbctoupper_l](../c-runtime-library/reference/mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)|文字を調べ、現在小文字の場合は大文字に変換する|
|[toupper、_toupper、towupper、_toupper_l、_towupper_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md)|文字を無条件に大文字に変換する|
|[wcstombs、_wcstombs_l](../c-runtime-library/reference/wcstombs-wcstombs-l.md)、[wcstombs_s、_wcstombs_s_l](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)|ワイド文字のシーケンスを、対応するマルチバイト文字のシーケンスに変換する|
|[wctomb、_wctomb_l](../c-runtime-library/reference/wctomb-wctomb-l.md)、[wctomb_s、_wctomb_s_l](../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)|ワイド文字を対応するマルチバイト文字に変換する|
|[_wtof、_wtof_l](../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)|ワイド文字列をに変換します。**`double`**|
|[_wtoi、_wtoi_l](../c-runtime-library/reference/atoi-atoi-l-wtoi-wtoi-l.md)|ワイド文字列をに変換する**`int`**|
|[_wtoi64、_wtoi64_l](../c-runtime-library/reference/atoi64-atoi64-l-wtoi64-wtoi64-l.md)|ワイド文字の文字列をまたはに変換します。 **`__int64`****`long long`**|
|[_wtol、_wtol_l](../c-runtime-library/reference/atol-atol-l-wtol-wtol-l.md)|ワイド文字列をに変換する**`long`**|

## <a name="see-also"></a>関連項目

[カテゴリ別ユニバーサル C ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)<br/>
