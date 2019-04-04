---
title: /Ge (スタック プローブの有効化)
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: a785ec041370e0bcbb2ce8b698bfba89235a0a0c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812136"
---
# <a name="ge-enable-stack-probes"></a>/Ge (スタック プローブの有効化)

ローカル変数のストレージを必要とされるすべての関数呼び出しでスタック プローブをアクティブにします。

## <a name="syntax"></a>構文

```
/Ge
```

## <a name="remarks"></a>Remarks

このメカニズムは、スタック プローブの機能を書き換える場合に便利です。 使用することをお勧め[/Gh (有効にする _penter フック関数)](gh-enable-penter-hook-function.md)スタック プローブの代わりにします。

[/Gs (コントロール スタック チェック呼び出し)](gs-control-stack-checking-calls.md)同じ効果があります。

**/Ge**は非推奨とされます。 以降、Visual Studio 2005 では、コンパイラを自動的に生成スタックをチェックします。 非推奨のコンパイラ オプションの一覧は、**非推奨とされた削除済みのコンパイラ オプション**で[Compiler Options Listed by Category](compiler-options-listed-by-category.md)を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
