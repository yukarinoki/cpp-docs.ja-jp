---
title: /Gw (グローバル データの最適化)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 406b1577b77f056e18753db10bae5675febe879e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50506692"
---
# <a name="gw-optimize-global-data"></a>/Gw (グローバル データの最適化)

グローバル データを最適化のために COMDAT セクションにパッケージ化します。

## <a name="syntax"></a>構文

```
/Gw[-]
```

## <a name="remarks"></a>Remarks

**/Gw**オプションは、個々 の COMDAT セクションで、パッケージのグローバル データ コンパイラ。 既定では、 **/Gw**がオフと明示的に有効にする必要があります。 これを明示的に無効にするを使用して **/Gw-** します。 ときに両方 **/Gw**と[/GL](../../build/reference/gl-whole-program-optimization.md)が有効にすると、リンカーを使用してプログラム全体の最適化またはマージする参照されないグローバル データを除外するために複数のオブジェクト ファイルの COMDAT セクションを比較するには同一読み取り専用のグローバル データ。 その結果、生成されるバイナリ実行可能ファイルのサイズが大幅に小さくなることがあります。

コンパイルしてリンクを別々 に使用できます、 [/OPT:REF](../../build/reference/opt-optimizations.md)でコンパイルされたオブジェクト ファイルで参照されないグローバル データの実行可能ファイルから除外するリンカー オプション、 **/Gw**オプション。

使用することも、 [/OPT:ICF](../../build/reference/opt-optimizations.md)と[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)で複数のオブジェクト ファイルと同じ読み取り専用グローバル データがコンパイルされた実行可能ファイルにマージするリンカー オプション、 **/Gw**オプション。

詳細については、次を参照してください。 [Introducing/Gw コンパイラ スイッチ](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx)Visual c チーム ブログにします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、 **C/C++** フォルダー。

1. 選択、**コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを **/Gw**選び、 **OK**します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)