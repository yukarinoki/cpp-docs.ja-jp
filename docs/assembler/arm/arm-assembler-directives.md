---
description: 詳細については、「ARM アセンブラディレクティブ」を参照してください。
title: ARM アセンブラー ディレクティブ
ms.date: 08/30/2018
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
ms.openlocfilehash: 8362453f2113922c5e834d1d68583b4199cf8d4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118119"
---
# <a name="arm-assembler-directives"></a>ARM アセンブラー ディレクティブ

ほとんどの場合、Microsoft ARM アセンブラーは arm アセンブリ言語を使用します。これは [Arm Compiler armasm リファレンスガイド](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)に記載されています。 ただし、一部のアセンブリディレクティブの Microsoft 実装は、ARM アセンブリディレクティブとは異なります。 この記事では、その違いについて説明します。

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>ARM アセンブリディレクティブの Microsoft 実装

- 領域

   Microsoft ARM アセンブラーは `AREA` `ALIGN` 、、、 `CODE` `CODEALIGN` 、 `DATA` `NOINIT` `READONLY` `READWRITE` `THUMB` `ARM` 、、、、、の各属性をサポートしています。

   およびを除くすべての `THUMB` `ARM` は、 [ARM コンパイラ Armasm リファレンスガイド](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html)に記載されているとおりに動作します。

   Microsoft ARM アセンブラーで、 `THUMB` `CODE` セクションに Thumb コードが含まれていることを示します。これがセクションの既定値です `CODE` 。  `ARM` セクションに ARM コードが含まれていることを示します。

- ATTR

   サポートされていません。

- コード

   サポートされていません。これは、Microsoft ARM アセンブラーで許可されていない UAL Thumb 構文を意味するためです。  `THUMB`代わりに、UAL 構文と共にディレクティブを使用します。

- 的

   共通領域のアラインメントの指定はサポートされていません。

- DCDO

   サポートされていません。

- `DN`, `QN`, `SN`

   レジスタエイリアスでの型またはレーンの指定はサポートされていません。

- ENTRY

   サポートされていません。

- EQU

   定義されたシンボルの型の指定はサポートされていません。

- `EXPORT` および `GLOBAL`

   次の構文を使用してエクスポートを指定します。

   > **エクスポート** |**グローバル** <em>sym</em>{**[**<em>種類</em>**]**}

   *sym* エクスポートするシンボルを指定します。  [*型*] を指定する場合は、 `[DATA]` シンボルがデータを指していることを示すか、 `[FUNC]` シンボルがコードを指していることを示すことができます。 `GLOBAL` は `EXPORT`のシノニムです。

- EXPORTAS

   サポートされていません。

- フレーム

   サポートされていません。

- `FUNCTION` および `PROC`

   アセンブリ構文では、呼び出し元の保存ファイルと呼び出し先で保存されるレジスタを一覧表示することによって、プロシージャのカスタム呼び出し規約を指定することができますが、Microsoft ARM アセンブラーは構文を受け入れますが、レジスタリストを無視します。  アセンブラによって生成されるデバッグ情報では、既定の呼び出し規約のみがサポートされます。

- `IMPORT` および `EXTERN`

   次の構文を使用してインポートを指定します。

   > **インポート** |**EXTERN** *Sym*{**、WEAK** *エイリアス*{**、型** *t*}}

   *sym* インポートするシンボルの名前を指定します。

   `WEAK`*別名* が指定されている場合は、 *sym* が外部の弱いものであることを示します。 リンク時にその定義が見つからない場合は、それに対するすべての参照が *エイリアス* にバインドされます。

   `TYPE` *T* が指定されている場合、 *t* はリンカーが *sym* の解決を試行する方法を示します。  *T* には次の値を指定できます。

   |値|説明|
   |-|-|
   |1|*Sym* のライブラリ検索を実行しない|
   |2|*Sym* のライブラリ検索を実行する|
   |3|*sym* *エイリアス* の別名 (既定値)|

   `EXTERN` はのシノニムです `IMPORT` 。ただし、 *sym* は、現在のアセンブリに参照がある場合にのみインポートされます。

- MACRO

   マクロの条件コードを保持するための変数の使用はサポートされていません。 マクロパラメーターの既定値はサポートされていません。

- NOFP

   サポートされていません。

- `OPT`, `TTL`, `SUBT`

   Microsoft ARM アセンブラーではリストが生成されないため、サポートされません。

- PRESERVE8

   サポートされていません。

- 配置

   `RELOC n` 命令またはデータ定義ディレクティブの後にのみ使用できます。 再配置できる "匿名シンボル" はありません。

- です

   サポートされていません。

- REQUIRE8

   サポートされていません。

- THUMBX

   Microsoft ARM アセンブラーが Thumb-2EE 命令セットをサポートしていないため、サポートされません。

## <a name="see-also"></a>関連項目

[ARM アセンブラー Command-Line リファレンス](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[ARM アセンブラー診断メッセージ](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
