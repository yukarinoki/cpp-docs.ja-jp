---
title: CWinApp および MFC アプリケーション ウィザード |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 702c20fc9f303670d2add4ebf840785acff7750d
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026486"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp および MFC アプリケーション ウィザード
MFC アプリケーション ウィザードでは、アプリケーションのクラスから派生した宣言、スケルトン アプリケーションの作成時に[CWinApp](../mfc/reference/cwinapp-class.md)します。 MFC アプリケーション ウィザードでは、次の項目を格納する実装ファイルも生成されます。  
  
-   アプリケーションのクラスのメッセージ マップです。  
  
-   空のクラスのコンス トラクターです。  
  
-   クラスのオブジェクトのみを宣言する変数。  
  
-   標準的な実装、`InitInstance`メンバー関数。  
  
 アプリケーションのクラスは、プロジェクトのヘッダーとメイン ソース ファイルに配置されます。 クラスと作成されるファイルの名前は、MFC アプリケーション ウィザードで、指定したプロジェクトの名前に基づきます。 これらのクラスのコードを表示する最も簡単な方法は使用[クラス ビュー](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925)します。  
  
 標準的な実装とメッセージ マップの指定は多くの目的で、適切であるが、必要に応じて変更することができます。 これらの実装の中で最も興味深いは、`InitInstance`メンバー関数。 スケルトンの実装にコードを追加する通常、`InitInstance`します。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)   
 [オーバーライド可能な CWinApp のメンバー関数します。](../mfc/overridable-cwinapp-member-functions.md)   
 [CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)

