---
title: /Gy (関数レベルのリンクの有効化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
ms.openlocfilehash: 8724ae4d018948c0f6aa9456f229db96878d7bf2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328273"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (関数レベルのリンクの有効化)

コンパイラが個々の関数をパッケージ関数 (COMDAT) の形式でパッケージ化できるようになります。

## <a name="syntax"></a>構文

```
/Gy[-]
```

## <a name="remarks"></a>解説

リンカーでは、DLL または .exe ファイル内の個々の関数を除外または順序付けするために、関数を COMDAS として個別にパッケージ化する必要があります。

リンカー オプション[/OPT (最適化) を](opt-optimizations.md)使用して、参照されていないパッケージ化された関数を .exe ファイルから除外できます。

リンカー オプション[/ORDER (関数を順序どおりに入れる) を](order-put-functions-in-order.md)使用すると、パッケージ化された関数を指定された順序で .exe ファイルに含めることができます。

インライン関数は、呼び出しとしてインスタンス化される場合 (インライン化がオフの場合や関数アドレスを取る場合など) に常にパッケージ化されます。 さらに、クラス宣言で定義された C++ メンバー関数は自動的にパッケージ化されます。他の関数はそうではないため、パッケージ化された関数としてコンパイルするにはこのオプションを選択する必要があります。

> [!NOTE]
> エディット コンティニュに使用される[/ZI](z7-zi-zi-debug-information-format.md)オプションは **、/Gy**オプションを自動的に設定します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [**コード生成**] プロパティ ページをクリックします。

1. [**機能レベルのリンクを有効にする]** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>」を参照してください。

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
