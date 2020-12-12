---
description: 詳細については、次を参照してください:/Qimprecise_fwaits (Try ブロック内の fwaits を削除)
title: /Qimprecise_fwaits (try ブロック内部の fwaits を削除する)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 5f3d96656d062a7e5b0c4ad78ba7cd536069e013
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225623"
---
# <a name="qimprecise_fwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (try ブロック内部の fwaits を削除する)

`fwait` **`try`** [/Fp: except](fp-specify-floating-point-behavior.md)コンパイラオプションを使用すると、ブロック内部のコマンドが削除されます。

## <a name="syntax"></a>構文

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>解説

このオプションは、 **/fp: except** が指定されていない場合は効果がありません。 **/Fp: except** オプションを指定すると、コンパイラは `fwait` ブロック内のコード行ごとにコマンドを挿入し **`try`** ます。 このようにして、コンパイラは例外を生成する特定のコード行を識別できます。 **/Qimprecise_fwaits** 内部 `fwait` 命令を削除し、ブロックを囲む待機だけを残し **`try`** ます。 これにより、パフォーマンスが向上しますが、コンパイラは、 **`try`** どのブロックによって例外が発生するかを特定することしかできません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. [追加のオプション]  ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低レベルの操作)](q-options-low-level-operations.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
