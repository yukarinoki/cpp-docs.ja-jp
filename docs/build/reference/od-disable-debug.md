---
title: -Od (無効 (デバッグ)) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /od
dev_langs:
- C++
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adfa2e2feaf44f5f29c1a16b8e68642e438095fe
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703327"
---
# <a name="od-disable-debug"></a>/Od (無効 (デバッグ))

すべてのプログラムでの最適化をオフにし、コンパイル速度が向上します。

## <a name="syntax"></a>構文

```
/Od
```

## <a name="remarks"></a>Remarks

このオプションは、既定値です。 **/Od**コードの移動を抑制しますが、デバッグ プロセスを簡略化されます。 デバッグ用のコンパイラ オプションの詳細については、次を参照してください。 [/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**最適化**プロパティ ページ。

1. 変更、**最適化**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)