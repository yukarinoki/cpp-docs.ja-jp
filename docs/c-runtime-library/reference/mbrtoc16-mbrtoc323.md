---
title: mbrtoc16、mbrtoc323
ms.date: 11/04/2016
apiname:
- mbrtoc16
- mbrtoc32
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
- mbrtoc16
- mbrtoc32
- uchar/mbrtoc16
- uchar/mbrtoc32
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
ms.openlocfilehash: f8573ac321772d19141be0228891b290ba48b217
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51520143"
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

*変換先*<br/>
ポインター、 **char16_t**または**char32_t**に変換するマルチバイト文字に相当します。 null の場合、関数は値を格納しません。

*source*<br/>
変換するマルチバイト文字列へのポインター。

*max_bytes*<br/>
内のバイトの最大数*ソース*変換する文字をチェックします。 これに残り、null 終端文字を含むバイトの数と 1 つの値を指定する必要があります*ソース*します。

*state*<br/>
ポインターを**mbstate_t**変換状態オブジェクトが 1 つまたは複数の出力文字にマルチバイト文字列を解釈するために使用します。

## <a name="return-value"></a>戻り値

成功した場合、最初の値を返しますが適用されるこれらの条件の指定、現在*状態*値。

|[値]|条件|
|-----------|---------------|
|0|次*max_bytes*から変換された文字数が少ないまたは*ソース*場合に格納された値は null ワイド文字に対応して*先*が null でないです。<br /><br /> *状態*初期のシフト状態が含まれています。|
|1 の間および*max_bytes*までの値|返される値のバイト数は、*ソース*有効なマルチバイト文字を完了します。 場合に変換されたワイド文字が格納されている*先*が null でないです。|
|-3|次のワイド文字関数は、以前の呼び出しの結果が保存されて*先*場合*先*が null でないです。 バイトから*ソース*関数には、この呼び出しによって使用されません。<br /><br /> ときに*ソース*(たとえば、サロゲート ペア) を表す、1 つ以上のワイド文字を必要とするマルチバイト文字を指す、*状態*値が更新されるため、次の関数呼び出しを書き込みます 追加する文字。|
|-2|次*max_bytes*バイトは、不完全で、可能性のある有効なマルチバイト文字ですが。 値は格納されません*先*します。 この結果は、場合に発生する可能性が*max_bytes*は 0 です。|
|-1|エンコーディング エラーが発生しました。 次*max_bytes*または以下のバイトは、完全かつ有効なマルチバイト文字には影響しません。 値は格納されません*先*します。<br /><br /> **EILSEQ**は**errno**され、変換状態*状態*が指定されていません。|

## <a name="remarks"></a>Remarks

**Mbrtoc16**関数は、最大読み取ります*max_bytes*からバイト*ソース*最初、完全な有効なマルチバイト文字とし、ストアと等価の utf-16 を検索するには文字内で*先*します。 ソース バイトは、現在のスレッドのマルチバイト ロケールに従って解釈されます。 マルチバイト文字がサロゲート ペアなどの 1 つ以上の utf-16 出力文字が必要な場合、*状態*設定は次の utf-16 文字を格納する*先*に次の呼び出しで**mbrtoc16**します。 **Mbrtoc32**関数は、同一ですが、出力は utf-32 文字として格納されます。

場合*ソース*null、戻り値のこれらの関数の引数を使用すると同等の呼び出しが行われた**NULL**の*先*、 **""** の*ソース*、1 を*max_bytes*します。 渡された値の*先*と*max_bytes*は無視されます。

場合*ソース*が null でない関数、文字列の先頭から開始し、最大を調べます*max_bytes*の次のマルチバイト文字の完了に必要なバイト数を決定するバイトを含むシフト シーケンス。 検査したバイトの中に正しくかつ完全なマルチバイト文字が含まれる場合、関数はその文字を等価の 16 ビットや 32 ビットのワイド文字 1 つまたは複数に変換します。 場合*先*が null でない最初 (かつ場合によっては唯一) の結果の文字を変換先の関数のストア。 値を設定する追加の出力文字が必要な場合は、*状態*関数への後続の呼び出しは追加の文字を出力し、値-3 を返すようにします。 出力文字が必要な場合、し*状態*が初期のシフト状態に設定します。

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
