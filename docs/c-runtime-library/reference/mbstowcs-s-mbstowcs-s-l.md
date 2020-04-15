---
title: mbstowcs_s、_mbstowcs_s_l
ms.date: 4/2/2020
api_name:
- _mbstowcs_s_l
- mbstowcs_s
- _o__mbstowcs_s_l
- _o_mbstowcs_s
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
ms.openlocfilehash: 07d694a7430f23e2f9600a5d2b147bcee2ef0e09
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338806"
---
# <a name="mbstowcs_s-_mbstowcs_s_l"></a>mbstowcs_s、_mbstowcs_s_l

マルチバイト文字のシーケンスを、対応するワイド文字のシーケンスに変換します。 「[Security Features in the CRT](../../c-runtime-library/security-features-in-the-crt.md)」 (CRT のセキュリティ機能) で説明されているように、セキュリティが強化されたバージョンの [mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md) です。

## <a name="syntax"></a>構文

```C
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count
);
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t *wcstr,
   size_t sizeInWords,
   const char *mbstr,
   size_t count,
   _locale_t locale
);
template <size_t size>
errno_t mbstowcs_s(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count
); // C++ only
template <size_t size>
errno_t _mbstowcs_s_l(
   size_t *pReturnValue,
   wchar_t (&wcstr)[size],
   const char *mbstr,
   size_t count,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>パラメーター

*値を返します。*<br/>
変換された文字数。

*ウストル*<br/>
結果として変換されたワイド文字の文字列のバッファーのアドレス。

*サイズインワーズ*<br/>
*wcstr*バッファーのサイズを単語で表します。

*mbstr*<br/>
NULL で終了するマルチバイト文字のシーケンスのアドレス。

*count*<br/>
終了 NULL を含まない*wcstr*バッファーに格納するワイド文字の最大数、または[_TRUNCATE。](../../c-runtime-library/truncate.md)

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー状態|戻り値と**エラーノ**|
|---------------------|------------------------------|
|*wcstr*は**NULL**で*サイズインワード*> 0 です|**Einval**|
|*MBSTR*は**NULL です**|**Einval**|
|変換後の文字列を格納するには、変換先のバッファが小さすぎます (*カウント*が **_TRUNCATE**場合を除き、下記の「解説」を参照してください)。|**ERANGE**|
|*wcstr*は**NULL**ではなく、*サイズInWords* == 0 です。|**Einval**|

これらのいずれかの条件が発生すると、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行を続行できる場合、関数はエラー コードを返し、テーブルに示されている**とおり errno**を設定します。

## <a name="remarks"></a>解説

**mbstowcs_s**関数は *、mbstr*が指すマルチバイト文字の文字列を *、wcstr*が指すバッファに格納されているワイド文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- マルチバイトの null 文字が検出されました。

- 無効なマルチバイト文字が検出されました。

- *wcstr*バッファに格納されているワイド文字の数は*カウント*に等しい。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

*count*が特殊値[_TRUNCATE](../../c-runtime-library/truncate.md)の場合 **、mbstowcs_s**は、文字列を宛先バッファに収まる限り変換しますが、null ターミネータの空き容量は残ります。

**mbstowcs_s**がソース文字列を正常に変換した場合、null 終端文字を含む変換された文字列のワイド文字でサイズ*を pReturnValue&#42;* に格納します *(pReturnValue*が**NULL**でない場合)。 これは *、wcstr*引数が**NULL**で、必要なバッファサイズを決定する方法を提供する場合でも発生します。 *wcstr*が**NULL**の場合は *、カウント*は無視され *、sizeInWords*は 0 である必要があります。

**mbstowcs_s**が無効なマルチバイト文字を検出すると *、pReturnValue&#42;* 0 を設定し、宛先バッファを空の文字列に設定し **、errno**を EILSEQ に設定し **、EILSEQ**を返します。 **EILSEQ**

*mbstr*と*wcstr*が指すシーケンスが重なっている場合 **、mbstowcs_s**の動作は未定義です。

> [!IMPORTANT]
> *wcstr*と*mbstr*が重ならないようにし、その*数*が変換するマルチバイト文字の数を正しく反映していることを確認してください。

**mbstowcs_s**は、ロケールに依存するすべての動作に現在のロケールを使用します。**_mbstowcs_s_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](/windows/win32/api/stringapiset/nf-stringapiset-multibytetowidechar)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
