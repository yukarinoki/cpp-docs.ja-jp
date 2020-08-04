---
title: /cgthreads (コード生成スレッド)
ms.date: 07/31/2020
f1_keywords:
- /cgthreads
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
ms.openlocfilehash: 319a42ab68f02df6019ff283f1039ef3d561c4a0
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520876"
---
# <a name="cgthreads-code-generation-threads"></a>`/cgthreads`(コード生成スレッド)

最適化とコード生成に使用するための cl.exe スレッドの数を設定します。

## <a name="syntax"></a>構文

> **`/cgthreads1`**\
> **`/cgthreads2`**\
> **`/cgthreads3`**\
> **`/cgthreads4`**\
> **`/cgthreads5`**\
> **`/cgthreads6`**\
> **`/cgthreads7`**\
> **`/cgthreads8`**

## <a name="arguments"></a>引数

**`cgthreadsN`**\
cl.exe が使用するスレッドの最大数。 *N*は 1 ~ 8 の範囲の数値です。

## <a name="remarks"></a>Remarks

オプションは、 **`cgthreads`** コンパイルの最適化およびコード生成のフェーズで並列に使用 cl.exe スレッドの最大数を指定します。 **`cgthreads`** と*number*引数の間にはスペースを使用できないことに注意してください。 既定では、が指定されている場合と同様に、cl.exe は4つのスレッドを使用し **`/cgthreads4`** ます。 使用可能なプロセッサコアが多い場合は、*数値*を大きくするとビルド時間が短縮されます。 このオプションは、 [ `/GL` (プログラム全体の最適化)](gl-whole-program-optimization.md)と組み合わせた場合に特に便利です。

ビルドでは複数のレベルの並列化を指定できます。 msbuild.exe スイッチは、 **`/maxcpucount`** 並列で実行できる MSBuild プロセスの数を指定します。 [ `/MP` (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)コンパイラフラグは、ソースファイルを同時にコンパイルする cl.exe プロセスの数を指定します。 オプションは、 **`cgthreads`** 各 cl.exe プロセスによって使用されるスレッドの数を指定します。 プロセッサは、プロセッサコアの数と同時に実行できるスレッドは1つだけです。 これらのオプションのすべてに対して大きな値を同時に指定することはできず、逆の場合もあります。 プロジェクトを並行してビルドする方法の詳細については、「[複数のプロジェクトの並行](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)ビルド」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [**追加オプション**] プロパティを変更して **`cgthreadsN`** 、を含めます。ここで、 *`N`* は 1 ~ 8 の値です。次に、[ **OK]** を選択します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
