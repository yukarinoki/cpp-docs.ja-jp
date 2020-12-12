---
description: 詳細情報:/Zo (最適化されたデバッグ機能の強化)
title: /Zo (最適化されたデバッグ機能の強化)
ms.date: 11/04/2016
f1_keywords:
- -Zo
- /Zo
helpviewer_keywords:
- Zo compiler option [C++]
- /Zo compiler option [C++]
- -Zo compiler option [C++]
ms.assetid: eea8d89a-7fe0-4fe1-86b2-7689bbebbd7f
ms.openlocfilehash: b2d5fb37205a6cf58492d7e6bc9080867ebacf54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224349"
---
# <a name="zo-enhance-optimized-debugging"></a>/Zo (最適化されたデバッグ機能の強化)

非デバッグ ビルドで最適化されたコードに関する拡張デバッグ情報を生成します。

## <a name="syntax"></a>構文

```cpp
/Zo[-]
```

## <a name="remarks"></a>解説

**/Zo** コンパイラスイッチは、最適化されたコードの強化されたデバッグ情報を生成します。 最適化では、ローカル変数にレジスターを使い、コードを並べ替え、ループをベクトル化し、関数呼び出しをインライン化することがあります。 これらの最適化により、ソース コードとコンパイル済みのオブジェクト コードの関係が不明瞭になる場合があります。 **/Zo** スイッチは、ローカル変数とインライン関数に関する追加のデバッグ情報を生成するようにコンパイラに指示します。 Visual Studio デバッガーで最適化されたコードをステップ実行するときに、[ **自動** 変数]、[ **ローカル**]、[ **ウォッチ** ] の各ウィンドウで変数を表示するために使用します。 また、スタック トレースを有効にして、WinDBG デバッガーでインライン関数を表示します。 最適化を無効にしたデバッグビルド ([/od](od-disable-debug.md)) では、 **/Zo** を指定した場合に生成される追加のデバッグ情報は必要ありません。 最適化が有効になっているリリース構成をデバッグするには、 **/Zo** スイッチを使用します。 最適化スイッチの詳細については、「 [/O オプション (コードの最適化)](o-options-optimize-code.md)」を参照してください。 **/Zi** または **/Z7** でデバッグ情報を指定すると、Visual Studio では **/Zo** オプションが既定で有効になります。 このコンパイラオプションを明示的に無効にするには、 **/Zo-** を指定します。

**/Zo** スイッチは Visual Studio 2013 Update 3 以降で使用できるようになり、前に記載されていない **/d2Zi +** スイッチが置き換えられます。

### <a name="to-set-the-zo-compiler-option-in-visual-studio"></a>Visual Studio で /Zo コンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳しくは、「[Visual Studio で C++ コンパイラとビルド プロパティを設定する](../working-with-project-properties.md)」をご覧ください。

1. [ **構成プロパティ**]、[ **c/c + +** ] フォルダーの順に選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. を含めるように " **追加オプション** " プロパティを変更し、[ `/Zo` **OK]** を選択します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[/Z7、/Zi、/ZI (デバッグ情報の形式)](z7-zi-zi-debug-information-format.md)<br/>
[エディット コンティニュ](/visualstudio/debugger/edit-and-continue)
