---
title: Win32 アプリケーション ウィザード |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.appwiz.win32.overview
dev_langs:
- C++
helpviewer_keywords:
- Win32 Application Wizard
- Win32 Project Wizard
ms.assetid: 5d7b3a5e-8461-479a-969a-67b7883725b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 18885e36b5f598a8b1dd6128c29a9e520128dcb2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33891426"
---
# <a name="win32-application-wizard"></a>Win32 アプリケーション ウィザード
Visual C++ の Win32 アプリケーション ウィザードを使用すると、以下の表の見出しに示す 4 種類のプロジェクトを作成できます。 いずれの場合でも、開くプロジェクトの種類に応じて追加のオプションを指定できます。 次の表では、使用できるオプションをアプリケーション タイプ別に示します。  
  
|アプリケーションの種類|コンソール アプリケーション|実行可能 (Windows) アプリケーション|ダイナミック リンク ライブラリ|スタティック ライブラリ|  
|---------------------|-------------------------|----------------------------------------|---------------------------|--------------------|  
|**空のプロジェクト**|[はい]|はい|はい|×|  
|**シンボルのエクスポート**|×|Ｘ|はい|×|  
|**プリコンパイル済みヘッダー**|×|Ｘ|Ｘ|[はい]|  
|**ATL サポート**|[はい]|いいえ|Ｘ|×|  
|**MFC サポート**|[はい]|いいえ|Ｘ|[はい]|  
  
## <a name="overview"></a>概要  
 このウィザード ページでは、作成する Win32 アプリケーションの現在のプロジェクト設定が示されます。 既定では、以下のオプションが設定されています。  
  
-   プロジェクトが Windows アプリケーションである。  
  
-   プロジェクトが空ではない。  
  
-   プロジェクトにエクスポート シンボルが含まれない。  
  
-   プロジェクトでプリコンパイル済みヘッダー ファイルを使用しない。このオプションを使用できるのはスタティック ライブラリ プロジェクトだけです。  
  
-   プロジェクトに MFC または ATL のサポートが含まれない。  
  
 これらの既定値を変更するには、ウィザードの左の列にある [[アプリケーションの設定]](../windows/application-settings-win-32-project-wizard.md) タブを使用します。  
  
 Windows デスクトップ アプリケーションを作成したら、 [汎用](../ide/generic-cpp-class-wizard.md) コード ウィザードを使用して汎用 C++ クラスを追加できます。 HTML ファイル、ヘッダー ファイル、リソース、テキスト ファイルなど、その他の項目も追加できます。  
  
> [!NOTE]
>  ATL クラスは追加できません。また、MFC クラスを追加できるのは、MFC をサポートするタイプの Windows デスクトップ アプリケーションだけです。上の表を参照してください。  
  
 ウィザードでプロジェクト用に作成されるファイルは、 **ソリューション エクスプローラー**で表示できます。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類の詳細については、「 [Visual C++ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [空の Windows デスクトップ アプリケーションを作成します。](../windows/creating-an-empty-windows-desktop-application.md)   
 [Visual C++ プロジェクトの種類](../ide/visual-cpp-project-types.md)