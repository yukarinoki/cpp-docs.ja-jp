---
title: /constexpr (constexpr の評価の制御)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: 7b3ae1cd732fe1ec234e2734ea4c6fa86db9d5af
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223864"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (constexpr の評価の制御)

**/Constexpr**コンパイラオプションを使用して、 **`constexpr`** コンパイル時に評価用のパラメーターを制御します。

## <a name="syntax"></a>構文

> **/constexpr: 深さ**<em>N</em>\
> **/constexpr: バックトレース**<em>N</em>\
> **/constexpr: 手順**<em>N</em>

## <a name="arguments"></a>引数

**深さ**<em>n</em>再帰関数呼び出しの深さ **`constexpr`** を*n*レベルに制限します。 既定値は 512 です。

**バックトレース**<em>n</em>では、診断で最大*n 個* **`constexpr`** の評価が表示されます。 既定値は 10 です。

**手順**<em>n</em> **`constexpr`** *n*ステップ後の評価を終了します。 既定値は10万です。

## <a name="remarks"></a>解説

**/Constexpr**コンパイラオプションは、式のコンパイル時の評価を制御し **`constexpr`** ます。 評価手順、再帰レベル、およびバックトレースの深さは、コンパイラによる評価に時間がかかりすぎるのを防ぐために制御され **`constexpr`** ます。 言語要素の詳細につい **`constexpr`** ては、「 [Constexpr (C++)](../../cpp/constexpr-cpp.md)」を参照してください。

**/Constexpr**オプションは、Visual Studio 2015 以降で使用できます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの [**プロパティページ**] ダイアログボックスを開きます。

2. [**構成プロパティ**] で、[ **C/c + +** ] フォルダーを展開し、[**コマンドライン**] プロパティページをクリックします。

3. [**追加オプション**] ボックスに、任意の **/constexpr**コンパイラオプションを入力します。 **[OK]** または [**適用**] を選択して、変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
