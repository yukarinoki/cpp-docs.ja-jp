---
description: 詳細については、次を参照してください:/Ge (スタックプローブの有効化)
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
ms.openlocfilehash: db996deb1c5b964661e5465fe72cfb0fab93df56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192019"
---
# <a name="ge-enable-stack-probes"></a>/Ge (スタック プローブの有効化)

ローカル変数のストレージを必要とするすべての関数呼び出しに対して、スタックプローブをアクティブにします。

## <a name="syntax"></a>構文

```
/Ge
```

## <a name="remarks"></a>解説

このメカニズムは、スタックプローブの機能を書き換える場合に便利です。 スタックプローブを書き換えるのではなく、 [/Gh (Enable _Penter フック関数)](gh-enable-penter-hook-function.md) を使用することをお勧めします。

[/Gs (スタックチェック呼び出しの制御)](gs-control-stack-checking-calls.md) は同じ効果を持ちます。

**/Ge** は非推奨とされます。Visual Studio 2005 以降では、コンパイラによって自動的にスタックチェックが生成されます。 非推奨のコンパイラオプションの一覧については、「[カテゴリ別に一覧表示さ](compiler-options-listed-by-category.md)れたコンパイラオプションの **非推奨のコンパイラオプション**」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
