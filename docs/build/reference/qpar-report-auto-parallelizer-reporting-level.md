---
title: /Qpar-report (自動並行化レポート作成レベル)
ms.date: 11/04/2016
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
ms.openlocfilehash: 3a154bdf50e951ee932173cdb65f9e1514011245
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839414"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-report (自動並行化レポート作成レベル)

コンパイラの [自動並行化](../../parallel/auto-parallelization-and-auto-vectorization.md) のレポート機能を有効にし、コンパイル時に出力する情報メッセージのレベルを指定します。

## <a name="syntax"></a>構文

```
/Qpar-report:{1}{2}
```

## <a name="remarks"></a>解説

**/Qpar-report: 1**<br/>
並列化されたループに対する情報メッセージを出力します。

**/Qpar-report: 2**<br/>
並列化されたループと並列化されていないループの情報メッセージを理由コードと共に出力します。

メッセージは stdout に報告されます。 情報メッセージが報告されない場合、コードにループが含まれていないか、並列化されていないループが報告されるようにレポートのレベルが設定されていませんでした。 理由コードとメッセージの詳細については、「 [ベクター化 And 並行化 messages](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md)」を参照してください。

### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>/Qpar-report コンパイラ オプションを Visual Studio で設定するには

1. **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]** をクリックします。

1. [ **プロパティページ** ] ダイアログボックスの [ **C/c + +**] で、[ **コマンドライン**] を選択します。

1. [ **追加オプション** ] ボックスに「」または「」と入力し `/Qpar-report:1` `/Qpar-report:2` ます。

### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>/Qpar-report コンパイラ オプションをコードから設定するには

- <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。

## <a name="see-also"></a>関連項目

[/Q オプション (低レベルの操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)<br/>
[Visual Studio でのネイティブコードベクター化](/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
