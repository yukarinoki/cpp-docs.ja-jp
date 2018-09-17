---
title: -showincludes (インクルード ファイル一覧) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs:
- C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51305212f97482c6963ee2ba0d272c5c4692416e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709394"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (インクルード ファイル一覧)

コンパイラでインクルード ファイルのリストを出力します。 入れ子になった含めるファイルも表示されている (に含まれるファイルを含むファイルから)。

## <a name="syntax"></a>構文

```
/showIncludes
```

## <a name="remarks"></a>Remarks

インクルード ファイルがコンパイル時に発生したときに、メッセージは、出力をなどです。

```
Note: including file: d:\MyDir\include\stdio.h
```

入れ子になった含めるなどのファイルは、インデントは、入れ子のレベルごとに 1 つの領域で示されます。

```
Note: including file: d:\temp\1.h
Note: including file:  d:\temp\2.h
```

この場合、`2.h`内から含まれていました`1.h`、そのため、インデントします。

**/ShowIncludes**オプションを生成する`stderr`ではなく、`stdout`します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**詳細**プロパティ ページ。

1. 変更、 **インクルード ファイルの**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)