---
title: /O1、/O2 (プログラム サイズ、実行速度)
description: MSVC コンパイラオプション/O1 と/O2 は、最小サイズまたは最大速度のすべての最適化を指定します。
ms.date: 07/08/2020
f1_keywords:
- /O2
- /O1
helpviewer_keywords:
- maximize speed compiler option [C++]
- minimize size compiler option [C++]
- -O2 compiler option [C++]
- fast code
- small code
- O2 compiler option [C++]
- /O2 compiler option [C++]
- -O1 compiler option [C++]
- O1 compiler option [C++]
- /O1 compiler option [C++]
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
ms.openlocfilehash: c1eda8395e604468cbb23572ec930d6171984fe4
ms.sourcegitcommit: 80c8a512b361bd84e38958beb1a1bf6db7434021
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2020
ms.locfileid: "86180904"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>`/O1`、 `/O2` (サイズを最小化し、速度を最大にする)

生成されるコードのサイズと速度に影響する、定義済みのオプションのセットを選択します。

## <a name="syntax"></a>構文

> **`/O1`**\
> **`/O2`**

## <a name="remarks"></a>解説

**`/O1`** と **`/O2`** コンパイラオプションを使うと、いくつかの特定の最適化オプションを一度にすばやく設定できます。 この **`/O1`** オプションは、ほとんどのケースで最小のコードを作成する個々の最適化オプションを設定します。 オプションは、 **`/O2`** ほとんどのケースで最速のコードを作成するオプションを設定します。 オプションは、 **`/O2`** リリースビルドの既定値です。 次の表は、およびによって設定される特定のオプションを示してい **`/O1`** **`/O2`** ます。

| オプション | 相当する構文 |
|--|--|
| **`/O1`**(サイズの最小化) | [`/Og`](og-global-optimizations.md) [`/Os`](os-ot-favor-small-code-favor-fast-code.md) [`/Oy`](oy-frame-pointer-omission.md) [`/Ob2`](ob-inline-function-expansion.md) [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) |
| **`/O2`**(速度を最大にする) | [`/Og`](og-global-optimizations.md) [`/Oi`](oi-generate-intrinsic-functions.md) [`/Ot`](os-ot-favor-small-code-favor-fast-code.md) [`/Oy`](oy-frame-pointer-omission.md) [`/Ob2`](ob-inline-function-expansion.md) [`/GF`](gf-eliminate-duplicate-strings.md) [`/Gy`](gy-enable-function-level-linking.md) |

**`/O1`** と **`/O2`** は相互に排他的です。

> [!NOTE]
> **x86 固有**\
> これらのオプションは、フレームポインターの省略 () オプションを使用することを意味し [`/Oy`](oy-frame-pointer-omission.md) ます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **最適化**] プロパティページを選択します。

1. **最適化**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>

## <a name="see-also"></a>関連項目

[`/O`オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[`/EH`(例外処理モデル)](eh-exception-handling-model.md)
