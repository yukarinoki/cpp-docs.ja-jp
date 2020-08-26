---
title: /Qpar (自動並行化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: effe1ad7799022ea85184513de1dc48c72d6bfcb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839440"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (自動並行化)

コンパイラの [自動並行化](../../parallel/auto-parallelization-and-auto-vectorization.md) 機能を有効にして、コード内のループを自動的に並列化します。

## <a name="syntax"></a>構文

```
/Qpar
```

## <a name="remarks"></a>解説

コンパイラは、コード内で自動的にループを並列化するときに、複数のプロセッサコアに対して計算を分散します。 ループが並列化されるのは、コンパイラが有効であることを判断し、並列処理によってパフォーマンスが向上する場合のみです。

ディレクティブは、 `#pragma loop()` オプティマイザーが特定のループを並列化するために使用できます。 詳細については、「 [loop](../../preprocessor/loop.md)」を参照してください。

自動並行化の出力メッセージを有効にする方法の詳細については、「 [/Qpar-report (自動並行化 Reporting Level)](qpar-report-auto-parallelizer-reporting-level.md)」を参照してください。

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio で/Qpar コンパイラオプションを設定するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。

1. [ **プロパティページ** ] ダイアログボックスの [ **C/c + +**] で、[ **コマンドライン**] を選択します。

1. [ **追加オプション** ] ボックスに、「」と入力し `/Qpar` ます。

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>/Qpar コンパイラオプションをプログラムで設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。

## <a name="see-also"></a>関連項目

[/Q オプション (低レベルの操作)](q-options-low-level-operations.md)<br/>
[/Qpar-report (自動並行化レポートレベル)](qpar-report-auto-parallelizer-reporting-level.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>
[#pragma ループ ()](../../preprocessor/loop.md)<br/>
[Visual Studio でのネイティブコードベクター化](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
