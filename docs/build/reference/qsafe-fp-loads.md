---
description: 詳細については、次を参照してください:/Qsafe_fp_loads
title: /Qsafe_fp_loads
ms.date: 01/24/2018
ms.openlocfilehash: e569b308d2da982c72775699ff2149daa45a8f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225519"
---
# <a name="qsafe_fp_loads"></a>/Qsafe_fp_loads

浮動小数点値の整数移動命令を要求し、特定の浮動小数点読み込み最適化を無効にします。

## <a name="syntax"></a>構文

> **/Qsafe_fp_loads**

## <a name="remarks"></a>解説

**/Qsafe_fp_loads** は、x86 を対象とするコンパイラでのみ使用できます。これは、x64 または ARM を対象とするコンパイラでは使用できません。

**/Qsafe_fp_loads** は、メモリと MMX レジスタ間でデータを移動するために、浮動小数点の移動命令ではなく、整数の移動命令を使用するようにコンパイラに強制します。 また、このオプションを指定すると、値の読み込み時に例外が発生する可能性がある場合 (NaN 値の読み込み時など)、複数のコントロール パスに読み込める浮動小数点値に対してレジスタ読み込み最適化が無効になります。

このオプションは、 [/fp: except](fp-specify-floating-point-behavior.md)でオーバーライドされます。 **/Qsafe_fp_loads** **/fp: except** によって指定されたコンパイラ動作のサブセットを指定します。

**/Qsafe_fp_loads** は [/clr](clr-common-language-runtime-compilation.md) および [/fp: fast](fp-specify-floating-point-behavior.md)と互換性がありません。 浮動小数点コンパイラオプションの詳細については、「 [/fp (Floating-Point 動作の指定)](fp-specify-floating-point-behavior.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **コマンドライン**] プロパティページを選択します。

1. [ **追加オプション** ] ボックスにコンパイラオプションを入力します。 **[OK]** を選択して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低レベルの操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
