---
title: -O1、O2 (サイズ最小化し、速度を最大化) |Microsoft Docs
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
ms.openlocfilehash: 24e57be50c2138cb9e772f6e6a2527300c9296ea
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446479"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1、/O2 (プログラム サイズ、実行速度)

定義済みのサイズに影響するオプションのセットと生成されるコードの速度を選択します。

## <a name="syntax"></a>構文

> /O1/O2

## <a name="remarks"></a>Remarks

**/O1**と **/O2**コンパイラ オプションで、一度にいくつかの特定の最適化オプションを設定する簡単な方法です。 **/O1**オプションは、ほとんどの場合に最小のコードを作成する個々 の最適化オプションを設定します。 **/O2**オプションは、ほとんどの場合に最も高速なコードを作成するオプションを設定します。 **/O2**オプションは、リリース ビルドの既定値。 この表に、特定のオプションが設定されている **/O1**と **/O2**:

|オプション|等価です。|
|------------|-------------------|
|**/O1** (サイズ最小化)|[/Og](../../build/reference/og-global-optimizations.md) [/Os](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|
|**/O2** (速度を最大化)|[/Og](../../build/reference/og-global-optimizations.md) [/Oi](../../build/reference/oi-generate-intrinsic-functions.md) [/Ot](../../build/reference/os-ot-favor-small-code-favor-fast-code.md) [/Oy](../../build/reference/oy-frame-pointer-omission.md) [/Ob2](../../build/reference/ob-inline-function-expansion.md) [/GF](../../build/reference/gf-eliminate-duplicate-strings.md) [/Gy](../../build/reference/gy-enable-function-level-linking.md)|

**/O1**と **/O2**は相互に排他的です。

> [!NOTE]
> **x86 固有**これらのオプションでは、フレーム ポインターの省略の使用 ([/Oy](../../build/reference/oy-frame-pointer-omission.md)) オプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **構成プロパティ**、オープン**C/C++** 選択し、**最適化**プロパティ ページ。

1. 変更、**最適化**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)
