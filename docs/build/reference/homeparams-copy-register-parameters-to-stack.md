---
description: 詳細については、次を参照してください:/homeparams (レジスタパラメーターをスタックにコピー)
title: /homeparams (レジスタ パラメーターのスタックへのコピー)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: 52145534121831be256c3db2a6ccacdffb30b2c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191473"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (レジスタ パラメーターのスタックへのコピー)

レジスタで渡されたパラメーターも、関数の入力時にスタック上のその場所に書き込まれるようにします。

## <a name="syntax"></a>構文

> **/homeparams**

## <a name="remarks"></a>解説

このコンパイラオプションは、x64 を対象とするネイティブコンパイラとクロスコンパイラでのみ使用できます。

X64 呼び出し規約では、レジスタに渡されたパラメーターの場合でも、すべてのパラメーターにスタック領域を割り当てる必要があります。 詳細については、「 [パラメーターの引き渡し](../../build/x64-calling-convention.md#parameter-passing)」を参照してください。 既定では、レジスタパラメーターは、リリースビルドで割り当てられたスタック領域にコピーされません。 これにより、プログラムの最適化されたリリースビルドをデバッグすることが難しくなります。

リリースビルドでは、 **/homeparams** オプションを使用して、アプリケーションをデバッグできるようにするために、コンパイラに対してレジスタパラメーターのスタックへのコピーを強制することができます。 **/homeparams** は、レジスタパラメーターをスタックに読み込むために余分なサイクルが必要になるため、パフォーマンスの欠点を意味します。

デバッグビルドでは、常にレジスタで渡されるパラメーターがスタックに設定されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**  >  ] [**C/c + +**  >  **] [コマンドライン**] プロパティページを開きます。

1. [ **追加オプション** ] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
