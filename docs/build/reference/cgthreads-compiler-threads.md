---
description: 詳細については、次を参照してください:/cgthreads (コンパイラスレッド)
title: /CGTHREADS (コンパイラ スレッド)
ms.date: 11/04/2016
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
ms.openlocfilehash: 71c5031c7013ec6f8ddad153d9cc16bee2004751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179253"
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

## <a name="remarks"></a>解説

**/Cgthreads** オプションは、リンク時のコード生成 ([/ltcg](ltcg-link-time-code-generation.md)) が指定されている場合に、コンパイルの最適化およびコード生成フェーズに対して並列で使用 cl.exe スレッドの最大数を指定します。 既定では、cl.exe は、 **/cgthreads: 4** が指定された場合と同様に4つのスレッドを使用します。 より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。

ビルドでは複数のレベルの並列化を指定できます。 msbuild.exe スイッチ **/maxcpucount** は、並列で実行できる MSBuild プロセスの数を指定します。 [/Mp (複数のプロセスを使用したビルド)](mp-build-with-multiple-processes.md)コンパイラフラグは、ソースファイルを同時にコンパイルする cl.exe プロセスの数を指定します。 [/Cgthreads](cgthreads-code-generation-threads.md)コンパイラオプションは、各 cl.exe プロセスによって使用されるスレッドの数を指定します。 プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。 プロジェクトを並行してビルドする方法の詳細については、「 [複数のプロジェクトの並行](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)ビルド」を参照してください。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **構成プロパティ**] の [ **リンカー** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. "**追加オプション**" プロパティを変更して **/cgthreads を含めます。** `number` ここで、 `number` は 1 ~ 8 の値で、[ **OK]** をクリックします。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC リンカー オプション](linker-options.md)<br/>
[MSVC リンカーのリファレンス](linking.md)
