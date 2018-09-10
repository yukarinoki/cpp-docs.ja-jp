---
title: -F (スタック サイズの設定) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /f
dev_langs:
- C++
helpviewer_keywords:
- set stack size compiler option
- F compiler option [C++]
- -F compiler option [C++]
- /F compiler option [C++]
- stack, setting size
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952933f72ae5d3f65aa646964ec6e04e758a27c6
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103776"
---
# <a name="f-set-stack-size"></a>/F (スタック サイズの設定)
プログラムのスタック サイズをバイト単位で設定します。

## <a name="syntax"></a>構文

> **/F** *数*

## <a name="arguments"></a>引数

*数*<br/>
スタック サイズ (バイト単位)。

## <a name="remarks"></a>Remarks

このオプションを指定せず、スタック サイズは 1 MB に既定値です。 *数*引数は、10 進数または C 言語表記で指定できます。 引数の範囲は 1 からリンカーによって受け付け最大スタック サイズです。 リンカーは、最も近い 4 バイトに指定した値を丸めます。 間のスペース **/F**と*数*は省略可能です。

プログラム スタック オーバーフローのメッセージを取得する場合は、スタック サイズを大きく必要があります。

スタック サイズを設定することもできます。

-   使用して、 **/stack**リンカー オプション。 詳細については、次を参照してください。 [/stack](../../build/reference/stack.md)します。

-   .Exe ファイルを EDITBIN を使用します。 詳細については、次を参照してください。 [EDITBIN リファレンス](../../build/reference/editbin-reference.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)