---
description: '詳細情報: ARM アセンブラー診断メッセージ'
title: ARM アセンブラー診断メッセージ
ms.date: 08/30/2018
f1_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
helpviewer_keywords:
- A2193
- A2196
- A2202
- A2513
- A2557
- A4228
- A4508
- A4509
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
ms.openlocfilehash: 91e4640c161cbb58522c3680ae5decdb4cc1e992
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118200"
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM アセンブラー診断メッセージ

Microsoft ARM アセンブラ (*armasm*) は、診断の警告とエラーが発生したときにエラーを出力します。 この記事では、最も一般的に発生するメッセージについて説明します。

## <a name="syntax"></a>構文

> <em>ファイル名</em>**(**<em>行番号</em>**):** \[ **エラー** | **警告**] <em>number</em>**:** *message*

## <a name="diagnostic-messages---errors"></a>診断メッセージ-エラー

> A2193: この命令は、予期しない動作を生成します

ARM アーキテクチャは、この命令が実行されたときの動作を保証できません。  この命令の適切に定義された形式の詳細については、 [ARM アーキテクチャリファレンスマニュアル](https://go.microsoft.com/fwlink/p/?linkid=246464)を参照してください。

```asm
    ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior
```

> A2196: 命令を16ビットでエンコードすることはできません

指定された命令を16ビットの Thumb 命令としてエンコードすることはできません。  32ビット命令を指定するか、ターゲットラベルを16ビット命令の範囲に戻すようにコードを再配置します。

アセンブラーは、16ビットのブランチをエンコードしようとして、32ビットの分岐が encodable であっても、このエラーで失敗する場合があります。 この問題を解決するには、指定子を使用して `.W` 、分岐を32ビットとして明示的にマークします。

```asm
    ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits

    B.W label             ; OK
    B.N label             ; A2196: instruction cannot be encoded in 16 bits
    SPACE 10000
label
```

> A2202: UAL 命令の構文は THUMB 領域で許可されていません

Thumb コードでは、統合アセンブラー言語 (UAL) 構文を使用する必要があります。  古い構文は受け入れられなくなりました

```asm
    ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region
    ADDSEQ r0, r1         ; OK
```

> A2513: ローテーションは偶数である必要があります

ARM モードでは、定数を指定するための別の構文があります。  を記述する代わりに `#<const>` 、を使用 `#<byte>,#<rot>` して値を右に回転させることによって取得される定数値を表すを記述でき `<byte>` `<rot>` ます。  この構文を使用する場合は、の値を偶数にする必要があり `<rot>` ます。

```asm
    MOV r0, #4, #2       ; OK
    MOV r0, #4, #1       ; A2513: Rotation must be even
```

> A2557: 書き戻すバイト数が正しくありません

ネオン構造の読み込みおよびストア命令 ( `VLDn` 、 `VSTn` ) では、ベースレジスタに書き戻しを指定するための別の構文があります。  アドレスの後に感嘆符 (!) を挿入する代わりに、基本レジスタに追加するオフセットを示すイミディエイト値を指定できます。  この構文を使用する場合は、命令によって読み込まれた、または保存された正確なバイト数を指定する必要があります。

```asm
    VLD1.8 {d0-d3}, [r0]!         ; OK
    VLD1.8 {d0-d3}, [r0], #32     ; OK
    VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back
```

## <a name="diagnostic-messages---warnings"></a>診断メッセージ-警告

> A4228: アラインメント値が領域の配置を超えています。配置は保証されません

ディレクティブで指定されたアラインメントが、それを囲むのアラインメントを超えてい `ALIGN` `AREA` ます。  その結果、アセンブラーはディレクティブが受け入れられることを保証できません `ALIGN` 。

この問題を解決するには、ディレクティブに対して、目的のアラインメント以上の属性を指定し `AREA` `ALIGN` ます。

```asm
AREA |.myarea1|
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed

AREA |.myarea2|,ALIGN=3
ALIGN 8           ; OK
```

> A4508: この回転定数の使用は推奨されていません

ARM モードでは、定数を指定するための別の構文があります。  を記述する代わりに `#<const>` 、を使用 `#<byte>,#<rot>` して値を右に回転させることによって取得される定数値を表すを記述でき `<byte>` `<rot>` ます。  一部のコンテキストでは、ARM ではこれらの回転定数の使用が非推奨とされています。 このような場合は、代わりに基本構文を使用し `#<const>` ます。

```asm
    ANDS r0, r0, #1                ; OK
    ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated
```

> A4509: この形式の条件付き命令は推奨されていません

この形式の条件付き命令は、ARMv8 アーキテクチャでは ARM によって非推奨とされています。 条件分岐を使用するようにコードを変更することをお勧めします。 まだサポートされている条件付き命令については、 [ARM アーキテクチャリファレンスマニュアル](https://go.microsoft.com/fwlink/p/?linkid=246464)を参照してください。

この警告は、 **-oldit** コマンドラインスイッチが使用されている場合は生成されません。

```asm
    ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated
```

## <a name="see-also"></a>関連項目

[ARM アセンブラー Command-Line リファレンス](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM アセンブラーディレクティブ](../../assembler/arm/arm-assembler-directives.md)<br/>
