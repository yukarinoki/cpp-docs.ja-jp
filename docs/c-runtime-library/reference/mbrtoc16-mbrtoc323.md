---
title: mbrtoc16、mbrtoc323
ms.date: 11/04/2016
api_name:
- mbrtoc16
- mbrtoc32
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
ms.openlocfilehash: 52bcec5911fdc2ecbb073ae0042777aa4eb2b963
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952436"
---
# <a name="mbrtoc16-mbrtoc32"></a>mbrtoc16、mbrtoc32

半角文字列の最初のマルチバイト文字を等価の UTF-16 や UTF-32 の文字に変換します。

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

*インストール*<br/>
変換するマルチバイト文字に相当する**char16_t**または**char32_t**へのポインター。 null の場合、関数は値を格納しません。

*source*<br/>
変換するマルチバイト文字列へのポインター。

*max_bytes*<br/>
変換する文字を検査する*ソース*内の最大バイト数。 これには、*ソース*の残りのバイト数と、null 終端記号を含むバイト数の間の値を指定する必要があります。

*state*<br/>
マルチバイト文字列を1つ以上の出力文字に解釈するために使用される**mbstate_t**変換状態オブジェクトへのポインター。

## <a name="return-value"></a>戻り値

成功した場合、現在の*状態*の値に基づいて、次の条件が適用される最初の値が返されます。

|値|条件|
|-----------|---------------|
|0|*Source*から変換された次の*max_bytes*文字数は、null ワイド文字に相当します。これは、 *destination*が null でない場合に格納される値です。<br /><br /> *状態*には初期のシフト状態が含まれます。|
|1から*max_bytes*までの範囲|返される値は、有効なマルチバイト文字を完成させる*ソース*のバイト数です。 変換*先*が null でない場合は、変換されたワイド文字が格納されます。|
|-3|前の関数の呼び出しの結果として返される次のワイド文字が、 *destination*が null でない場合は、 *destination*に格納されています。 関数のこの呼び出しでは、*ソース*からのバイトは使用されません。<br /><br /> *ソース*が複数のワイド文字を表す必要があるマルチバイト文字を指している場合 (サロゲートペアなど)、次の関数呼び出しが追加の文字を書き出すように*state*値が更新されます。|
|-2|次の*max_bytes*バイトは、不完全であるが有効なマルチバイト文字を表します。 値が*変換先*に格納されていません。 この結果は、 *max_bytes*が0の場合に発生する可能性があります。|
|-1|エンコーディング エラーが発生しました。 次の*max_bytes*以下のバイトは、完全かつ有効なマルチバイト文字に寄与しません。 値が*変換先*に格納されていません。<br /><br /> **EILSEQ**は**errno**に格納され、変換状態の*状態*は指定されていません。|

## <a name="remarks"></a>Remarks

**Mbrtoc16**関数は、 *source*から最大*max_bytes*バイトを読み取り、最初の完全な有効なマルチバイト文字を検索してから、等価の utf-16 文字を*変換先*に格納します。 ソース バイトは、現在のスレッドのマルチバイト ロケールに従って解釈されます。 マルチバイト文字にサロゲートペアなどの複数の UTF-16 出力文字が必要な場合は、次に**mbrtoc16**を呼び出したときに、次の utf-16 文字が*宛先*に格納されるように*状態*値が設定されます。 **Mbrtoc32**関数は同じですが、出力は32文字として格納されます。

*Source*が null の場合、これらの関数は、 *destination*の場合は**null** 、 *source*の場合は 1、 *max_bytes*の場合は1を返します。 *Destination*と*max_bytes*の渡された値は無視されます。

*Source*が null でない場合、関数は文字列の先頭から開始し、最大*max_bytes*バイトを検査して、シフトシーケンスを含む次のマルチバイト文字を完了するために必要なバイト数を決定します。 検査したバイトの中に正しくかつ完全なマルチバイト文字が含まれる場合、関数はその文字を等価の 16 ビットや 32 ビットのワイド文字 1 つまたは複数に変換します。 *Destination*が null でない場合、関数は最初の (および場合によっては唯一の) 結果の文字を変換先に格納します。 追加の出力文字が必要な場合、値は*状態*で設定されるため、後続の関数の呼び出しで追加の文字が出力され、値-3 が返されます。 これ以上出力文字が不要な場合は、 *state*が初期のシフト状態に設定されます。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**mbrtoc16**、 **mbrtoc32**|\<uchar.h>|\<cuchar>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[c16rtomb、c32rtomb](c16rtomb-c32rtomb1.md)<br/>
[mbrtowc](mbrtowc.md)<br/>
[mbsrtowcs](mbsrtowcs.md)<br/>
[mbsrtowcs_s](mbsrtowcs-s.md)<br/>
