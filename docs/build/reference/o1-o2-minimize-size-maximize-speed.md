---
title: /O1、/O2 (プログラム サイズ、実行速度)
ms.date: 09/25/2017
f1_keywords:
- /o2
- /o1
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
ms.openlocfilehash: 3daf5dd5f9912194fd5d8aaeb4c7a312be142b69
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825347"
---
# <a name="o1-o2-minimize-size-maximize-speed"></a>/O1、/O2 (プログラム サイズ、実行速度)

生成されるコードのサイズと速度に影響する、定義済みのオプションのセットを選択します。

## <a name="syntax"></a>構文

> O1
> /O2

## <a name="remarks"></a>解説

**/O1**および **/O2**コンパイラオプションを使うと、いくつかの特定の最適化オプションを一度にすばやく設定できます。 **/O1**オプションは、ほとんどのケースで最小のコードを作成する個々の最適化オプションを設定します。 **/O2**オプションは、ほとんどのケースで最速のコードを作成するオプションを設定します。 **/O2**オプションは、リリースビルドの既定値です。 次の表は、 **/O1**と **/O2**によって設定される特定のオプションを示しています。

|オプション|相当する構文|
|------------|-------------------|
|**/O1** (サイズの最小化)|[/Og](og-global-optimizations.md) [/Os](os-ot-favor-small-code-favor-fast-code.md) [/Oy](oy-frame-pointer-omission.md) [/ob2](ob-inline-function-expansion.md) [/gf](gf-eliminate-duplicate-strings.md) [/gy](gy-enable-function-level-linking.md)|
|**/O2** (速度を最大にする)|[/Og](og-global-optimizations.md) [/Oi](oi-generate-intrinsic-functions.md) [/Ot](os-ot-favor-small-code-favor-fast-code.md) [/oy](oy-frame-pointer-omission.md) [/ob2](ob-inline-function-expansion.md) [/gf](gf-eliminate-duplicate-strings.md) [/gy](gy-enable-function-level-linking.md)|

**/O1**と **/O2**は相互に排他的です。

> [!NOTE]
> **x86 固有**\
> これらのオプションは、フレームポインターの省略 ([/oy](oy-frame-pointer-omission.md)) オプションを使用することを意味します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] で、[ **C/c + +** ] を開き、[**最適化**] プロパティページをクリックします。

1. **最適化**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A> 」を参照してください。

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[/EH (例外処理モデル)](eh-exception-handling-model.md)
