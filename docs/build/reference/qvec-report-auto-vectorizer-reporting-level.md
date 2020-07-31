---
title: /Qvec-report (自動ベクター化レポート作成レベル)
ms.date: 11/04/2016
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
ms.openlocfilehash: 260cf89d50110f960eb6f320dccbb4a1d80f65bc
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373815"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (自動ベクター化レポート作成レベル)

コンパイラの[自動ベクター化](../../parallel/auto-parallelization-and-auto-vectorization.md)のレポート機能を有効にし、コンパイル時に出力する情報メッセージのレベルを指定します。

## <a name="syntax"></a>構文

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>解説

**/Qvec-report: 1**<br/>
ベクター化のループに関する情報メッセージを出力します。

**/Qvec-report: 2**<br/>
ベクター化とベクター化ではないループの情報メッセージを、理由コードと共に出力します。

理由コードとメッセージの詳細については、「[ベクター化 And 並行化 messages](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)」を参照してください。

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Visual Studio で/Qvec-report コンパイラオプションを設定するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。

1. [**プロパティページ**] ダイアログボックスの [ **C/c + +**] で、[**コマンドライン**] を選択します。

1. [**追加オプション**] ボックスに「」または「」と入力し `/Qvec-report:1` `/Qvec-report:2` ます。

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>/Qvec-report コンパイラオプションをプログラムで設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。

## <a name="see-also"></a>関連項目

[/Q オプション (低レベルの操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>
[Visual Studio でのネイティブコードベクター化](https://docs.microsoft.com/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
