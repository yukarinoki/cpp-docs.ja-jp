---
title: CCommonDialog クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCommonDialog
- AFXDLGS/CCommonDialog
- AFXDLGS/CCommonDialog::CCommonDialog
dev_langs:
- C++
helpviewer_keywords:
- CCommonDialog [MFC], CCommonDialog
ms.assetid: 1f68d65f-a0fd-4778-be22-ebbe51a95f95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6821b7a33339b2a143778172caa7a4a22cb101e
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335916"
---
# <a name="ccommondialog-class"></a>CCommonDialog クラス
Windows コモン ダイアログの機能をカプセル化したクラスの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CCommonDialog : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCommonDialog::CCommonDialog](#ccommondialog)|`CCommonDialog` オブジェクトを構築します。|  
  
## <a name="remarks"></a>Remarks  
 次のクラスは、Windows のコモン ダイアログの機能をカプセル化します。  
  
- [CFileDialog](../../mfc/reference/cfiledialog-class.md)  
  
- [CFontDialog](../../mfc/reference/cfontdialog-class.md)  
  
- [CColorDialog](../../mfc/reference/ccolordialog-class.md)  
  
- [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md)  
  
- [CPrintDialog](../../mfc/reference/cprintdialog-class.md)  
  
- [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md)  
  
- [CFindReplaceDialog](../../mfc/reference/cfindreplacedialog-class.md)  
  
- [COleDialog](../../mfc/reference/coledialog-class.md)  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `CCommonDialog`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdlgs.h  
  
##  <a name="ccommondialog"></a>  CCommonDialog::CCommonDialog  
 `CCommonDialog` オブジェクトを構築します。  
  
```  
explicit CCommonDialog(CWnd* pParentWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *pParentWnd*  
 親またはオーナー ウィンドウのオブジェクトを指し示す (型の[CWnd](../../mfc/reference/cwnd-class.md)) ダイアログ オブジェクトが属しています。 NULL の場合、ダイアログ オブジェクトの親ウィンドウは、アプリケーションのメイン ウィンドウに設定されます。  
  
### <a name="remarks"></a>Remarks  
 参照してください[詳細](../../mfc/reference/cdialog-class.md#cdialog)の完全な情報。  
  
## <a name="see-also"></a>関連項目  
 [CDialog クラス](../../mfc/reference/cdialog-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFileDialog クラス](../../mfc/reference/cfiledialog-class.md)   
 [CFontDialog クラス](../../mfc/reference/cfontdialog-class.md)   
 [CColorDialog クラス](../../mfc/reference/ccolordialog-class.md)   
 [CPageSetupDialog クラス](../../mfc/reference/cpagesetupdialog-class.md)   
 [CPrintDialog クラス](../../mfc/reference/cprintdialog-class.md)   
 [CFindReplaceDialog クラス](../../mfc/reference/cfindreplacedialog-class.md)   
 [COleDialog クラス](../../mfc/reference/coledialog-class.md)
