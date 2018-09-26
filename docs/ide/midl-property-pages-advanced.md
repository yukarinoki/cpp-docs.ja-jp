---
title: '[詳細] ([MIDL] プロパティ ページ) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ValidateParameters
dev_langs:
- C++
helpviewer_keywords:
- MIDL, property pages
ms.assetid: d1c92e01-f403-4ed6-ab45-4043a3c9c6bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11c7d4b437e77e5acfe363fd3b4125477eceb0f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46394968"
---
# <a name="midl-property-pages-advanced"></a>[詳細] ([MIDL] プロパティ ページ)

**MIDL** フォルダーの **[詳細]** プロパティ ページでは、次の MIDL コンパイラ オプションを指定します。

- エラー チェックを有効にする ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 割り当てのチェック ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 範囲のチェック ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 列挙型の範囲のチェック ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- 参照ポインターのチェック ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- スタブ データのチェック ([/error](https://msdn.microsoft.com/library/windows/desktop/aa367324))

- パラメーターの確認 ([/robust](https://msdn.microsoft.com/library/windows/desktop/aa367363))\*

- 構造体メンバーの配置 ([/Zp](https://msdn.microsoft.com/library/windows/desktop/aa367388))

- 出力先の変更 ([/o](https://msdn.microsoft.com/library/windows/desktop/aa367351))

- C プリプロセス オプション ([/cpp_opt](https://msdn.microsoft.com/library/windows/desktop/aa367318))

- 指定したプリプロセッサ定義の無効化 ([/U](https://msdn.microsoft.com/library/windows/desktop/aa367373))

\* /robust は、Windows 2000 以降のコンピューター向けとしてビルドするときにのみ使用されます。 ATL プロジェクトをビルドするとき、/robust を使用する場合、dlldatax.c ファイルでこの行を変更します。

```
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM
to
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM
```

**MIDL** フォルダーの **[詳細]** プロパティ ページにアクセスする方法については、「[プロジェクトのプロパティの操作](../ide/working-with-project-properties.md)」を参照してください。

C++ プロジェクト用の MIDL オプションにプログラムでアクセスする方法の詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>」を参照してください。

## <a name="see-also"></a>参照

[[MIDL] プロパティ ページ](../ide/midl-property-pages.md)