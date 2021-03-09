---
description: 詳細については、「コンパイラとリンカーでの Unicode のサポート」を参照してください。
title: コンパイラおよびリンカーでの Unicode のサポート
ms.date: 03/07/2021
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: e1795a5a9b9d4a3a1672b2661aa598d0ef6e059f
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2021
ms.locfileid: "102465341"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>コンパイラおよびリンカーでの Unicode のサポート

ほとんどの Microsoft C/c + + (MSVC) ビルドツールは、Unicode 入力と出力をサポートしています。

## <a name="filenames"></a>ファイル名

コマンドラインまたはコンパイラディレクティブ (など) で指定されたファイル名には、 `#include` Unicode 文字を含めることができます。

## <a name="source-code-files"></a>ソース コード ファイル

Unicode 文字は、識別子、マクロ、文字列リテラル、文字リテラル、およびコメントでサポートされています。  ユニバーサル文字名もサポートされています。

Unicode は、次のエンコーディングのソース コード ファイルに入力できます。

- BOM (Byte Order Mark) 付き、または BOM なしの UTF-16 リトル エンディアン。

- BOM 付き、または BOM なしの UTF-16 ビッグ エンディアン。

- UTF-8 with BOM

Visual Studio IDE では、Unicode を含む複数のエンコード形式でファイルを保存できます。 [**保存**] ボタンのドロップダウンを使用して、[**ファイル名を付けて保存**] ダイアログに保存します。 ドロップダウンで [ **エンコード付きで保存** ] を選択します。 次に、[ **保存オプションの詳細設定** ] ダイアログボックスで、ドロップダウンリストからエンコードを選択します。 **[OK]** を選択して、ファイルを保存します。

## <a name="output"></a>出力

コンパイラは、コンパイル時に、UTF-16 で診断をコンソールに出力します。  コンソールに表示できる文字は、コンソール ウィンドウのプロパティによって決まります  ファイルにリダイレクトされるコンパイラ出力は、現在の ANSI コンソール コードページになります。

## <a name="linker-response-files-and-def-files"></a>リンカー応答ファイルと `.DEF` ファイル

応答ファイルと *`.DEF`* ファイルは、1つの BOM または ANSI を使用した utf-16 または utf-8 のいずれかになります。

## <a name="asm-and-cod-dumps"></a>`.asm` および `.cod` ダンプ

*`.asm`* および *`.cod`* ダンプは、MASM との互換性のために既定で ANSI になっています。 [`/FAu`](fa-fa-listing-file.md)Utf-8 を出力するには、を使用します。

を指定した場合 **`/FAs`** 、混在ソースは直接印刷されます。 たとえば、ソースコードが UTF-8 で、が指定されていない場合など **`/FAsu`** です。

## <a name="see-also"></a>関連項目

[コマンド ラインから MSVC ツールセットを使用する](../building-on-the-command-line.md)
