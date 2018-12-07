---
title: /Oy (フレーム ポインターの省略)
ms.date: 11/19/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
ms.openlocfilehash: 343b0e026c2932e97d4a8d4472ba2035d6302661
ms.sourcegitcommit: 3da2cb3ec85e77ddfd4d2a55edb133d580ce4f18
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/27/2018
ms.locfileid: "52330391"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (フレーム ポインターの省略)

呼び出し履歴にフレーム ポインターが作成されなくなります。

## <a name="syntax"></a>構文

> /Oy [-]

## <a name="remarks"></a>Remarks

このオプションを使用すると、フレーム ポインターを設定したり削除したりする必要がなくなるため、関数呼び出しが高速化されます。 一般的な使用法のレジスタのもう 1 つも解放します。

**/Oy**フレーム ポインターの省略を有効および **/Oy-** の省略を無効にします。 X64 コンパイラでは、 **/Oy**と **/Oy-** は使用できません。

指定できるかどうか、コードは、フレーム ベースのアドレス指定を必要とする、 **/Oy-** オプションの後ろ、 **/Ox**オプションまたは使用[最適化](../../preprocessor/optimize.md)で、"**y**"と**オフ**最大限の最適化フレーム ベースのアドレス指定を取得する引数。 コンパイラは、フレーム ベースのアドレス指定が必要になるほとんどの状況を検出 (たとえば、`_alloca`と`setjmp`関数と構造化例外処理)。

[/Ox (有効にする最もの速度の最適化)](../../build/reference/ox-full-optimization.md)と[/O1、/O2 (サイズの最小化、速度の最大化)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)オプションでは **/Oy**します。 指定する **/Oy-** 後、 **/Ox**、 **/O1**、または **/O2**オプションを無効にします **/Oy**がかどうか、明示的または黙示を問わずします。

**/Oy**コンパイラ フレーム ポインター情報を抑制するため、難しくのデバッガーを使用してコンパイラ オプションは。 デバッグ コンパイラ オプションを指定する場合 ([/Z7、/Zi、/ZI](../../build/reference/z7-zi-zi-debug-information-format.md))、指定することをお勧め、 **/Oy-** 他の最適化コンパイラ オプションの後のオプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **最適化**プロパティ ページ。

1. 変更、**フレーム ポインターなし**プロパティ。 このプロパティが追加または削除のみ、 **/Oy**オプション。 追加する場合、 **/Oy-** オプションを選択し、**コマンド ライン**プロパティ ページ、および変更**追加オプション**します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
