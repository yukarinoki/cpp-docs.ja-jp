---
title: -Gy (関数レベルのリンクを有効にする) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFunctionLevelLinking
- /gy
- VC.Project.VCCLWCECompilerTool.EnableFunctionLevelLinking
dev_langs:
- C++
helpviewer_keywords:
- enable function-level linking compiler option [C++]
- COMDAT function
- Gy compiler option [C++]
- -Gy compiler option [C++]
- /Gy compiler option [C++]
- packaged functions
ms.assetid: 0d3cf14c-ed7d-4ad3-b4b6-104e56f61046
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09faa1a1d2b6743b7fce31af32ba4fe1572b592e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705004"
---
# <a name="gy-enable-function-level-linking"></a>/Gy (関数レベルのリンクの有効化)

コンパイラが個々の関数をパッケージ関数 (COMDAT) の形式でパッケージ化できるようになります。

## <a name="syntax"></a>構文

```
/Gy[-]
```

## <a name="remarks"></a>Remarks

リンカーは、関数が、除外したり、DLL、または .exe ファイルで個別の関数の順序の Comdat として個別にパッケージ化することが必要です。

リンカー オプションを使用する[/OPT (最適化)](../../build/reference/opt-optimizations.md) .exe ファイルから参照されていないパッケージ化された関数を除外します。

リンカー オプションを使用する[/ORDER (順序で配置関数)](../../build/reference/order-put-functions-in-order.md)に .exe ファイルで指定した順序でパッケージ化された関数を含めます。

インライン関数は、インスタンスが呼び出される場合に常にパッケージ化されます (が発生する、たとえば、インライン化がオフまたは関数のアドレスを取得する)。 さらに、クラス宣言で定義されている C++ メンバー関数は自動的にパッケージ化されます。その他の関数は使用されませんし、それらをパッケージ化された関数としてコンパイルする必要はこのオプションを選択します。

> [!NOTE]
>  [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) 、エディット コンティニュを使用するオプションが自動的に設定、 **/Gy**オプション。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**コード生成**プロパティ ページ。

1. 変更、**関数レベルのリンクを有効にする**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFunctionLevelLinking%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)