---
title: CWinApp および MFC アプリケーション ウィザード |Microsoft ドキュメント
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
ms.openlocfilehash: d40f314c7717d2e69b2b4802bf9c2c5468511db5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341262"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp および MFC アプリケーション ウィザード
MFC アプリケーション ウィザードでは、アプリケーション クラスから派生した宣言、スケルトン アプリケーションの作成時に[CWinApp](../mfc/reference/cwinapp-class.md)です。 MFC アプリケーション ウィザードでは、次の項目を含んでいる実装ファイルも生成します。  
  
-   アプリケーションのクラスのメッセージ マップです。  
  
-   空のクラスのコンス トラクターです。  
  
-   クラスのオブジェクトのみを宣言する変数です。  
  
-   標準的な実装、`InitInstance`メンバー関数。  
  
 アプリケーションのクラスは、プロジェクトのヘッダーとメインのソース ファイルに配置されます。 クラスと作成されるファイルの名前は、MFC アプリケーション ウィザードで指定されたプロジェクト名に基づきます。 これらのクラスのコードを表示する最も簡単な方法は、[クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)です。  
  
 標準の実装および提供のメッセージ マップが多くの目的で、適切なものが、必要に応じて変更できます。 これらの実装の中で最も興味深いは、`InitInstance`メンバー関数。 通常、コードのスケルトンの実装を追加が`InitInstance`です。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)   
 [オーバーライド可能な CWinApp のメンバー関数します。](../mfc/overridable-cwinapp-member-functions.md)   
 [CWinApp のその他のサービス](../mfc/special-cwinapp-services.md)

