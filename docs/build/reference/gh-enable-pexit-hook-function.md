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
ms.openlocfilehash: 5382ba90f490aaa12e9e55767fdf15170a69ced5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749228"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH (_pexit フック関数の有効化)

すべてのメソッド`_pexit`または関数の末尾で関数を呼び出します。

## <a name="syntax"></a>構文

```
/GH
```

## <a name="remarks"></a>解説

この`_pexit`関数はライブラリの一部ではなく、 の定義を指定する必要があります`_pexit`。

明示的に呼び出`_pexit`す場合を除き、プロトタイプを提供する必要はありません。 関数は、次のプロトタイプを持っているかのように見える必要があり、エントリ上のすべてのレジスタの内容をプッシュし、終了時に変更されていない内容をポップする必要があります。

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit`は に`_penter`似ています。関数の記述方法の例については[、/Gh (_penterフック関数を有効](gh-enable-penter-hook-function.md)にする)を参照してください。 `_pexit`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション] **** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
