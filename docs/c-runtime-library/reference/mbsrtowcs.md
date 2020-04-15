---
title: mbsrtowcs
ms.date: 4/2/2020
api_name:
- mbsrtowcs
- _o_mbsrtowcs
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
- mbsrtowcs
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
ms.openlocfilehash: 509046e1c55d89cd78b09076838983691423a1ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338892"
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

*ウストル*<br/>
結果として変換されたワイド文字の文字列を格納するアドレス。

*mbstr*<br/>
変換するマルチバイト文字列の場所への間接ポインター。

*count*<br/>
変換して*wcstr*に格納する最大文字数 (バイトではありません) です。

*mbstate*<br/>
**mbstate_t**変換状態オブジェクトへのポインター。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部**mbstate_t**オブジェクトはスレッド セーフではないため、常に独自の*mbstate*パラメーターを渡すことをお勧めします。

## <a name="return-value"></a>戻り値

正常に変換された文字数を返します (終端の null 文字があっても含まれません)。 エラーが発生した場合は (size_t)(-1) を返し **、errno**を EILSEQ に設定します。

## <a name="remarks"></a>解説

**mbsrtowcs**関数は *、 mbstr*によって間接的に指すマルチバイト文字の文字列を、 *mbstate*に含まれる変換状態を使用して*wcstr*が指すバッファーに格納されているワイド文字に変換します。 終端の NULL マルチバイト文字が検出されるか、現在のロケールの有効な文字に対応しないマルチバイトシーケンスが検出されるまで、または*カウント*文字が変換されるまで、各文字の変換が継続されます。 **mbsrtowcs**は *、カウント*が発生する前または時にマルチバイトのヌル文字 ('\0') を検出すると、それを 16 ビット終端の NULL 文字に変換して停止します。

したがって *、wcstr*のワイド文字ストリングは、変換中に**mbsrtowcs**がマルチバイトのヌル文字を検出した場合にのみ、ヌル終了されます。 *mbstr*と*wcstr*によって示されるシーケンスが重なっている場合 **、mbsrtowcs**の動作は未定義です。 **mbsrtowcs**は、現在のロケールのLC_TYPEカテゴリの影響を受けます。

**mbsrtowcs**関数は、その再起動性によって[_mbstowcs_l、mbstowcs](mbstowcs-mbstowcs-l.md)とは異なります。 変換状態は、同じ関数または他の再開可能な関数を呼び出す後続の呼び出しの場合は*mbstate*に格納されます。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば **、mbstowcs**の代わりに mbsrtowcs への後続の呼び出しを使用する場合は、mbsrlen ではなく**mbsrlen**を使用する必要があります。 **mbsrlen** **mbslen**

*wcstr*が null ポインターでない場合、終了 NULL 文字に達したために変換が停止した場合 *、mbstr*が指すポインター・オブジェクトにヌル・ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。

*wcstr*引数が null ポインターの場合 *、count*引数は無視され **、mbsrtowcs**は宛先ストリングに必要なサイズをワイド文字で返します。 *mbstate*が null ポインターの場合、関数は非スレッド セーフな静的内部mbstate_t変換状態オブジェクト**を**使用します。 文字シーケンス*mbstr*に対応するマルチバイト文字表現がない場合は、-1 が返され **、errno**が**EILSEQ**に設定されます。

*mbstr* isa null ポインターの場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し、-1 を返します。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「[セキュリティ保護されたテンプレート オーバーロード](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="exceptions"></a>例外

この関数が実行されている間、mbstate 引数が null ポインターでない限り、現在のスレッドで**setlocale**を呼び出す関数がない限り **、mbsrtowcs**関数はマルチスレッド セーフです。 *mbstate*

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**mbsrtowcs**|\<wchar.h>|

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbtowc、_mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
