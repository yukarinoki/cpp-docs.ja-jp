---
title: '[Midl] プロパティ ページ: 高度な |Microsoft ドキュメント'
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
ms.openlocfilehash: 5f87518c23848cea91a3e3c48361aa0a63fa88a2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="midl-property-pages-advanced"></a>[詳細] ([MIDL] プロパティ ページ)
**[詳細設定]** プロパティ ページで、 **MIDL**フォルダーは、次の MIDL コンパイラ オプションを指定します。  
  
-   エラー チェックを有効にする ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   割り当ての確認 ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   範囲のチェック ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   Enum の範囲のチェック ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   参照ポインターをチェック ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   スタブ データを確認する ([/error](http://msdn.microsoft.com/library/windows/desktop/aa367324))  
  
-   パラメーターを検証する ([/robust](http://msdn.microsoft.com/library/windows/desktop/aa367363)) *  
  
-   構造体メンバーの配置 ([/Zp](http://msdn.microsoft.com/library/windows/desktop/aa367388))  
  
-   出力にリダイレクト ([/o](http://msdn.microsoft.com/library/windows/desktop/aa367351))  
  
-   C プリプロセス オプション ([/cpp_opt](http://msdn.microsoft.com/library/windows/desktop/aa367318))  
  
-   プリプロセッサ定義の解除 ([/U](http://msdn.microsoft.com/library/windows/desktop/aa367373))  
  
 \* /Windows 2000 またはそれ以降のコンピューターを構築するときに使用するためだけ堅牢なは。 ATL プロジェクトをビルドして使用するかどうかは/robust, dlldatax.c ファイルのこの行を変更します。  
  
```  
#define _WIN32_WINNT 0x0400   //for Windows NT 4.0 or Windows 95 with DCOM  
to   
#define _WIN32_WINNT 0x0500   //for Windows NT 4.0 or Windows 95 with DCOM  
```  
  
 アクセスする方法については、 **[詳細設定]** プロパティ ページで、 **MIDL**フォルダーを参照してください[のプロジェクト プロパティの操作](../ide/working-with-project-properties.md)です。  
  
 C++ プロジェクト用の MIDL オプションにアクセスする方法については、次を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool>です。  
  
## <a name="see-also"></a>関連項目  
 [[MIDL] プロパティ ページ](../ide/midl-property-pages.md)