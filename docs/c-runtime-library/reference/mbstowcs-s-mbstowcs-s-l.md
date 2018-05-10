---
title: mbstowcs_s、_mbstowcs_s_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f366e01fbaa8da5c0dbc96ff4da324611e132f1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s、_mbstowcs_s_l

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

*pReturnValue*<br/>
変換された文字数。

*wcstr*<br/>
結果として変換されたワイド文字の文字列のバッファーのアドレス。

*sizeInWords*<br/>
サイズ、 *wcstr*単語内のバッファー。

*mbstr*<br/>
null で終了するマルチバイト文字のシーケンスのアドレス。

*count*<br/>
格納するワイド文字の最大数、 *wcstr*バッファー、終端の null は含まないまたは[_TRUNCATE](../../c-runtime-library/truncate.md)です。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

正常終了した場合は 0 を返します。失敗した場合はエラー コードを返します。

|エラー条件|戻り値と**errno**|
|---------------------|------------------------------|
|*wcstr*は**NULL**と*sizeInWords* > 0|**EINVAL**|
|*mbstr*は**NULL**|**EINVAL**|
|コピー先のバッファーが小さすぎて、変換された文字列を含める (しない限り、*カウント*は **_TRUNCATE**; 解説を参照してください)|**ERANGE**|
|*wcstr*は**NULL**と*sizeInWords* = = 0|**EINVAL**|

これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター例外が呼び出されます。 実行の継続が許可された場合、関数はエラー コードを返します設定と**errno**表に示すようにします。

## <a name="remarks"></a>コメント

**Mbstowcs_s**関数によって示される、マルチバイト文字の文字列に変換*mbstr*が指すバッファーに格納されているワイド文字に*wcstr*です。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- マルチバイトの null 文字が検出されました。

- 無効なマルチバイト文字が検出されました。

- 格納されるワイド文字の数、 *wcstr* equals をバッファー*カウント*です。

変換後の文字列は、常に null で終わります (エラーの場合も同様)。

場合*カウント*特殊な値は、 [_TRUNCATE](../../c-runtime-library/truncate.md)、し**mbstowcs_s** null 用の領域を残して、コピー先のバッファーに収まるようだけでなく、文字列のと同様に変換しますターミネータです。

場合**mbstowcs_s**ソース文字列を変換が正常に null 終端文字も含めて、変換後の文字列のワイド文字単位のサイズを入れ *&#42;pReturnValue* (を提供*pReturnValue*は**NULL**)。 これが発生した場合でも、 *wcstr*引数は**NULL**し、必要なバッファー サイズを決定する方法を提供します。 されている場合*wcstr*は**NULL**、*カウント*は無視されますと*sizeInWords* 0 にする必要があります。

場合**mbstowcs_s**で無効なマルチバイト文字が発生した 0 に入れます *&#42;pReturnValue*、空の文字列をコピー先のバッファーを設定、設定**errno** に**EILSEQ**、し、返します**EILSEQ**です。

シーケンスを指す場合*mbstr*と*wcstr*などの動作の重複**mbstowcs_s**が定義されていません。

> [!IMPORTANT]
> いることを確認*wcstr*と*mbstr*が重なり合わず、および*カウント*変換するマルチバイト文字の数を正確に反映します。

**mbstowcs_s** ; すべてのロケールに依存する動作に現在のロケールを使用 **_mbstowcs_s_l**は、代わりに渡されるロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

C++ では、これらの関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbstowcs_s**|\<stdlib.h>|
|**_mbstowcs_s_l**|\<stdlib.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen、mblen、_mblen_l](mbclen-mblen-mblen-l.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[wcstombs、_wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb、_wctomb_l](wctomb-wctomb-l.md)<br/>
