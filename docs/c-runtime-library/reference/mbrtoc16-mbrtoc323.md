---
title: mbrtoc16、mbrtoc323 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- mbrtoc16 function
- mbrtoc32 function
ms.assetid: 099ade4d-56f7-4e61-8b45-493f1d7a64bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a12e90f9a4bc0cc27df421c27d77a1b9b69334b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
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

*ソース*<br/>
変換するマルチバイト文字列へのポインター。

*max_bytes*<br/>
内のバイトの最大数*ソース*に変換する文字がないか調査します。 これは、値に残っている、null 終端文字を含むバイトの数と 1 つの値には*ソース*です。

*state*<br/>
ポインター、 **mbstate_t**変換状態オブジェクトが 1 つまたは複数の出力文字にマルチバイト文字列を解釈するために使用します。

## <a name="return-value"></a>戻り値

成功した場合、最初の値を返す、これらの状態が適用されるの与え現在*状態*値。

|[値]|条件|
|-----------|---------------|
|0|次*max_bytes*から変換された文字数の少ないまたは*ソース*場合格納される値は null ワイド文字に対応している*先*が null でないです。<br /><br /> *状態*初期のシフト状態が含まれています。|
|1 の間および*max_bytes*、包括的|返される値のバイト数は、*ソース*有効なマルチバイト文字を完了します。 場合に、変換されたワイド文字が格納されている*先*が null でないです。|
|-3|次のワイド文字関数を前回呼び出したときの結果が格納されている*先*場合*先*が null でないです。 バイトから*ソース*関数には、この呼び出しによって使用されません。<br /><br /> ときに*ソース*(たとえば、サロゲート ペア) を表す、1 つ以上のワイド文字を必要とするマルチバイト文字を指す、*状態*値は、次の関数呼び出しが書き込むように更新 out 文字を追加します。|
|-2|次*max_bytes*バイトが不完全なが有効になり得るマルチバイト文字を表します。 値が格納されていない*先*です。 この結果は、場合に発生する可能性が*max_bytes*ゼロです。|
|-1|エンコーディング エラーが発生しました。 次*max_bytes*以下のバイト数は、完全かつ有効なマルチバイト文字に寄与しません。 値が格納されていない*先*です。<br /><br /> **EILSEQ**に格納されて**errno**され、変換状態*状態*は指定されていません。|

## <a name="remarks"></a>コメント

**Mbrtoc16**関数まで読み取ります*max_bytes*からバイト*ソース*最初、完全な有効なマルチバイト文字とし、ストアと等価の utf-16 を検索するには文字内*先*です。 ソース バイトは、現在のスレッドのマルチバイト ロケールに従って解釈されます。 マルチバイト文字がサロゲート ペアなどの 1 つ以上の utf-16 出力文字が必要な場合、*状態*の次の utf-16 文字を格納する値を設定*先*に次の呼び出しで**mbrtoc16**です。 **Mbrtoc32**関数は、同一ですが、出力は utf-32 文字として格納します。

場合*ソース*が null の場合、戻り値のこれらの関数の呼び出しと同等の引数を使用して**NULL**の*先*、 **""** の*ソース*、1 を*max_bytes*です。 渡された値の*先*と*max_bytes*は無視されます。

場合*ソース*が null でない関数、文字列の先頭から開始を検査して最大*max_bytes*の次のマルチバイト文字を完了に必要なバイト数を決定するバイト数を含むシフト シーケンス。 検査したバイトの中に正しくかつ完全なマルチバイト文字が含まれる場合、関数はその文字を等価の 16 ビットや 32 ビットのワイド文字 1 つまたは複数に変換します。 場合*先*が null でない最初の (および場合によっては唯一の) 結果の文字を変換先の関数のストア。 値を設定する追加の出力文字が必要な場合、*状態*関数への後続の呼び出しが追加の文字を出力し、値-3 を返すようにします。 出力文字が必要な場合、し*状態*が初期のシフト状態に設定します。

## <a name="requirements"></a>要件

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
