---
title: CMFCWindowsManagerDialog クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog
- AFXWINDOWSMANAGERDIALOG/CMFCWindowsManagerDialog::CMFCWindowsManagerDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCWindowsManagerDialog [MFC], CMFCWindowsManagerDialog
ms.assetid: 35b4b0db-33c4-4b22-94d8-5e3396341340
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6900164b3ce89031d0db7630c026a302616511c5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcwindowsmanagerdialog-class"></a>CMFCWindowsManagerDialog クラス
`CMFCWindowsManagerDialog`オブジェクトにより、ユーザーを MDI アプリケーションで、MDI 子ウィンドウを管理します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCWindowsManagerDialog : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCWindowsManagerDialog::CMFCWindowsManagerDialog](#cmfcwindowsmanagerdialog)|`CMFCWindowsManagerDialog` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 `CMFCWindowsManagerDialog`アプリケーションで現在開いている MDI 子ウィンドウの一覧が含まれています。 ユーザーは、このダイアログ ボックスを使用して、MDI 子ウィンドウの状態を手動で制御できます。  
  
 `CMFCWindowsManagerDialog` 内に埋め込まれた、 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)です。 `CMFCWindowsManagerDialog`手動で作成する必要がありますクラスではありません。 代わりに、関数を呼び出して[CMDIFrameWndEx::ShowWindowsDialog](../../mfc/reference/cmdiframewndex-class.md#showwindowsdialog)と作成が表示され、`CMFCWindowsManagerDialog`オブジェクト。  
  
## <a name="example"></a>例  
 次の例で作成する方法、`CMFCWindowsManagerDialog`を呼び出してオブジェクト`CMDIFrameWndEx::ShowWindowsDialog`です。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#18](../../mfc/codesnippet/cpp/cmfcwindowsmanagerdialog-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxWindowsManagerDialog.h  
  
##  <a name="cmfcwindowsmanagerdialog"></a>  CMFCWindowsManagerDialog::CMFCWindowsManagerDialog  
 構築、 [CMFCWindowsManagerDialog](../../mfc/reference/cmfcwindowsmanagerdialog-class.md)オブジェクト。  
  
```  
CMFCWindowsManagerDialog(
    CMDIFrameWndEx* pMDIFrame,  
    BOOL bHelpButton = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pMDIFrame`  
 親ウィンドウまたはオーナー ウィンドウへのポインター。  
  
 [入力] `bHelpButton`  
 フレームワークを表示するかどうかを指定するブール型パラメーター、**ヘルプ**ボタンをクリックします。  
  
### <a name="remarks"></a>コメント  
 ビジュアル マネージャーの詳細については、次を参照してください。[ビジュアル マネージャー](../../mfc/visualization-manager.md)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMDIFrameWndEx クラス](../../mfc/reference/cmdiframewndex-class.md)
