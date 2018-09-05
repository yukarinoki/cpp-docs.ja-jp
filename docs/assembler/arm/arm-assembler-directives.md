---
title: ARM アセンブラー ディレクティブ |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
dev_langs:
- C++
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 282d8bbd55bec8053961c709eb3733a65972b187
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693114"
---
# <a name="arm-assembler-directives"></a>ARM アセンブラー ディレクティブ

ほとんどの場合、Microsoft ARM アセンブラーが記載されている ARM アセンブリ言語を使用して、 [ARM コンパイラ armasm リファレンス ガイド](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)します。 ただし、一部のアセンブリ ディレクティブの Microsoft 実装には、ARM アセンブリ ディレクティブによって異なります。 この記事では、相違点について説明します。

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>Microsoft の実装の ARM アセンブリ ディレクティブ

`AREA`<br/>
これらをサポートする Microsoft ARM アセンブラー`AREA`属性: `ALIGN`、 `CODE`、 `CODEALIGN`、 `DATA`、 `NOINIT`、 `READONLY`、 `READWRITE`、 `THUMB`、`ARM`します。

除くすべて`THUMB`と`ARM`に記載されている作業、 [ARM コンパイラ armasm リファレンス ガイド](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)します。

Microsoft ARM アセンブラー、`THUMB`ことを示します、`CODE`セクションが Thumb コードが含まれの既定値は、`CODE`セクション。  `ARM` ARM コードにはセクションが含まれていることを示します。

`ATTR`<br/>
サポートされていません。

`CODE16`<br/>
Microsoft ARM アセンブラーが許可されていない pre UAL Thumb 構文を使用すると、発生するので、サポートされていません。  使用して、`THUMB`代わりに、UAL 構文と共にディレクティブ。

`COMMON`<br/>
一般的な領域の配置の仕様がサポートされていません。

`DCDO`<br/>
サポートされていません。

`DN`、`QN`、`SN`<br/>
型またはレジスタ エイリアスのレーンの仕様がサポートされていません。

`ENTRY`<br/>
サポートされていません。

`EQU`<br/>
定義されているシンボルの型の仕様がサポートされていません。

`EXPORT` および `GLOBAL`

> **エクスポート** <em>sym</em>{**[**<em>型</em>**]**}

*sym*はエクスポートする記号です。  [*型*]、指定した場合いずれかになります`[DATA]`シンボル データをポイントすることを示すまたは`[FUNC]`をシンボルがコードを指していることを示します。

`GLOBAL` シノニムです`EXPORT`します。

`EXPORTAS`<br/>
サポートされていません。

`FRAME`<br/>
サポートされていません。

`FUNCTION` および `PROC`<br/>
Assembly 構文は、カスタムの仕様をサポートしていますは、呼び出し元の保存と呼び出し先保存されるレジスタの一覧を表示して、プロシージャの呼び出し規約、Microsoft ARM アセンブラーは、構文を受け入れますが、レジスタの一覧を無視します。  アセンブラーによって生成されるデバッグ情報には、既定の呼び出し規約のみがサポートしています。

`IMPORT` および `EXTERN`

> **インポート** *sym*{**、弱い***エイリアス*{**、型** *t*}}

*sym*をインポートするシンボルの名前を指定します。

場合`WEAK`*エイリアス*が指定されていることを示します*sym*弱い外部です。 リンク時に、その定義が見つからないかどうかへの参照がすべてをバインドする代わりに*エイリアス*します。

場合`TYPE` *t*が指定されると、 *t*解決するのには、リンカーを試みる必要がある方法を示します*sym*します。  これらの値の*t*が考えられます。<br/>
1-ライブラリの検索を実行しない*sym*<br/>
2: ライブラリの検索を実行*sym*<br/>
3-*sym*の別名です*エイリアス*(既定値)

`EXTERN` シノニムです`IMPORT`ことを除いて、 *sym*への参照が現在のアセンブリである場合にのみをインポートします。

`MACRO`<br/>
マクロの条件コードを保持する変数の使用がサポートされていません。 既定の値はマクロのパラメーターがサポートされていません。

`NOFP`<br/>
サポートされていません。

`OPT`、`TTL`、`SUBT`<br/>
Microsoft ARM アセンブラーが番組表を生成しないため、サポートされていません。

`PRESERVE8`<br/>
サポートされていません。

`RELOC`<br/>
`RELOC n` 命令またはデータ定義ディレクティブしか従うことができます。 これは、シンボルがありません。"匿名"を再配置することができます。

`REQUIRE`<br/>
サポートされていません。

`REQUIRE8`<br/>
サポートされていません。

`THUMBX`<br/>
Microsoft ARM アセンブラーは 2 ee のつまみの命令セットをサポートしていないためにサポートされていません。

## <a name="see-also"></a>関連項目

[ARM アセンブラーのコマンド ライン リファレンス](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM アセンブラー診断メッセージ](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
