---
title: コンパイラおよびリンカーでの Unicode サポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
dev_langs:
- C++
helpviewer_keywords:
- Unicode, Visual C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ec0b84cd62f3fcca378ab55de16006925e685b37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376193"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>コンパイラおよびリンカーでの Unicode のサポート

ほとんどの Visual C ビルド ツールは、Unicode の入力と出力をサポートします。

## <a name="filenames"></a>ファイル名

コマンドラインまたはコンパイラ ディレクティブを指定されたファイル名 (など`#include`) Unicode 文字を含めることがあります。

## <a name="source-code-files"></a>ソース コード ファイル

Unicode 文字には、識別子、マクロ、文字列リテラルおよび文字リテラル、およびコメントではサポートされています。  ユニバーサル文字名もサポートします。

Unicode は、次のエンコーディングのソース コード ファイルに入力できます。

- BOM (Byte Order Mark) 付き、または BOM なしの UTF-16 リトル エンディアン。

- BOM 付き、または BOM なしの UTF-16 ビッグ エンディアン。

- BOM 付きの UTF-8

## <a name="output"></a>出力

コンパイル時に、コンパイラは、utf-16 でコンソールに診断を出力します。  コンソールに表示できる文字は、コンソール ウィンドウのプロパティによって決まります  ファイルにリダイレクトされるコンパイラ出力は、現在の ANSI コンソール コードページになります。

## <a name="linker-response-files-and-def-files"></a>リンカー応答ファイルおよび .DEF ファイル

応答ファイルおよび DEF ファイルは、いずれかの utf-16 BOM、または ANSI を指定できます。

## <a name="asm-and-cod-dumps"></a>.asm ダンプおよび .cod ダンプ

.asm ダンプおよび .cod ダンプは、MASM との互換性のために、既定で ANSI になっています。 使用して[/FAu](../../build/reference/fa-fa-listing-file.md) utf-8 を出力します。 指定した場合 **/FAs**、混在したソースが直接は印刷だけされ、ソース コードが utf-8 を指定しなかった場合の例については、文字化けして見えます **/FAsu**です。

## <a name="see-also"></a>関連項目

[コマンドラインでの C/C++ コードのビルド](../../build/building-on-the-command-line.md)