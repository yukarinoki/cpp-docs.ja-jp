---
description: 詳細情報:/F (スタックサイズの設定)
title: /F (スタック サイズの設定)
ms.date: 11/04/2016
f1_keywords:
- /f
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
ms.openlocfilehash: 5bf8b0855c65fc39caf8935b06a877c62a4e0df0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200781"
---
# <a name="f-set-stack-size"></a>/F (スタック サイズの設定)

プログラムのスタックサイズをバイト単位で設定します。

## <a name="syntax"></a>構文

> **/F** *番号*

## <a name="arguments"></a>引数

*number*<br/>
バイト単位のスタックサイズ。

## <a name="remarks"></a>解説

このオプションを指定しない場合、スタックサイズは既定で 1 MB に設定されます。 *Number* 引数には、10進表記または C 言語表記を使用できます。 引数は、1からリンカーが受け入れる最大スタックサイズまでの範囲で指定できます。 リンカーは、指定された値を最も近い4バイトに切り上げます。 **/F** と *number* の間のスペースは省略可能です。

プログラムがスタックオーバーフローメッセージを取得した場合は、スタックサイズの増加が必要になることがあります。

スタックサイズは、次の方法で設定することもできます。

- **/STACK** リンカーオプションを使用します。 詳細については、「 [/STACK](stack.md)」を参照してください。

- .Exe ファイルで EDITBIN を使用します。 詳細については、「 [EDITBIN リファレンス](editbin-reference.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
