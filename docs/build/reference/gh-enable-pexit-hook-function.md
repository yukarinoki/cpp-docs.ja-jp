---
title: /GH (_pexit フック関数の有効化)
description: ローカル _pexit のフック関数を設定する/GH コンパイラオプションについて説明します。
ms.date: 07/06/2020
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: b8fc355503055af8b928874ced39cb8224901d3e
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: ja-JP
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058608"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH (_pexit フック関数の有効化)

は、 `_pexit` すべてのメソッドまたは関数の最後に関数を呼び出します。

## <a name="syntax"></a>構文

> **`/GH`**

## <a name="remarks"></a>Remarks

`_pexit`関数はどのライブラリの一部でもありません。 の定義を指定する必要が `_pexit` あります。

明示的にを呼び出す予定がない限り `_pexit` 、プロトタイプを提供する必要はありません。 関数は、入力時にすべてのレジスタの内容をプッシュし、終了時に変更されていないコンテンツをポップする必要があります。 次のプロトタイプがあるかのように表示される必要があります。

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

この宣言は、64ビットのプロジェクトでは使用できません。

`_pexit`はに似 `_penter` ています。関数を記述する方法の例については、「 [ `/Gh` (_Penter のフック関数を有効にする)](gh-enable-penter-hook-function.md) 」を参照してください `_penter` 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**  >  ] [**C/c + +**  >  **] [コマンドライン**] プロパティページを開きます。

1. [**追加オプション**] ボックスにコンパイラオプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[`/Gh`(_Penter フック関数を有効にする)](gh-enable-penter-hook-function.md)
