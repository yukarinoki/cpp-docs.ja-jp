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
ms.openlocfilehash: 4d3f33a64dcebfc40778f81354cb5067a5239ace
ms.sourcegitcommit: 6b749db14b4cf3a2b8d581fda6fdd8cb98bc3207
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "82825592"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (constexpr の評価の制御)

**/Constexpr**コンパイラオプションを使用して、コンパイル時に**constexpr**の評価のパラメーターを制御します。

## <a name="syntax"></a>構文

> **/constexpr: 深さ**<em>N</em>\
> **/constexpr: バックトレース**<em>N</em>\
> **/constexpr: 手順**<em>N</em>

## <a name="arguments"></a>引数

**深さ**<em>n</em>再帰的な**constexpr**関数呼び出しの深さを*n*レベルに制限します。 既定値は 512 です。

**バックトレース**<em>N</em>は、診断で最大*N 個*の**constexpr**評価を示します。 既定値は 10 です。

**手順**<em>n</em> *n*ステップ後に**constexpr**評価を終了します。 既定値は10万です。

## <a name="remarks"></a>解説

**/Constexpr**コンパイラオプションは、 **constexpr**式のコンパイル時の評価を制御します。 評価手順、再帰レベル、およびバックトレースの深さは、コンパイラが**constexpr**の評価に過度に時間をかけないようにするために制御されます。 **Constexpr**言語要素の詳細については、「 [constexpr (C++)](../../cpp/constexpr-cpp.md)」を参照してください。

**/Constexpr**オプションは、Visual Studio 2015 以降で使用できます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの [**プロパティページ**] ダイアログボックスを開きます。

2. [**構成プロパティ**] で、[ **C/c + +** ] フォルダーを展開し、[**コマンドライン**] プロパティページをクリックします。

3. [**追加オプション**] ボックスに、任意の **/constexpr**コンパイラオプションを入力します。 **[OK]** または [**適用**] を選択して、変更を保存します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「 <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> 」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
