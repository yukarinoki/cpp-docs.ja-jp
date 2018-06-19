---
title: ATL ダイアログ ボックスを追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0883b87ce991b08a96b1d10b4acedf8562022a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361526"
---
# <a name="adding-an-atl-dialog-box"></a>ATL ダイアログ ボックスを追加します。
ATL ダイアログをプロジェクトに追加するには、プロジェクトは ATL プロジェクト、または ATL のサポートを含む MFC プロジェクトをする必要があります。 使用することができます、 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)ATL アプリケーションを作成するか、 [ATL オブジェクトを MFC アプリケーションに追加](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)MFC アプリケーションに対する ATL のサポートを実装します。  
  
 ATL ダイアログ ウィザード実装から派生したダイアログ ボックスを既定では、 [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md)です。 このクラスには、ActiveX や Windows のコントロールをホストするためのサポートが含まれています。 ウィザードは、コードを生成した後に ActiveX コントロール サポートのオーバーヘッドをしない場合は、すべてのインスタンスを置き換える`CAxDialogImpl`いずれかで[CSimpleDialog](../../atl/reference/csimpledialog-class.md)または[CDialogImpl](../../atl/reference/cdialogimpl-class.md)基底クラスとして.  
  
> [!NOTE]
>  `CSimpleDialog` Windows コモン コントロールのみをサポートするモーダル ダイアログ ボックスのみを作成します。 `CDialogImpl` いずれかのモーダルまたはモードレスのダイアログ ボックスを作成します。  
  
### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>ATL ダイアログ リソースをプロジェクトに追加するには  
  
1.  ATL プロジェクトを使用して、作成、 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)です。  
  
2.  [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)プロジェクト名を右クリックし、クリックして、**追加**ショートカット メニューからです。 をクリックして**クラスを追加**です。  
  
3.  [テンプレート] ペインで、[クラスの追加](../../ide/add-class-dialog-box.md)ダイアログ ボックスで、をクリックして**ATL ダイアログ**です。 をクリックして**開く**を表示する、 [ATL ダイアログ ウィザード](../../atl/reference/atl-dialog-wizard.md)です。  
  
 詳細については、次を参照してください。 [ ダイアログ ボックスを実装する](../../atl/implementing-a-dialog-box.md)です。  
  
## <a name="see-also"></a>関連項目  
 [クラスの追加](../../ide/adding-a-class-visual-cpp.md)   
 [ウィンドウ クラス](../../atl/atl-window-classes.md)   
 [メッセージ マップ](../../atl/message-maps-atl.md)

