---
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
ms.openlocfilehash: b7cbf8de06e698e67e370eb399da5bb00b262895
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595797"
---
# <a name="od-disable-debug"></a>/Od (無効 (デバッグ))

すべてのプログラムでの最適化をオフにし、コンパイル速度が向上します。

## <a name="syntax"></a>構文

```
/Od
```

## <a name="remarks"></a>Remarks

このオプションは、既定値です。 **/Od**コードの移動を抑制しますが、デバッグ プロセスを簡略化されます。 デバッグ用のコンパイラ オプションの詳細については、次を参照してください。 [/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**最適化**プロパティ ページ。

1. 変更、**最適化**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)