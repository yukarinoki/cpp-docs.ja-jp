---
title: '[全般] ([MIDL] プロパティ ページ) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.OVERWRITEStandardIncludePath
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: 0692484c-a7e6-4270-8df7-981589368399
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32e1c743844d252b391a4a747d803ba0e8c81c54
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431425"
---
# <a name="midl-property-pages-general"></a>[全般] ([MIDL] プロパティ ページ)

**MIDL** フォルダーの **[全般]** プロパティ ページでは、次の MIDL コンパイラ オプションを指定します。

- プリプロセッサの定義 [(/D](https://msdn.microsoft.com/library/windows/desktop/aa367321))

- 追加のインクルード ディレクトリ ([/I](https://msdn.microsoft.com/library/windows/desktop/aa367328))

- 標準インクルード パスの無視 ([/no_def_idir](https://msdn.microsoft.com/library/windows/desktop/aa367347))

- MkTypLib 互換 ([/mktyplib203](https://msdn.microsoft.com/library/windows/desktop/aa367332))

- 警告レベル ([/W](https://msdn.microsoft.com/library/windows/desktop/aa367383))

- エラーとして警告 ([/WX](https://msdn.microsoft.com/library/windows/desktop/aa367387))

- 著作権情報の非表示 ([/nologo](https://msdn.microsoft.com/library/windows/desktop/aa367341))

- MIDL Char 型 ([/char](https://msdn.microsoft.com/library/windows/desktop/aa367314))

- 対象の環境 ([/env](https://msdn.microsoft.com/library/windows/desktop/aa367323))

- スタブレス プロキシの生成 ([/Oicf](https://msdn.microsoft.com/library/windows/desktop/aa367352))

**MIDL** フォルダーの **[全般]** プロパティ ページにアクセスする方法については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。

C++ プロジェクト用の MIDL オプションにプログラムでアクセスする方法の詳細については、<xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> オブジェクトに関するページを参照してください。

## <a name="see-also"></a>参照

[[MIDL] プロパティ ページ](../ide/midl-property-pages.md)