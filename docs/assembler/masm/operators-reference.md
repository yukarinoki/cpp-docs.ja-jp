---
title: MASM オペレーターリファレンス
ms.date: 07/15/2020
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: db79473f5d4264b869eeac334fa7957cfe553364
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88830944"
---
# <a name="masm-operators-reference"></a>MASM オペレーターリファレンス

## <a name="arithmetic"></a>算術

:::row:::
   :::column span="":::
      [`*` 乗じる](operator-multiply.md)\
      [`+` アドイン](operator-add.md)\
      [`-` (減算または反転)](operator-subtract-2.md)
   :::column-end:::
   :::column span="":::
      [`.` 分野](operator-dot.md)\
      [`/` 8060](operator-subtract-1.md)
   :::column-end:::
   :::column span="":::
      [`[]` 化](operator-brackets.md)\
      [`MOD` 後述](operator-mod.md)
   :::column-end:::
:::row-end:::

## <a name="control-flow"></a>制御フロー

:::row:::
   :::column span="":::
      [`!` (ランタイム論理 not)](operator-logical-not-masm-run-time.md)\
      [`!=` (ランタイムが等しくない)](operator-not-equal-masm.md)\
      [`||` (ランタイム論理 or)](operator-logical-or.md)\
      [`&&` (ランタイム論理 and)](operator-logical-and-masm-run-time.md)\
      [`<` (ランタイムより小さい)](operator-less-than-masm-run-time.md)
   :::column-end:::
   :::column span="":::
      [`<=` (実行時間が少ないか等しい)](operator-less-or-equal-masm-run-time.md)\
      [`==` (ランタイム equal)](operator-equal-masm-run-time.md)\
      [`>` (より大きいランタイム)](operator-greater-than-masm-run-time.md)\
      [`>=` (以上のランタイム)](operator-greater-or-equal-masm-run-time.md)\
      [`&` (ランタイムビットごとの and)](operator-bitwise-and.md)
   :::column-end:::
   :::column span="":::
      [`CARRY?` (ランタイムのキャリーテスト)](operator-carry-q.md)\
      [`OVERFLOW?` (ランタイムオーバーフローテスト)](operator-overflow-q.md)\
      [`PARITY?` (ランタイムパリティテスト)](operator-parity-q.md)\
      [`SIGN?` (ランタイム署名テスト)](operator-sign-q.md)\
      [`ZERO?` (ランタイムゼロテスト)](operator-zero-q.md)
   :::column-end:::
:::row-end:::

## <a name="logical-and-shift"></a>論理 and シフト

:::row:::
   :::column span="":::
      [`AND` (ビットごとの and)](operator-and.md)\
      [`NOT` (ビットごとの not)](operator-not.md)
   :::column-end:::
   :::column span="":::
      [`OR` (ビットごとの or)](operator-or.md)\
      [`SHL` (左シフトビット)](operator-shl.md)
   :::column-end:::
   :::column span="":::
      [`SHR` (ビットシフト右)](operator-shr.md)\
      [`XOR` (ビットごとの排他的 or)](operator-xor.md)
   :::column-end:::
:::row-end:::

## <a name="macro"></a>マクロ

:::row:::
   :::column span="":::
      [`!` (文字リテラル)](operator-logical-not-masm.md)\
      [`%` (テキストとして扱う)](operator-percent.md)
   :::column-end:::
   :::column span="":::
      [`;;` (コメントとして扱う)](operator-semicolons.md)\
      [`< >` (1 つのリテラルとして扱う)](operator-literal.md)
   :::column-end:::
   :::column span="":::
      [`& &` (代替パラメーター値)](operator-logical-and-masm.md)
   :::column-end:::
:::row-end:::

## <a name="miscellaneous"></a>その他

:::row:::
   :::column span="":::
      [`' '` (文字列として扱う)](operator-single-quote.md)\
      [`" "` (文字列として扱う)](operator-double-quote.md)\
      `:` (ローカルラベル定義)
   :::column-end:::
   :::column span="":::
      `::` (登録セグメントとオフセット) \
      `::` (グローバルラベル定義)
   :::column-end:::
   :::column span="":::
      [`;` (コメントとして扱う)](operator-semicolon.md)\
      [`DUP` (繰り返し宣言)](operator-dup.md)
   :::column-end:::
:::row-end:::

## <a name="record"></a>Record

:::row:::
   :::column span="":::
      [`MASK` (レコードまたはフィールドのビットマスクを取得します)](operator-mask.md)
   :::column-end:::
   :::column span="2":::
      [`WIDTH` (レコードまたはフィールドの幅を取得)](operator-width.md)
   :::column-end:::
:::row-end:::

## <a name="relational"></a>関係

:::row:::
   :::column span="":::
      [`EQ` つの](operator-eq.md)\
      [`GE` (より大きいまたは等しい)](operator-ge.md)
   :::column-end:::
   :::column span="":::
      [`GT` (より大きい)](operator-gt.md)\
      [`LE` (以下)](operator-le.md)
   :::column-end:::
   :::column span="":::
      [`LT` (より小さい)](operator-lt.md)\
      [`NE` (等しくない)](operator-ne.md)
   :::column-end:::
:::row-end:::

## <a name="segment"></a>Segment

:::row:::
   :::column span="":::
      [`:` (セグメントのオーバーライド)](operator-colon.md)\
      `::` (登録セグメントとオフセット) \
      [`IMAGEREL` (画像の相対オフセット)](operator-imagerel.md)
   :::column-end:::
   :::column span="":::
      [`LROFFSET` (ローダーによって解決されたオフセット)](operator-lroffset.md)\
      [`OFFSET` (セグメントの相対オフセット)](operator-offset.md)
   :::column-end:::
   :::column span="":::
      [`SECTIONREL` (セクション相対オフセット)](operator-sectionrel.md)\
      [`SEG` (セグメントの取得)](operator-seg.md)
   :::column-end:::
:::row-end:::

## <a name="type"></a>Type

:::row:::
   :::column span="":::
      [`HIGH` (16 ビット以上の上位8ビット)](operator-high.md)\
      [`HIGH32` (64 ビットの上位32ビット)](operator-high32.md)\
      [`HIGHWORD` (最低32ビットの上位16ビット)](operator-highword.md)\
      [`LENGTH` (配列内の要素数)](operator-length.md)\
      [`LENGTHOF` (配列内の要素数)](operator-lengthof.md)\
      [`LOW` (低8ビット)](operator-low.md)
   :::column-end:::
   :::column span="":::
      [`LOW32` (低32ビット)](operator-low32.md)\
      [`LOWWORD` (16 ビット)](operator-lowword.md)\
      [`OPATTR` (引数の型の情報を取得します)](operator-opattr.md)\
      [`PTR` (または型としてのポインター)](operator-ptr.md)\
      [`SHORT` (短いラベルの種類としてマークします)](operator-short.md)
   :::column-end:::
   :::column span="":::
      [`SIZE` (型または変数のサイズ)](operator-size.md)\
      [`SIZEOF` (型または変数のサイズ)](operator-sizeof.md)\
      [`THIS` (現在の場所)](operator-this.md)\
      [`TYPE` (式の型を取得)](operator-type.md)\
      [`.TYPE` (引数の型の情報を取得します)](operator-dot-type.md)
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>関連項目

[Microsoft マクロアセンブラーリファレンス](microsoft-macro-assembler-reference.md)\
[MASM BNF 文法](masm-bnf-grammar.md)
