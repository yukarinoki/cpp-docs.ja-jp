---
title: -Zo (最適化されたデバッグ機能の強化) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- -Zo
- /Zo
dev_langs:
- C++
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b40f7b4fff1d6df6f5fb818e090ce687f12a7b4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412788"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (最適化されたデバッグ機能の強化)

非デバッグ ビルドで最適化されたコードに関する拡張デバッグ情報を生成します。

## <a name="syntax"></a>構文

```cpp
/Zo[-]
```

## <a name="remarks"></a>Remarks

**/Zo**コンパイラ スイッチが最適化されたコードに関する拡張デバッグ情報を生成します。 最適化では、ローカル変数にレジスターを使い、コードを並べ替え、ループをベクトル化し、関数呼び出しをインライン化することがあります。 これらの最適化により、ソース コードとコンパイル済みのオブジェクト コードの関係が不明瞭になる場合があります。 **/Zo**スイッチをローカル変数とインライン関数の追加のデバッグ情報を生成するコンパイラに指示します。 変数を参照して、 **[自動変数]**、**ローカル**と**ウォッチ**手順を実行したときに、Visual Studio デバッガーでコードを最適化します。 また、スタック トレースを有効にして、WinDBG デバッガーでインライン関数を表示します。 デバッグ ビルドの最適化を無効にしている ([/Od](../../build/reference/od-disable-debug.md)) ときに生成される追加のデバッグ情報は必要ありません **/Zo**を指定します。 使用して、 **/Zo**最適化が有効で、リリース構成をデバッグするスイッチ。 最適化スイッチの詳細については、次を参照してください。 [/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)します。 **/Zo**でデバッグ情報を指定すると、オプションが Visual Studio で既定で有効に **/Zi**または **/Z7**します。 指定 **/Zo-** このコンパイラ オプションを明示的に無効にします。

**/Zo**スイッチは、Visual Studio 2013 Update 3 以降を使用して、以前ドキュメントに未記載置き換わるもの **/d2Zi+** スイッチします。

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio で /Zo コンパイラ オプションを設定するには

1. 開く、**プロパティ ページ**プロジェクトのダイアログ ボックス。 詳細については、「[プロジェクト プロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. 選択、**構成プロパティ**、 **C/C++** フォルダー。

1. 選択、**コマンドライン**プロパティ ページ。

1. 変更、**追加オプション**含めるプロパティを`/Zo`選び、 **OK**します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](../../build/reference/o-options-optimize-code.md)<br/>
[/Z7、/Zi、/ZI (デバッグ情報の形式)](../../build/reference/z7-zi-zi-debug-information-format.md)<br/>
[エディット コンティニュ](/visualstudio/debugger/edit-and-continue)