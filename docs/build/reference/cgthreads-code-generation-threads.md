---
title: /cgthreads (コード生成スレッド)
ms.date: 11/04/2016
f1_keywords:
- /cgthreads
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
ms.openlocfilehash: 6c3d3b51691247ddef5614cae113ffa9ded576e9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57425238"
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (コード生成スレッド)

最適化とコード生成に使用するための cl.exe スレッドの数を設定します。

## <a name="syntax"></a>構文

```
/cgthreads[1-8]
```

## <a name="arguments"></a>引数

*number*<br/>
cl.exe が使用できるスレッドの最大数で、1 から 8 の範囲。

## <a name="remarks"></a>Remarks

**/Cgthreads**オプションは、cl.exe のスレッドの最大数を使用して並列での最適化およびコード コンパイルの生成のフェーズを指定します。 できませんの間にスペースに注意してください。 **/cgthreads**と`number`引数。 既定では、cl.exe は 4 つのスレッドを使用する場合と **/cgthreads4**指定されました。 より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。 このオプションと結合されている場合に特に役立ちます[/GL (Whole Program Optimization)](../../build/reference/gl-whole-program-optimization.md)します。

ビルドでは複数のレベルの並列化を指定できます。 Msbuild.exe スイッチ **/maxcpucount**並列に実行できる MSBuild プロセスの数を指定します。 [/MP (複数のプロセスを使用したビルド)](../../build/reference/mp-build-with-multiple-processes.md)コンパイラ フラグを同時にソース ファイルをコンパイルする cl.exe プロセスの数を指定します。 **/Cgthreads**オプションは、それぞれの cl.exe プロセスで使用されるスレッドの数を指定します。 プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。 プロジェクトの並行ビルドする方法の詳細については、次を参照してください。[複数プロジェクトの並行ビルド](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ**、 **C/C++** フォルダー。

1. 選択、**コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/cgthreads**`N`ここで、`N`は 1 から 8 の値を選び**OK**。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
