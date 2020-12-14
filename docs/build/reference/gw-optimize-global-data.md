---
description: 詳細情報:/Gw (グローバルデータの最適化)
title: /Gw (グローバル データの最適化)
ms.date: 11/04/2016
f1_keywords:
- /Gw
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
ms.openlocfilehash: 2f9a6b9452f09473e650a5453ad2600cc73f0c00
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200144"
---
# <a name="gw-optimize-global-data"></a>/Gw (グローバル データの最適化)

グローバル データを最適化のために COMDAT セクションにパッケージ化します。

## <a name="syntax"></a>構文

```
/Gw[-]
```

## <a name="remarks"></a>解説

**/Gw** オプションを指定すると、コンパイラは個々の COMDAT セクションにグローバルデータをパッケージ化します。 既定では、 **/Gw** はオフであり、明示的に有効にする必要があります。 明示的に無効にするには、 **/Gw-** を使用します。 **/Gw** と [/gl](gl-whole-program-optimization.md)の両方が有効になっている場合、リンカーはプログラム全体の最適化を使用して複数のオブジェクトファイル間で COMDAT セクションを比較し、参照されていないグローバルデータを除外するか、同一の読み取り専用グローバルデータをマージします。 その結果、生成されるバイナリ実行可能ファイルのサイズが大幅に小さくなることがあります。

を個別にコンパイルしてリンクする場合は、 [/opt: REF](opt-optimizations.md) リンカーオプションを使用して、 **/Gw** オプションを使用してコンパイルされたオブジェクトファイル内の参照されていないグローバルデータを実行可能ファイルから除外できます。

また、 [/opt: ICF](opt-optimizations.md) オプションと [/ltcg](ltcg-link-time-code-generation.md) リンカーオプションを一緒に使用して、 **/Gw** オプションを使用してコンパイルされた複数のオブジェクトファイル間で、同じ読み取り専用のグローバルデータを実行可能ファイルにマージすることもできます。

詳細については、C++ チームブログの「 [/Gw コンパイラスイッチの概要](https://devblogs.microsoft.com/cppblog/introducing-gw-compiler-switch/) 」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [ **C/c + +** ] フォルダーを選択します。

1. [ **コマンドライン** ] プロパティページを選択します。

1. [ **追加オプション** ] プロパティを変更して **/Gw** を含め、[ **OK]** を選択します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
