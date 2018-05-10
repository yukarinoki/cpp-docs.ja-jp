---
title: -O1、O2 (サイズを最小限に抑える、速度) |Microsoft ドキュメント
ms.custom: ''
ms.date: 09/25/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /o2
- /o1
dev_langs:
- C++
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d6bbe16cb3f33e048c08d36cb9cd3d5016d7987c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1、/O2 (プログラム サイズ、実行速度)

生成されたコードの速度とサイズに影響するオプションの定義済みセットを選択します。

## <a name="syntax"></a>構文

> /O1  
> /O2

## <a name="remarks"></a>コメント

**/O1**と **/O2**コンパイラ オプションで、一度にいくつかの特定の最適化オプションを設定する簡単な方法です。 **/O1**オプションは、多くの場合、最小のコードを作成する個々 の最適化オプションを設定します。 **/O2**オプションは、ほとんどの場合に最も高速のコードを作成するオプションを設定します。 **/O2**オプションは、リリース ビルドの既定値です。 この表の特定のオプションで設定されている **/O1**と **/O2**:

|オプション|相当する機能|
|------------|-------------------|
|**/O1** (サイズを最小限に抑える)|[/Og](../../build/reference/og-global-optimizations.md) [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/Gs](../../build/reference/gs-control-stack-checking-calls.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/O2** (速度を最大限に)|[/Og](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/Gs](../../build/reference/gs-control-stack-checking-calls.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/O1**と **/O2**は相互に排他的です。

> [!NOTE]  
> **x86 固有**  
> これらのオプションは、フレーム ポインターの省略の使用を意味 ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) オプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. **構成プロパティ**、開かれている**C/C++** を選択し、**最適化**プロパティ ページ。

1. 変更、**最適化**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)  
[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)