---
title: コンパイラおよびリンカーでの Unicode のサポート
ms.date: 12/15/2017
f1_keywords:
- VC.Project.VCLinkerTool.UseUnicodeResponseFiles
- VC.Project.VCLibrarianTool.UseUnicodeResponseFiles
- VC.Project.VCCLCompilerTool.UseUnicodeResponseFiles
- VC.Project.VCXDCMakeTool.UseUnicodeResponseFiles
helpviewer_keywords:
- Unicode, Visual C++
ms.openlocfilehash: 420b01263320cf86df3f99da4523cc2b8bb4d4b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168838"
---
# <a name="unicode-support-in-the-compiler-and-linker"></a>コンパイラおよびリンカーでの Unicode のサポート

ほとんどのC++ Visual ビルドツールは、Unicode 入力と出力をサポートしています。

## <a name="filenames"></a>ファイル名

コマンドラインまたはコンパイラディレクティブ (`#include`など) で指定されたファイル名には、Unicode 文字を含めることができます。

## <a name="source-code-files"></a>ソース コード ファイル

Unicode 文字は、識別子、マクロ、文字列リテラル、文字リテラル、およびコメントでサポートされています。  ユニバーサル文字名もサポートされています。

Unicode は、次のエンコーディングのソース コード ファイルに入力できます。

- BOM (Byte Order Mark) 付き、または BOM なしの UTF-16 リトル エンディアン。

- BOM 付き、または BOM なしの UTF-16 ビッグ エンディアン。

- UTF-8 with BOM

## <a name="output"></a>Output

コンパイラは、コンパイル時に、UTF-16 で診断をコンソールに出力します。  コンソールに表示できる文字は、コンソール ウィンドウのプロパティによって決まります  ファイルにリダイレクトされるコンパイラ出力は、現在の ANSI コンソール コードページになります。

## <a name="linker-response-files-and-def-files"></a>リンカー応答ファイルおよび .DEF ファイル

応答ファイルと DEF ファイルには、BOM を使用した UTF-16 または ANSI のいずれかを指定できます。

## <a name="asm-and-cod-dumps"></a>.asm ダンプおよび .cod ダンプ

.asm ダンプおよび .cod ダンプは、MASM との互換性のために、既定で ANSI になっています。 [/FAu](fa-fa-listing-file.md)を使用して utf-8 を出力します。 **/Fa**を指定した場合、混在ソースは直接印刷されるだけで、ソースコードが utf-8 で、 **/FAsu**を指定していない場合などには、正しく表示されないことに注意してください。

## <a name="see-also"></a>参照

[コマンド ラインから MSVC ツールセットを使用する](../building-on-the-command-line.md)
