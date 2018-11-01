---
title: MASM 演算子リファレンス
ms.date: 08/30/2018
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), operators reference
- operators [MASM]
ms.assetid: c069cab7-d6b0-4f82-a6ce-0ca3fc7e6428
ms.openlocfilehash: cb97c5dcb640b8d8592d842afd7dbb8cf9d0852c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50430460"
---
# <a name="masm-operators-reference"></a>MASM 演算子リファレンス

## <a name="arithmetic"></a>算術

||||
|-|-|-|
|[* (乗算)](operator-multiply.md)|[+ (加算)](operator-add.md)|[-(減算または否定)](operator-subtract-2.md)|
|[.(フィールド)](operator-dot.md)|[/(除算)](operator-subtract-1.md)|[&#91;&#93;(インデックス)](operator-brackets.md)|
|[MOD (剰余)](operator-mod.md)|||

## <a name="control-flow"></a>制御フロー

||||
|-|-|-|
|[\! (ランタイム論理 not)](operator-logical-not-masm-run-time.md)|[\!= (等しくないランタイム)](operator-not-equal-masm.md)|[&#124;&#124;(論理ランタイムまたは)](operator-logical-or.md)|
|[& & (論理ランタイムと)](operator-logical-and-masm-run-time.md)|[< (ランタイム未満)](operator-less-than-masm-run-time.md)|[\<= (以下のランタイム)](operator-less-or-equal-masm-run-time.md)|
|[(ランタイムと等しい) = =](operator-equal-masm-run-time.md)|[> (より大きいランタイム)](operator-greater-than-masm-run-time.md)|[> = (ランタイム大きいまたは等しい)](operator-greater-or-equal-masm-run-time.md)|
|[& (ビットごとのランタイムと)](operator-bitwise-and.md)|||
|[CARRY?(ランタイム実行のテスト)](operator-carry-q.md)|[OVERFLOW?(ランタイム オーバーフロー テスト)](operator-overflow-q.md)|[パリティでしょうか。(ランタイム パリティ テスト)](operator-parity-q.md)|
|[サインインしますか。(符号検定のランタイム)](operator-sign-q.md)|[0 か。(ランタイム 0 テスト)](operator-zero-q.md)||

## <a name="logical-and-shift"></a>論理と shift キー

||||
|-|-|-|
|[(ビットごとと)](operator-and.md)|[しない (ビット演算子 not)](operator-not.md)|[OR (ビットごとまたは)](operator-or.md)|
|[SHL (shift ビット左)](operator-shl.md)|[SHR (右シフト ビット)](operator-shr.md)|[XOR (排他的論理和または)](operator-xor.md)|

## <a name="macro"></a>マクロ

||||
|-|-|-|
|[\! (文字リテラル)](operator-logical-not-masm.md)|[% (テキストとして扱う)](operator-percent.md)||
|[;;(コメントとして扱う)](operator-semicolons.md)|[&lt; &gt; (1 つのリテラルとして扱う)](operator-literal.md)|[& & (パラメーターの値を置き換えてください)](operator-logical-and-masm.md)|

## <a name="miscellaneous"></a>その他

||||
|-|-|-|
|['' (文字列として扱う)](operator-single-quote.md)|[""(文字列として扱う)](operator-double-quote.md)||
|: (ローカルのラベルの定義)|: (セグメントとオフセットを登録する)|: (ラベルのグローバル定義)|
|[;(コメントとして扱う)](operator-semicolon.md)|[DUP (繰り返し宣言)](operator-dup.md)||

## <a name="record"></a>レコード

|||
|-|-|
|[マスク (レコードまたはフィールドのビットマスクを取得する)](operator-mask.md)|[幅 (レコードまたはフィールドの幅を取得する)](operator-width.md)|

## <a name="relational"></a>関係

||||
|-|-|-|
|[EQ (等しい)](operator-eq.md)|[GE (以上)](operator-ge.md)|[GT (より大きい)](operator-gt.md)|
|[LE (以下)](operator-le.md)|[LT (より小さい)](operator-lt.md)|[NE (等しくない)](operator-ne.md)|

## <a name="segment"></a>セグメント

|||
|-|-|
|[: (上書きをセグメント化)](operator-colon.md)|: (セグメントとオフセットを登録する)|
|[IMAGEREL (イメージの相対オフセット)](operator-imagerel.md)|[LROFFSET (ローダーは、オフセットを解決)](operator-lroffset.md)|
|[オフセット (セグメントの相対オフセット)](operator-offset.md)|[SECTIONREL (セクションの相対オフセット)](operator-sectionrel.md)|
|[SEG (get セグメント)](operator-seg.md)||

## <a name="type"></a>型

||||
|-|-|-|
|[高 (高 8 ビットの下位 16 ビット)](operator-high.md)|[HIGH32 (64 ビットの高い 32 ビット)](operator-high32.md)|[HIGHWORD (最下位の 32 ビットの上位 16 のビット)](operator-highword.md)|
|[長さ (配列内の要素の数)](operator-length.md)|[LENGTHOF (配列内の要素の数)](operator-lengthof.md)|[低 (下位 8 ビット)](operator-low.md)|
|[LOW32 (32 ビットを低)](operator-low32.md)|[LOWWORD (下位 16 ビット)](operator-lowword.md)|[OPATTR (引数の型情報の取得)](operator-opattr.md)|
|[PTR (ポインターをまたは型として)](operator-ptr.md)|[SHORT (短いラベルの種類)](operator-short.md)|[サイズ (型または変数のサイズ)](operator-size.md)|
|[SIZEOF (型または変数のサイズ)](operator-sizeof.md)|[この (現在の場所)](operator-this.md)|[型 (get 式の型)](operator-type.md)|
|[.型 (引数の型情報の取得)](operator-dot-type.md)|||

## <a name="see-also"></a>関連項目

[Microsoft Macro Assembler リファレンス](microsoft-macro-assembler-reference.md)<br/>
