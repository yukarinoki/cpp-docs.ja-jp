---
title: /GH (_pexit フック関数の有効化)
ms.date: 11/04/2016
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: 21649838ba81f3affdda3f3833de23e4d9e33746
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422530"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (_pexit フック関数の有効化)

呼び出し、`_pexit`関数のすべてのメソッドまたは関数の末尾。

## <a name="syntax"></a>構文

```
/GH
```

## <a name="remarks"></a>Remarks

`_pexit`関数は、任意のライブラリの一部ではないの定義を提供するかどうかは`_pexit`します。

明示的に呼び出す予定がない限り`_pexit`プロトタイプを提供する必要はありません。 関数は、次のプロトタイプがあった場合とおよびエントリのすべてのレジスタのコンテンツをプッシュし、終了時に変更されていないコンテンツを表示にする必要がありますに記述する必要があります。

```
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit` ような`_penter`; を参照してください[/Gh (有効にする _penter フック関数)](../../build/reference/gh-enable-penter-hook-function.md)を記述する方法の例については、`_pexit`関数。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)
