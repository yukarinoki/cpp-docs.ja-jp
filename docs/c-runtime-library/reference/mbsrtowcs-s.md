---
description: '詳細については、次を参照してください: mbsrtowcs_s'
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsrtowcs_s
helpviewer_keywords:
- mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
ms.openlocfilehash: c7c53d3213bbe552dd63eb527a635660e803e9a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240170"
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

*pReturnValue*<br/>
変換された文字数。

*wcstr*<br/>
結果として変換されたワイド文字の文字列を格納するバッファーのアドレス。

*sizeInWords*<br/>
*Wcstr* のサイズ (ワイド文字)。

*mbstr*<br/>
変換されるマルチバイト文字の文字列の場所への間接ポインター。

*count*<br/>
*Wcstr* バッファーに格納するワイド文字の最大数。終端の null を含めたり、 [_TRUNCATE](../../c-runtime-library/truncate.md)したりすることはできません。

*mbstate*<br/>
**Mbstate_t** 変換状態オブジェクトへのポインター。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部 **mbstate_t** オブジェクトはスレッドセーフではないため、常に独自の *mbstate* パラメーターを渡すことをお勧めします。

## <a name="return-value"></a>戻り値

変換が正常に終了した場合は 0 を返し、失敗した場合はエラー コードを返します。

|エラー状態|戻り値と **errno**|
|---------------------|------------------------------|
|*wcstr* は null ポインターで、 *sizeinwords* > 0|**EINVAL**|
|*mbstr* は null ポインターです|**EINVAL**|
|*Mbstr* が間接的に指す文字列には、現在のロケールに対して無効なマルチバイトシーケンスが含まれています。|**EILSEQ**|
|コピー先のバッファーが小さすぎて、変換後の文字列を含めることができません ( *count* が **_TRUNCATE** 場合を除きます。詳細については、「解説」を参照してください)。|**ERANGE**|

これらのいずれかの条件が発生すると、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」に説明されているとおり無効なパラメーター例外が呼び出されます。 実行の継続が許可された場合、関数はエラーコードを返し、表に示されているように **errno** を設定します。

## <a name="remarks"></a>解説

**Mbsrtowcs_s** 関数は、 *mbstate* に含まれる変換状態を使用して、 *mbstr* が間接的に指すマルチバイト文字の文字列を *wcstr* が指すバッファーに格納されているワイド文字に変換します。 これらの条件のいずれかが満たされるまで、各文字に対して変換が続きます。

- マルチバイトの null 文字が検出されました。

- 無効なマルチバイト文字が検出されました。

- *Wcstr* buffer に格納されているワイド文字の数は *count* と等しくなります。

*Wcstr* が null ポインターでない場合、変換先の文字列 *wcstr* は、エラーが発生した場合でも、常に null で終了します。

*Count* が [_TRUNCATE](../../c-runtime-library/truncate.md)特別な値の場合、 **mbsrtowcs_s** は、null 終端文字用の空きを残したまま、コピー先のバッファーに収まる限りの文字列を変換します。

**Mbsrtowcs_s** がソース文字列を正常に変換した場合は、変換後の文字列のワイド文字と null 終端文字のサイズが *&#42;preturnvalue* 値に格納されます ( *preturnvalue* 値が null ポインターではない場合)。 これは、 *wcstr* 引数が null ポインターであり、必要なバッファーサイズを決定できる場合でも発生します。 *Wcstr* が null ポインターの場合、 *count* は無視されることに注意してください。

*Wcstr* が null ポインターでない場合は、終端の null 文字に到達したために変換が停止した場合、 *mbstr* が指すポインターオブジェクトに null ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。

*Mbstate* が null ポインターの場合、ライブラリの内部 **mbstate_t** 変換状態の静的オブジェクトが使用されます。 この内部静的オブジェクトはスレッドセーフではないため、独自の *mbstate* 値を渡すことをお勧めします。

現在のロケールで無効なマルチバイト文字が検出された **mbsrtowcs_s** 場合は、 *&#42;preturnvalue* に-1 を入れ、コピー先のバッファー を空の文字列に設定し、 **errno** を **EILSEQ** に設定して、 **EILSEQ** を返します。

*Mbstr* と *wcstr* が指すシーケンスが重なっている場合、 **mbsrtowcs_s** の動作は未定義です。 **mbsrtowcs_s** は、現在のロケールの LC_TYPE カテゴリの影響を受けます。

> [!IMPORTANT]
> *Wcstr* と *mbstr* が重複しないようにし、その *カウント* に変換するマルチバイト文字数が正しく反映されていることを確認します。

**Mbsrtowcs_s** 関数は、再起動によって [_mbstowcs_s_l mbstowcs_s と](mbstowcs-s-mbstowcs-s-l.md)異なります。 変換状態は、同じまたはその他の再開可能な関数への後続の呼び出しのために *mbstate* に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。 たとえば、 **mbstowcs_s** ではなく **mbsrtowcs_s** の後続の呼び出しが使用される場合、アプリケーションでは **mbslen** ではなく **mbsrlen** を使用する必要があります。

C++ では、この関数の使用はテンプレートのオーバーロードによって簡素化されます。オーバーロードでは、バッファー長を自動的に推論できる (サイズの引数を指定する必要がなくなる) だけでなく、古くてセキュリティが万全ではない関数を新しく安全な関数に自動的に置き換えることができます。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="exceptions"></a>例外

**Mbsrtowcs_s** 関数は、この関数が実行されていて、 *mbstate* 引数が null ポインターでない限り、現在のスレッドの関数が **setlocale** を呼び出すことができない場合に、マルチスレッドセーフです。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**mbsrtowcs_s**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[Multibyte-Character シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs_s、_mbstowcs_s_l](mbstowcs-s-mbstowcs-s-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
