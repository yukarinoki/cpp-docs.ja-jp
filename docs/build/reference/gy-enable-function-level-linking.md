---
description: 詳細について:/Gy (Function-Level リンクの有効化)
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
ms.openlocfilehash: 3c4136b25001f7f6d6729b9c6089995d1bcd71bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200131"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (関数レベルのリンクの有効化)

コンパイラが個々の関数をパッケージ関数 (COMDAT) の形式でパッケージ化できるようになります。

## <a name="syntax"></a>構文

```
/Gy[-]
```

## <a name="remarks"></a>解説

リンカーでは、DLL または .exe ファイル内の個々の関数を除外または順序付けするために、関数を Comdat として個別にパッケージ化する必要があります。

リンカーオプション [/opt (最適化)](opt-optimizations.md) を使用して、参照されていないパッケージ関数を .exe ファイルから除外することができます。

リンカーオプション [/order (順に Put 関数)](order-put-functions-in-order.md) を使用して、パッケージ化された関数を指定した順序で .exe ファイルに含めることができます。

インライン関数は、呼び出しとしてインスタンス化される場合は常にパッケージ化されます (インライン展開が無効になっている場合や、関数のアドレスを取得した場合など)。 また、クラス宣言で定義されている C++ メンバー関数は自動的にパッケージ化されます。その他の関数はではなく、パッケージ化された関数としてコンパイルするには、このオプションを選択する必要があります。

> [!NOTE]
> [/Zi](z7-zi-zi-debug-information-format.md)オプションは、エディットコンティニュに使用され、 **/gy** オプションを自動的に設定します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **コード生成** ] プロパティページをクリックします。

1. [ **Function-Level リンクを有効にする** ] プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
