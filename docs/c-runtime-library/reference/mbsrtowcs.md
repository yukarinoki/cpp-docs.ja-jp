---
title: mbsrtowcs | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ccb5bda16238888905678ffb3b6de01b93555ad0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405433"
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
最大文字数 (バイトではなく) を変換し、保存する*wcstr*です。

*呼び出すため*<br/>
ポインター、 **mbstate_t**変換状態オブジェクト。 この値が null ポインターの場合、静的な内部変換状態オブジェクトが使用されます。 内部**mbstate_t**オブジェクトはスレッド セーフであることをお勧めを常に渡す独自*呼び出すため*パラメーター。

## <a name="return-value"></a>戻り値

正常に変換された文字数を返します (終端の null 文字があっても含まれません)。 返します (size_t)(-1) 場合は、エラーが発生し、設定**errno** EILSEQ にします。

## <a name="remarks"></a>コメント

**Mbsrtowcs**関数が直接に指すマルチバイト文字の文字列に変換します*mbstr*が指すバッファーに格納されているワイド文字に*wcstr*により、含まれる変換状態を使用して*呼び出すため*です。 変換が続行されます文字ごとに、終端 null マルチバイト文字が出現するまで、現在のロケールで有効な文字に対応しないマルチバイト シーケンスが発生した、またはまで*カウント*文字が変換されています。 場合**mbsrtowcs**前に、またはときにマルチバイト null 文字 ('\0') が発生した*カウント*発生すると、16 ビット終端の null 文字と停止に変換します。

したがって、ワイド文字列で*wcstr*が null で終わる場合にのみ**mbsrtowcs**変換中にマルチバイト null 文字を検出します。 シーケンスを指す場合*mbstr*と*wcstr*などの動作の重複**mbsrtowcs**が定義されていません。 **mbsrtowcs**は、現在のロケールの LC_TYPE カテゴリの影響を受けます。

**Mbsrtowcs**関数とは異なります[mbstowcs、_mbstowcs_l](mbstowcs-mbstowcs-l.md)によって、再起動します。 変換状態が格納されている*呼び出すため*以降の呼び出し、同じまたは再開可能なその他の関数にします。 再開可能な関数と再開不可能な関数を混用した場合、結果は未定義です。  たとえば、アプリケーションを使用する必要があります**mbsrlen**の代わりに**mbslen**場合、後続の呼び出しには、 **mbsrtowcs**の代わりに使用される**mbstowcs**.

場合*wcstr*が null のポインターでないポインター オブジェクトを指す*mbstr*終端の null 文字に達したために、変換が停止した場合に null ポインターが割り当てられます。 それ以外の場合、変換された最後のマルチバイト文字がある場合は、その後ろのアドレスが割り当てられます。 これにより、後続の関数呼び出しで、この呼び出しが停止した場所から変換を再開できます。

場合、 *wcstr*引数が null のポインター、*カウント*引数は無視されますと**mbsrtowcs**変換先の文字列のワイド文字で必要なサイズを返します。 場合*呼び出すため*null ポインターでは、関数の使用、スレッド セーフでは非静的な内部**mbstate_t**変換状態オブジェクト。 場合文字シーケンス*mbstr*が対応するマルチバイト文字の表現、-1 が返され、 **errno**に設定されている**EILSEQ**です。

場合*mbstr* 」の説明に従って、null ポインターである無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、-1 を返します。

C++ では、この関数にテンプレートのオーバーロードがあります。このオーバーロードは、この関数に対応するセキュリティで保護された新しい関数を呼び出します。 詳細については、「 [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md)」を参照してください。

## <a name="exceptions"></a>例外

**Mbsrtowcs**関数が呼び出す関数、現在のスレッドがない限り、マルチ スレッド セーフは**setlocale、_wsetlocale**この関数を実行している限り、*呼び出すため*引数が null ポインターではありません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
