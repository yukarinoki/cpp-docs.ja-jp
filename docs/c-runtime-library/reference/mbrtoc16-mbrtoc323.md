---
title: mbrtoc16、mbrtoc323
ms.date: 4/2/2020
api_name:
- mbrtoc16
- mbrtoc32
- _o_mbrtoc16
- _o_mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: 91755d19eacf73f19700eed7fffbffc529d4e235
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340976"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16、mbrtoc32

文字列の最初の UTF-8 マルチバイト文字を、等価の UTF-16 または UTF-32 文字に変換します。

## <a name="syntax"></a>構文

```C
size_t mbrtoc16(
   char16_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);

size_t mbrtoc32(
   char32_t* destination,
   const char* source,
   size_t max_bytes,
   mbstate_t* state
);
```

### <a name="parameters"></a>パラメーター

*先*\
変換する utf-8 マルチバイト文字に相当する**char16_t**または**char32_t**へのポインター。 null の場合、関数は値を格納しません。

*ソース*\
変換する UTF-8 マルチバイト文字列へのポインター。

*max_bytes*\
変換する文字を調べる*ソース*内の最大バイト数。 この引数は、1 バイトとバイト数の間の値で、任意の null 終端文字を含め *、source*に残る値にする必要があります。

*状態*\
UTF-8 マルチバイト文字列を 1 つ以上の出力文字に変換するために使用される**mbstate_t**変換状態オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

成功した場合、現在の*状態*値を指定して、適用されるこれらの条件の最初の値を返します。

|[値]|条件|
|-----------|---------------|
|0|*次*にソースから変換される*文字max_bytes*以下は、null ワイド文字に対応します。 *destination*<br /><br /> *状態*には初期シフト状態が含まれています。|
|1 から*max_bytes*の間で、|返される値は、有効なマルチバイト文字を完了する*ソース*のバイト数です。 *変換後*文字が null でない場合、変換されたワイド文字が格納されます。|
|-3|関数への以前の呼び出しによって生成された次のワイド文字は、*宛先*が null でない場合、*宛先*に格納されています。 この関数の呼び出しでは *、ソース*からのバイトは消費されません。<br /><br /> *ソース*が UTF-8 マルチバイト文字を指し、複数のワイド文字を表す (サロゲート ペアなど) 場合、次の関数呼び出しが追加の文字を書き出すため、*状態*値が更新されます。|
|-2|次の*max_bytes*バイトは不完全だが、有効である可能性のある UTF-8 マルチバイト文字を表します。 *デスティネーション*には値が格納されません。 この結果は *、max_bytes*がゼロの場合に発生する可能性があります。|
|-1|エンコーディング エラーが発生しました。 次の*max_bytes以下の*バイトは、完全で有効な UTF-8 マルチバイト文字に影響を与えなくなります。 *デスティネーション*には値が格納されません。<br /><br /> **EILSEQ**は**errno**に格納され、変換*状態の状態*は指定されていません。|

## <a name="remarks"></a>解説

**mbrtoc16**関数は *、ソース*から最大*max_bytes*バイトを読み取って、最初の完全な有効な UTF-8 マルチバイト文字を見つけ、その後、対応する UTF-16 文字を*変換先*に格納します。 サロゲート ペアなど、文字に複数の UTF-16 出力文字が必要な場合、次に**mbrtoc16**を呼び出すと *、次*の UTF-16 文字が*送り先*に格納されます。 **mbrtoc32**関数は同じですが、出力は UTF-32 文字として格納されます。

*source*が null の場合、これらの関数は *、宛先*に対して**NULL** 、`""`*ソース*に対して空の NULL で終わる文字列 *、max_bytes*の場合は 1 の引数を使用して行われた呼び出しと同等の値を返します。 *宛先*と*max_bytes*の渡された値は無視されます。

*source*が null でない場合、関数は文字列の先頭から開始し、最大*max_bytes*バイトを検査して、シフト シーケンスを含む次の UTF-8 マルチバイト文字を完了するために必要なバイト数を決定します。 検査されたバイトに、有効で完全な UTF-8 マルチバイト文字が含まれている場合、関数は、その文字を同等の 16 ビットまたは 32 ビット幅の文字に変換します。 *変換先*が null でない場合、関数は最初の (場合によっては唯一の) 結果文字を宛先に格納します。 追加の出力文字が必要な場合は、state*に値*が設定され、関数の後続の呼び出しで追加の文字が出力され、値 -3 が返されます。 これ以上出力文字が必要ない場合、*状態*は初期シフト状態に設定されます。

UTF-8 以外のマルチバイト文字を UTF-16 LE 文字に変換するには[、mbrtowc](mbrtowc.md) [、mbtowc、または _mbtowc_l](mbtowc-mbtowc-l.md)関数を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**mbrtoc16** **,mbrtoc32**|\<uchar.h>|\<cuchar>|

互換性の詳細については、「[互換性](../compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../data-conversion.md)\
[ロケール](../locale.md)\
[マルチバイト文字シーケンスの解釈](../interpretation-of-multibyte-character-sequences.md)\
[c16rtomb, c32rtomb](c16rtomb-c32rtomb1.md)\
[mbrtowc](mbrtowc.md)\
[ムズルトウフス](mbsrtowcs.md)\
[mbsrtowcs_s](mbsrtowcs-s.md)
