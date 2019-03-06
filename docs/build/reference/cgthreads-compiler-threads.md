---
title: /CGTHREADS (コンパイラ スレッド)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: e2e1a51dcff46601034ed18292e9c4dcf4bd7d5c
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413941"
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (コンパイラ スレッド)

リンク時のコード生成を指定した場合に最適化とコード生成に使う cl.exe スレッドの数を設定します。

## <a name="syntax"></a>構文

```
/CGTHREADS:[1-8]
```

## <a name="arguments"></a>引数

*number*<br/>
cl.exe が使用できるスレッドの最大数で、1 から 8 の範囲。

## <a name="remarks"></a>Remarks

**/CGTHREADS**オプション並列コンパイルとリンク時の最適化およびコード生成のフェーズの cl.exe のスレッドの最大数を指定するコード生成 ([/LTCG](../../build/reference/ltcg-link-time-code-generation.md)) は、指定します。 既定では、cl.exe は 4 つのスレッドを使用する場合と **/CGTHREADS:4**指定されました。 より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。

ビルドでは複数のレベルの並列化を指定できます。 Msbuild.exe スイッチ **/maxcpucount**並列に実行できる MSBuild プロセスの数を指定します。 [/MP (複数のプロセスを使用したビルド)](../../build/reference/mp-build-with-multiple-processes.md)コンパイラ フラグを同時にソース ファイルをコンパイルする cl.exe プロセスの数を指定します。 [/Cgthreads](../../build/reference/cgthreads-code-generation-threads.md)コンパイラ オプションは、それぞれの cl.exe プロセスで使用されるスレッドの数を指定します。 プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。 プロジェクトの並行ビルドする方法の詳細については、次を参照してください。[複数プロジェクトの並行ビルド](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)します。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ**、**リンカー**フォルダー。

1. 選択、**コマンドライン**プロパティ ページ。

1. 変更、**追加のオプション**含めるプロパティを **/CGTHREADS:**`number`ここで、 `number` 1 から 8 の値は、選択**OK**。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[リンカー オプション](../../build/reference/linker-options.md)<br/>
[リンカー オプションの設定](../../build/reference/setting-linker-options.md)
