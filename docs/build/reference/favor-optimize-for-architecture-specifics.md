---
description: 詳細について:/favor (アーキテクチャの詳細の最適化)
title: /favor (アーキテクチャ固有の最適化)
ms.date: 11/04/2016
f1_keywords:
- /favor
helpviewer_keywords:
- -favor compiler option [C++]
- /favor compiler option [C++]
ms.assetid: ad264df2-e30f-4d68-8bd0-10d6bee71a2a
ms.openlocfilehash: 184e81e1007214a09088601b6c579692a0dd20a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192305"
---
# <a name="favor-optimize-for-architecture-specifics"></a>/favor (アーキテクチャ固有の最適化)

**/favor:** `option` 特定のアーキテクチャ、または AMD および Intel アーキテクチャのマイクロアーキテクチャの仕様に合わせて最適化されたコードを生成します。

## <a name="syntax"></a>構文

> **/favor:**{**blend**  |  **ATOM**  |  **AMD64**  |  **INTEL64**}

## <a name="remarks"></a>解説

**/favor: blend**<br/>
(x86 および x64) は、AMD および Intel アーキテクチャのマイクロアーキテクチャの仕様に合わせて最適化されたコードを生成します。 **/Favor: blend** は、特定のプロセッサで可能な限り最高のパフォーマンスを得られない場合がありますが、さまざまな x86 および x64 プロセッサで最高のパフォーマンスを提供するように設計されています。 既定では、 **/favor: blend** が有効になっています。

**/favor: ATOM**<br/>
(x86 および x64) は、Intel Atom プロセッサおよび Intel セントリーノ Atom プロセッサテクノロジの仕様に合わせて最適化されたコードを生成します。 **/Favor: ATOM** を使用して生成されたコードは、intel プロセッサ用の intel SSSE3、SSE3、SSE2、および SSE 命令を生成することもあります。

**/favor: AMD64**<br/>
(x64 のみ) AMD Opteron 用に生成されたコードと、64ビットの拡張をサポートする Athlon プロセッサを最適化します。 最適化されたコードは、すべての x64 互換プラットフォームで実行できます。 **/Favor: AMD64** を使用して生成されたコードは、Intel64 をサポートする Intel プロセッサのパフォーマンスが悪化する可能性があります。

**/favor: INTEL64**<br/>
(x64 のみ) Intel64 をサポートする Intel プロセッサ用に生成されたコードを最適化します。通常は、そのプラットフォームのパフォーマンスが向上します。 生成されたコードは、任意の x64 プラットフォームで実行できます。 **/Favor: INTEL64** で生成されるコードでは、AMD Opteron のパフォーマンスが低下したり、64ビットの拡張をサポートする Athlon プロセッサが発生したりする可能性があります。

> [!NOTE]
> Intel64 アーキテクチャは、以前は拡張メモリ64テクノロジと呼ばれていましたが、対応するコンパイラオプションは **/favor: EM64T** でした。

X64 アーキテクチャのプログラミング方法の詳細については、「 [X64 Software 規約](../x64-software-conventions.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **C/c + +** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション** ] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
