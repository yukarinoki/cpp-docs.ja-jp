---
title: mbsrtowcs_s
ms.date: 4/2/2020
api_name:
- mbsrtowcs_s
- _o_mbsrtowcs_s
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: 62ae534e8080b74ada49cca005811a049055cb65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338898"
---
# <a name="mbsrtowcs_s"></a>mbsrtowcs_s

現在のロケールのマルチバイト文字の文字列をワイド文字の文字列表現に変換します。 これは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおりセキュリティーが強化されたバージョンの [mbsrtowcs](mbsrtowcs.md) です。

## <a name="syntax"></a>構文

```C
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t * wcstr,
   size_t sizeInWords,
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
);
template <size_t size>
errno_t mbsrtowcs_s(
   size_t * pReturnValue,
   wchar_t (&wcstr)[size],
   const char ** mbstr,
   size_t count,
   mbstate_t * mbstate
); // C++ only
```

### <a name="parameters"></a>パラメーター

*値を返します。*<br/>
変換された文字数。

*ウストル*<br/>
結果として変換されたワイド文字の文字列を格納するバッファーのアドレス。

*サイズインワーズ*<br/>
単語の*wcstr*のサイズ (ワイド文字)。

*mbstr*<br/>
変換されるマルチバイト文字の文字列の場所への間接ポインター。

*count*<br/>
終了 NULL を含まない*wcstr*バッファーに格納するワイド文字の最大数、または[_TRUNCATE。](../../c-runtime-library/truncate.md)

*mbstate*<br/>
**mbstate_t**変換状態オブジェクトへのポインター。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部**mbstate_t**オブジェクトはスレッド セーフではないため、常に独自の*mbstate*パラメーターを渡すことをお勧めします。

## <a name="return-value"></a>戻り値

変換が正常に終了した場合は 0 を返し、失敗した場合はエラー コードを返します。

|エラー状態|戻り値と**エラーノ**|
|---------------------|------------------------------|
|*wcstr*は null ポインターであり *、サイズInWords* > 0 です|**Einval**|
|*mbstr*は NULL ポインタです|**Einval**|
|間接的に指定された*mbstr*の文字列には、現在のロケールでは無効なマルチバイト シーケンスが含まれています。|**EILSEQ**|
|変換後のバッファが小さすぎて変換された文字列を格納するには (*カウント*が **_TRUNCATE**場合を除くが、詳細については「解説」を参照)|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり無効なパラメーター例外が呼び出されます。 実行を続行できる場合、関数はエラー コードを返し、テーブルに示されている**とおり errno**を設定します。

## <a name="remarks"></a>解説

**mbsrtowcs_s**関数は *、mbstr*が間接的に指すマルチバイト文字の文字列を、 *mbstate*に含まれる変換状態を使用して*wcstr*が指すバッファに格納されているワイド文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- マルチバイトの null 文字が検出されました。

- 無効なマルチバイト文字が検出されました。

- *wcstr*バッファに格納されているワイド文字の数は*カウント*に等しい。

*wcstr*が null ポインターでない限り、変換先の文字列*wcstr*は常に null で終了します。

*count*が特殊値[_TRUNCATE](../../c-runtime-library/truncate.md)の場合 **、mbsrtowcs_s**は、文字列を宛先バッファに収まる限り変換しますが、null ターミネータの空き容量は残ります。

**mbsrtowcs_s**がソース文字列を正常に変換した場合、サイズは変換された文字列のワイド文字に、null 終端文字は *&#42;pReturnValue**pReturnValue*に格納されます。 これは *、wcstr*引数が null ポインターであり、必要なバッファー・サイズを判別できる場合でも発生します。 *wcstr*が null ポインタの場合、*カウント*は無視されます。

*wcstr*が null ポインターでない場合、終了 NULL 文字に達したために変換が停止した場合 *、mbstr*が指すポインター・オブジェクトにヌル・ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。

*mbstate*が null ポインターの場合、ライブラリ内部**mbstate_t**変換状態静的オブジェクトが使用されます。 この内部静的オブジェクトはスレッド セーフではないため、独自の*mbstate*値を渡すことをお勧めします。

mbsrtowcs_sが現在のロケールで有効でないマルチバイト文字**を検出した**場合は *、pReturnValue&#42;* に -1 を入れ、宛先バッファ*wcstr*を空の文字列に設定し **、errno**を EILSEQ に設定し **、EILSEQ**を返します。 **EILSEQ**

*mbstr*と*wcstr*が指すシーケンスが重なっている場合 **、mbsrtowcs_s**の動作は未定義です。 **mbsrtowcs_s**は、現在のロケールのLC_TYPEカテゴリの影響を受けます。

> [!IMPORTANT]
> *wcstr*と*mbstr*が重ならないようにし、その*数*が変換するマルチバイト文字の数を正しく反映していることを確認してください。

**mbsrtowcs_s**関数は、mbstowcs_sとは異なり[、_mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)再起動可能性があります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、mbstowcs_sではなく **、mbsrtowcs_s**への後続の呼び出しを使用する場合は、mbslen ではなく**mbsrlen**を使用する必要**があります。** **mbsrlen**

C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="exceptions"></a>例外

この関数が実行されている間、現在のスレッドで**setlocale**を呼び出す関数がなく *、mbstate*引数が null ポインターでない場合 **、mbsrtowcs_s**関数はマルチスレッド セーフです。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s、_mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
