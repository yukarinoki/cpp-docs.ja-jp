---
description: 詳細については、「/Od (Disable (デバッグ))」を参照してください。
title: /Od (無効 (デバッグ))
ms.date: 11/04/2016
f1_keywords:
- /od
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
ms.openlocfilehash: 9d425244a1790a9bb74e1c92db88f32bb0372ab2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214306"
---
# <a name="od-disable-debug"></a>/Od (無効 (デバッグ))

プログラムのすべての最適化をオフにし、コンパイルを高速化します。

## <a name="syntax"></a>構文

```
/Od
```

## <a name="remarks"></a>解説

これが既定のオプションです。 **/Od** によってコードの移動が抑制されるため、デバッグプロセスが簡略化されます。 デバッグ用のコンパイラオプションの詳細については、「 [/Z7、/zi、/zi (デバッグ情報の形式)](z7-zi-zi-debug-information-format.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **最適化** ] プロパティページをクリックします。

1. **最適化** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/Z7、/Zi、/ZI (デバッグ情報の形式)](z7-zi-zi-debug-information-format.md)
