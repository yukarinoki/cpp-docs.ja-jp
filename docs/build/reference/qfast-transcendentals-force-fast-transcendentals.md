---
description: 詳細については、次を参照してください:/Qfast_transcendentals (Force Fast 超越関数)
title: /Qfast_transcendentals (超越関数高速化の強制)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 7701925aa7df33107b0829ade1c0c711eda14c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225662"
---
# <a name="qfast_transcendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (超越関数高速化の強制)

超越 functions のインラインコードを生成します。

## <a name="syntax"></a>構文

```
/Qfast_transcendentals
```

## <a name="remarks"></a>解説

このコンパイラオプションを使用すると、超越関数がインラインコードに変換され、実行速度が向上します。 このオプションは、 **/fp: except** または **/fp: 精密** と組み合わせた場合にのみ効果があります。 超越 functions のインラインコードの生成は、既に **/fp: fast** での既定の動作です。

このオプションは、 **/fp: strict** と互換性がありません。 浮動小数点コンパイラオプションの詳細については、「 [/fp (Floating-Point 動作の指定)](fp-specify-floating-point-behavior.md) 」を参照してください。

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
