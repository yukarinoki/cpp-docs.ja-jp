---
title: MASM オペレーターリファレンス
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: c29b173a1dcf29c297e41f136044599fbd5218a5
ms.sourcegitcommit: e15b46ea7888dbdd7e0bb47da76aeed680c3c1f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/17/2020
ms.locfileid: "86446464"
---
# <a name="masm-operators-reference"></a>MASM オペレーターリファレンス

## <a name="arithmetic"></a>算術

:::row:::
   :::column span="":::
      [`*`乗じる](operator-multiply.md)<br/>[`+`アドイン](operator-add.md)<br/>[`-`(減算または反転)](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.`分野](operator-dot.md)<br/>[`/`8060](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]`化](operator-brackets.md)<br/>[`MOD`後述](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>制御フロー

:::row:::
   :::column span="":::
      [`!`(ランタイム論理 not)](operator-logical-not-masm-run-time.md)<br/>[`!=`(ランタイムが等しくない)](operator-not-equal-masm.md)<br/>[`||`(ランタイム論理 or)](operator-logical-or.md)<br/>[`&&`(ランタイム論理 and)](operator-logical-and-masm-run-time.md)<br/>[`<`(ランタイムより小さい)](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=`(実行時間が少ないか等しい)](operator-less-or-equal-masm-run-time.md)<br/>[`==`(ランタイム equal)](operator-equal-masm-run-time.md)<br/>[`>`(より大きいランタイム)](operator-greater-than-masm-run-time.md)<br/>[`>=`(以上のランタイム)](operator-greater-or-equal-masm-run-time.md)<br/>[`&`(ランタイムビットごとの and)](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?`(ランタイムのキャリーテスト)](operator-carry-q.md)<br/>[`OVERFLOW?`(ランタイムオーバーフローテスト)](operator-overflow-q.md)<br/>[`PARITY?`(ランタイムパリティテスト)](operator-parity-q.md)<br/>[`SIGN?`(ランタイム署名テスト)](operator-sign-q.md)<br/>[`ZERO?`(ランタイムゼロテスト)](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>論理 and シフト

:::row:::
   :::column span="":::
      [`AND`(ビットごとの and)](operator-and.md)<br/>[`NOT`(ビットごとの not)](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR`(ビットごとの or)](operator-or.md)<br/>[`SHL`(左シフトビット)](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR`(ビットシフト右)](operator-shr.md)<br/>[`XOR`(ビットごとの排他的 or)](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>マクロ

:::row:::
   :::column span="":::
      [`!`(文字リテラル)](operator-logical-not-masm.md)<br/>[`%`(テキストとして扱う)](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;`(コメントとして扱う)](operator-semicolons.md)<br/>[`< >`(1 つのリテラルとして扱う)](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &`(代替パラメーター値)](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>その他

:::row:::
   :::column span="":::
      [`' '`(文字列として扱う)](operator-single-quote.md)<br/>[`" "`(文字列として扱う)](operator-double-quote.md)<br/>`:`(ローカルラベル定義)
   :::column-end:::
   :::column span="":::
      `::`(レジスタセグメントとオフセット)<br/>`::`(グローバルラベル定義)
   :::column-end:::
   :::column span="":::
      [`;`(コメントとして扱う)](operator-semicolon.md)<br/>[`DUP`(繰り返し宣言)](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>Record

:::row:::
   :::column span="":::
      [`MASK`(レコードまたはフィールドのビットマスクを取得します)](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH`(レコードまたはフィールドの幅を取得)](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>リレーショナル

:::row:::
   :::column span="":::
      [`EQ`つの](operator-eq.md)<br/>[`GE`(より大きいまたは等しい)](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT`(より大きい)](operator-gt.md)<br/>[`LE`(以下)](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT`(より小さい)](operator-lt.md)<br/>[`NE`(等しくない)](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>Segment

:::row:::
   :::column span="":::
      [`:`(セグメントのオーバーライド)](operator-colon.md)<br/>`::`(レジスタセグメントとオフセット)<br/>[`IMAGEREL`(画像の相対オフセット)](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET`(ローダーによって解決されたオフセット)](operator-lroffset.md)<br/>[`OFFSET`(セグメントの相対オフセット)](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL`(セクション相対オフセット)](operator-sectionrel.md)<br/>[`SEG`(セグメントの取得)](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>型

:::row:::
   :::column span="":::
      [`HIGH`(16 ビット以上の上位8ビット)](operator-high.md)<br/>[`HIGH32`(64 ビットの上位32ビット)](operator-high32.md)<br/>[`HIGHWORD`(最低32ビットの上位16ビット)](operator-highword.md)<br/>[`LENGTH`(配列内の要素数)](operator-length.md)<br/>[`LENGTHOF`(配列内の要素数)](operator-lengthof.md)<br/>[`LOW`(低8ビット)](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32`(低32ビット)](operator-low32.md)<br/>[`LOWWORD`(16 ビット)](operator-lowword.md)<br/>[`OPATTR`(引数の型の情報を取得します)](operator-opattr.md)<br/>[`PTR`(または型としてのポインター)](operator-ptr.md)<br/>[`SHORT`(短いラベルの種類としてマークします)](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE`(型または変数のサイズ)](operator-size.md)<br/>[`SIZEOF`(型または変数のサイズ)](operator-sizeof.md)<br/>[`THIS`(現在の場所)](operator-this.md)<br/>[`TYPE`(式の型を取得)](operator-type.md)<br/>[`.TYPE`(引数の型の情報を取得します)](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>関連項目

[Microsoft マクロアセンブラーリファレンス](microsoft-macro-assembler-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
