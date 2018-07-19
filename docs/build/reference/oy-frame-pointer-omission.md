---
title: -Oy (フレーム ポインターの省略) |Microsoft ドキュメント
ms.custom: ''
ms.date: 09/22/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OmitFramePointers
- /oy
dev_langs:
- C++
helpviewer_keywords:
- omit frame pointer
- Oy compiler option [C++]
- stack frame pointer compiler option [C++]
- -Oy compiler option [C++]
- frame pointer omission compiler option [C++]
- suppress frame pointer creation
- /Oy compiler option [C++]
ms.assetid: c451da86-5297-4c5a-92bc-561d41379853
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b6feb682d364c4c40fd01e4aff33404c4506d9c1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377262"
---
# <a name="oy-frame-pointer-omission"></a>/Oy (フレーム ポインターの省略)

呼び出し履歴にフレーム ポインターが作成されなくなります。

## <a name="syntax"></a>構文

> /Oy [-]

## <a name="remarks"></a>コメント

このオプションを使用すると、フレーム ポインターを設定したり削除したりする必要がなくなるため、関数呼び出しが高速化されます。 また、レジスタ (Intel 386 以降では EBP) をもう 1 つ解放して、頻繁に使用される変数と部分式を格納します。

**/Oy**フレーム ポインターの省略を有効にし、 **/Oy-** の省略を無効にします。 **/Oy** x86 でのみ使用できますコンパイラです。

かどうかは、EBP ベースのアドレス指定、コードが必要とすることを指定する、 **/Oy-** 後オプション、 **/Ox**オプションを使用するか[最適化](../../preprocessor/optimize.md)で、"**y**"および**オフ**EBP ベースのアドレス指定最大限の最適化を取得する引数。 コンパイラは、EBP ベースのアドレス指定が必要な場所を検出します。たとえば、`_alloca` 関数および `setjmp` 関数や構造化例外処理が使われている場合にアドレス指定が必要です。

[/Ox (有効にする最も速度の最適化)](../../build/reference/ox-full-optimization.md)と[/O1、/O2 (サイズの最小化、最大速度)](../../build/reference/o1-o2-minimize-size-maximize-speed.md)オプションでは **/Oy**です。 指定する **/Oy-** 後、 **/Ox**、 **/O1**、または **/O2**オプションを無効に **/Oy**であるかどうか、明示的または暗黙的です。

**/Oy**コンパイラ オプションでは、コンパイラは、フレーム ポインター情報を表示しません。 ため困難のデバッガーを使用しています。 デバッグ コンパイラ オプションを指定する場合 ([/Z7、/Zi、/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)) を指定することをお勧め、 **/Oy-** 他の最適化コンパイラ オプションの後にオプションです。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **[C/C++]** フォルダーをクリックします。

1. クリックして、**最適化**プロパティ ページ。

1. 変更、**フレーム ポインターなし**プロパティです。 このプロパティが追加または削除のみ、 **/Oy**オプション。 追加する場合、 **/Oy-** オプションで、**コマンド ライン**および変更**追加オプション**です。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitFramePointers%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)

[コンパイラ オプション](../../build/reference/compiler-options.md)

[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)