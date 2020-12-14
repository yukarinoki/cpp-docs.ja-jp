---
description: 詳細情報:/Oy (フレームポインターの省略)
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
ms.openlocfilehash: dc0f9272bce5ad36840eac9ccdfc7e2465f7e3c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226299"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (フレーム ポインターの省略)

呼び出し履歴にフレーム ポインターが作成されなくなります。

## <a name="syntax"></a>構文

> /Oy [-]

## <a name="remarks"></a>解説

このオプションを使用すると、フレーム ポインターを設定したり削除したりする必要がなくなるため、関数呼び出しが高速化されます。 また、一般使用のためにもう1つのレジスタを解放します。

**/Oy** はフレームポインターの省略を有効にし、 **/Oy-** は省略を無効にします。 X64 コンパイラでは、 **/oy** と **/Oy-** は使用できません。

コードでフレームベースのアドレス指定が必要な場合は、 **/ox** オプションの後に **/Oy-** オプションを指定するか、"**y**" と "y" の引数を指定して [optimize](../../preprocessor/optimize.md)を使用し **て、フレーム** ベースのアドレス指定で最大限の最適化を実現することができます。 コンパイラは、フレームベースのアドレス指定が必要なほとんどの状況を検出します (たとえば、 `_alloca` および `setjmp` 関数と構造化例外処理を使用します)。

[/Ox (ほとんどの速度の最適化を有効にする)](ox-full-optimization.md)と [/O1、/O2 (サイズの最小化、最大速度)](o1-o2-minimize-size-maximize-speed.md)オプションは、 **/oy** を意味します。 **/Ox**、 **/O1**、または **/O2** オプションの後に **/Oy-** を指定すると、明示的か暗黙的かにかかわらず、 **/oy** が無効になります。

**/Oy** コンパイラオプションを使用すると、コンパイラによってフレームポインター情報が抑制されるため、デバッガーがより困難になります。 デバッグコンパイラオプション ([/Z7、/zi、/zi](z7-zi-zi-debug-information-format.md)) を指定する場合は、他の最適化コンパイラオプションの後に **/Oy-** オプションを指定することをお勧めします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **最適化**] プロパティページを選択します。

1. " **フレームポインターを省略** する" プロパティを変更します。 このプロパティは、 **/oy** オプションだけを追加または削除します。 **/Oy-** オプションを追加する場合は、[**コマンドライン**] プロパティページを選択し、**追加のオプション** を変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
