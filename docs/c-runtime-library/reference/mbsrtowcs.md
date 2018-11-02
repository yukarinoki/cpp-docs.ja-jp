---
title: mbsrtowcs
ms.date: 11/04/2016
apiname:
- mbsrtowcs
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
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 2bc0c8c9e2d871b6d1748c42dc02c627244dbf69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597146"
---
# <a name="mbsrtowcs"></a>mbsrtowcs

現在のロケールのマルチバイト文字列を、対応するワイド文字の文字列に変換します。マルチバイト文字の途中から再開することが可能です。 この関数のセキュリティが強化されたバージョンについては、「[mbsrtowcs_s](mbsrtowcs-s.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
size_t mbsrtowcs(
   wchar_t *wcstr,
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t mbsrtowcs(
   wchar_t (&wcstr)[size],
   const char **mbstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>パラメーター

*wcstr*<br/>
結果として変換されたワイド文字の文字列を格納するアドレス。

*mbstr*<br/>
変換するマルチバイト文字列の場所への間接ポインター。

*count*<br/>
変換および格納する文字 (バイトではなく) の最大数*wcstr*します。

*呼び出すため*<br/>
ポインター、 **mbstate_t**変換状態オブジェクト。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部**mbstate_t**オブジェクトはスレッド セーフではありませんを常に渡す独自ことをお勧めします。*呼び出すため*パラメーター。

## <a name="return-value"></a>戻り値

正常に変換された文字数を返します (終端の null 文字があっても含まれません)。 返します (size_t)(-1) 場合は、エラーが発生し、設定**errno** EILSEQ にします。

## <a name="remarks"></a>Remarks

**Mbsrtowcs**関数が直接に指すマルチバイト文字の文字列に変換します*mbstr*が指すバッファーに格納されているワイド文字に*wcstr*により、含まれる変換状態を使用して*呼び出すため*します。 変換は引き続き文字ごとに、終端 null マルチバイト文字が検出された、まで、現在のロケールで有効な文字に対応しないマルチバイト シーケンスが発生しましたまで、または*カウント*文字が変換されています。 場合**mbsrtowcs**前に、かにマルチバイト null 文字 ('\0') が発生した*カウント*発生すると、16 ビット終端の null 文字を停止に変換します。

つまり、ワイド文字の文字列*wcstr*が null で終わる場合にのみ**mbsrtowcs**変換中にマルチバイト null 文字を検出するとします。 によって、シーケンスを指している場合*mbstr*と*wcstr*の動作が重なる**mbsrtowcs**が定義されていません。 **mbsrtowcs**は現在のロケールの LC_TYPE カテゴリを受けます。

**Mbsrtowcs**関数とは異なります[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)によってその再起動します。 変換の状態が格納されている*呼び出すため*同じか、またはその他の再開可能な関数を呼び出すのためです。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションで使用する**mbsrlen**の代わりに**mbslen**後続の呼び出しの場合は、 **mbsrtowcs**の代わりに使用が**mbstowcs**.

場合*wcstr*が null ポインターを指すポインター オブジェクト*mbstr*終端の null 文字に達したために、変換が停止している場合に null ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。

場合、 *wcstr*引数が null ポインターの場合、*カウント*引数は無視されますと**mbsrtowcs**コピー先の文字列のワイド文字で、必要なサイズを返します。 場合*呼び出すため*null ポインターの場合は、関数が使用する内部の非スレッド セーフな静的**mbstate_t**変換状態オブジェクト。 場合の文字シーケンス*mbstr*が対応するマルチバイト文字の表現、-1 が返されます、 **errno**に設定されている**EILSEQ**します。

場合*mbstr* 」の説明に従って、isa の null ポインター、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL** -1 を返します。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Mbsrtowcs**関数は、現在のスレッドで関数が呼び出すない限り、マルチ スレッド セーフ**setlocale**この関数を実行している限り、*呼び出すため*引数が null ポインターではありません。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
