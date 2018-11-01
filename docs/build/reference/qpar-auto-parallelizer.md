---
title: /Qpar (自動並行化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
ms.openlocfilehash: c75770f834abcf17862e173e692129a43a5155c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588696"
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (自動並行化)

により、[自動並行化](../../parallel/auto-parallelization-and-auto-vectorization.md)を自動的にコード内のループを並列化するコンパイラの機能です。

## <a name="syntax"></a>構文

```
/Qpar
```

## <a name="remarks"></a>Remarks

コンパイラは、コード内のループを並列化に自動的に、複数のプロセッサ コア間で計算が分散されます。 ループを並列化するようにすることは、パフォーマンスが向上する並列処理、コンパイラが判断した場合のみです。

`#pragma loop()`ディレクティブは、オプティマイザーで特定のループを並列化に使用できます。 詳細については、次を参照してください。[ループ](../../preprocessor/loop.md)します。

自動並行化の出力メッセージを有効にする方法については、次を参照してください。 [/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)します。

### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio で/Qpar コンパイラ オプションを設定するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。

1. **プロパティ ページ**ダイアログ ボックスで、 **C/C++**、**コマンド ライン**。

1. **追加オプション**ボックスに、入力`/Qpar`します。

### <a name="to-set-the-qpar-compiler-option-programmatically"></a>/Qpar コンパイラ オプションをプログラムで設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)<br/>
[/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[#pragma loop()](../../preprocessor/loop.md)<br/>
[ネイティブ コードでの並列プログラミング](https://blogs.msdn.microsoft.com/nativeconcurrency/2012/04/12/auto-vectorizer-in-visual-studio-2012-overview/)