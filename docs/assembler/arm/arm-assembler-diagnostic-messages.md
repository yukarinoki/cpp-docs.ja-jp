---
title: ARM アセンブラー診断メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1616b4bd9c4b64e771ec537a1b8cd7b582702222
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32052774"
---
# <a name="arm-assembler-diagnostic-messages"></a>ARM アセンブラー診断メッセージ
Microsoft ARM アセンブラー (*armasm*) ことを検出すると、診断に関する警告とエラーを出力します。 この記事では、一般的に発生メッセージについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## <a name="diagnostic-messages"></a>診断メッセージ  
  
### <a name="errors"></a>エラー  
 A2193: この命令で予期しない動作が生成されます。  
 ARM アーキテクチャでは、この命令の実行時の動作を保証できません。  適切に定義されたフォームこの命令の詳細についてを参照してください、 [ARM アーキテクチャ リファレンス マニュアル](http://go.microsoft.com/fwlink/p/?linkid=246464)です。  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196: 命令は 16 ビットでエンコードすることはできません。  
 指定された命令は、16 ビット Thumb 命令としてエンコードすることはできません。  16 ビット命令の範囲を先のラベルをさせるためにコードを再配置または 32 ビット命令を指定します。  
  
 アセンブラーしようと 16 ビット ブランチをエンコードし、このエラーで失敗する場合でも、32 ビット分岐は encodable します。 この問題を解決するを使用して、`.W`指定子を 32 ビットと分岐を明示的にマークします。  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202: Pre UAL 命令の構文が THUMB 領域では使用できません。  
 Thumb コードでは、Unified アセンブラー言語 (UAL) 構文を使用する必要があります。  古い構文は受け付けられません。  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513: 回転は、偶数でなければなりません  
 ARM モードでは、定数を指定するための代替構文があります。  作成する代わりに`#<const>`、記述することができます`#<byte>,#<rot>`、回転の値を取得する定数値を表す`<byte>`して`<rot>`です。  この構文を使用する場合は、値を行う必要があります`<rot>`もします。  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557: 正しくないバイト数への書き戻し  
 NEON 構造をロードおよびストア用命令 (`VLDn`、 `VSTn`)、ベース レジスタへの書き戻しを指定するための代替構文があります。  アドレスの後に感嘆符 (!) を設定する代わりには基底レジスタに追加するオフセットを示すイミディ エイト値を指定できます。  この構文を使用する場合は、読み込まれたか、または命令によって格納されるバイトの正確な数を指定する必要があります。  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### <a name="warnings"></a>警告  
 A4228: アラインメント値を超える領域の配置です。アラインメントが保証されません。  
 指定されている配置、`ALIGN`ディレクティブは、包含のアラインメントより大きい`AREA`です。  その結果、アセンブラーは保証できませんを`ALIGN`ディレクティブが有効となります。  
  
 これを解決するで指定することができます、`AREA`ディレクティブ、`ALIGN`目的の配置を示す属性です。  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508: この回転定数の使用は推奨されていません  
 ARM モードでは、定数を指定するための代替構文があります。  作成する代わりに`#<const>`、記述することができます`#<byte>,#<rot>`、回転の値を取得する定数値を表す`<byte>`して`<rot>`です。  一部のコンテキストで ARM はこれらの回転定数の使用を推奨していません。 このような場合は、基本的なを使用して`#<const>`構文代わりにします。  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509: 条件付きの命令のこのフォームは推奨されていません  
 この形式の条件付きの命令は ARMv8 アーキテクチャでは、ARM で廃止されました。 条件分岐を使用するコードを変更することをお勧めします。 どの条件付きの手順については引き続きサポートを表示するを参照してください、 [ARM アーキテクチャ リファレンス マニュアル](http://go.microsoft.com/fwlink/p/?linkid=246464)です。  
  
 この警告がないときに出力、`-oldit`コマンド ライン スイッチを使用します。  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## <a name="see-also"></a>関連項目  
 [ARM アセンブラーのコマンド ライン リファレンス](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM アセンブラー ディレクティブ](../../assembler/arm/arm-assembler-directives.md)