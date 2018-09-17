---
title: /Qsafe_fp_loads |Microsoft Docs
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0af28b391390f28be4e111b55c909dcae66ca2f8
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713662"
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads

浮動小数点値の整数移動命令を要求し、特定の浮動小数点読み込み最適化を無効にします。

## <a name="syntax"></a>構文

> **/Qsafe_fp_loads**

## <a name="remarks"></a>Remarks

**/Qsafe_fp_loads**のみコンパイラでは x86 を対象には、x64 または ARM を対象とするコンパイラで使用できることはできません。

**/Qsafe_fp_loads**強制的にコンパイラに浮動小数点移動命令ではなく整数移動命令を使用して、メモリと MMX の間のデータの移動を登録します。 また、このオプションを指定すると、値の読み込み時に例外が発生する可能性がある場合 (NaN 値の読み込み時など)、複数のコントロール パスに読み込める浮動小数点値に対してレジスタ読み込み最適化が無効になります。

このオプションは、によってオーバーライド[/fp: を除く](../../build/reference/fp-specify-floating-point-behavior.md)します。 **/Qsafe_fp_loads**で指定されているコンパイラの動作のサブセットを指定 **/fp: 除く**します。

**/Qsafe_fp_loads**と互換性がない[/clr](../../build/reference/clr-common-language-runtime-compilation.md)と[/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md)します。 浮動小数点コンパイラ オプションの詳細については、次を参照してください。 [/fp (浮動小数点の動作の指定)](../../build/reference/fp-specify-floating-point-behavior.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **コマンドライン**プロパティ ページ。

1. コンパイラ オプションを入力して、**追加オプション**ボックス。 選択**OK**して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
