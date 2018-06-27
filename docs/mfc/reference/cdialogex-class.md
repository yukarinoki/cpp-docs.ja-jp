---
title: CDialogEx クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialogEx
- AFXDIALOGEX/CDialogEx
- AFXDIALOGEX/CDialogEx::CDialogEx
- AFXDIALOGEX/CDialogEx::SetBackgroundColor
- AFXDIALOGEX/CDialogEx::SetBackgroundImage
dev_langs:
- C++
helpviewer_keywords:
- CDialogEx [MFC], CDialogEx
- CDialogEx [MFC], SetBackgroundColor
- CDialogEx [MFC], SetBackgroundImage
ms.assetid: a6ed3b1f-aef8-4b66-ac78-2160faf63c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff365134a9b952b92211418c03d147a65077c66e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951853"
---
# <a name="cdialogex-class"></a>CDialogEx クラス
`CDialogEx` クラスは、ダイアログ ボックスの背景色と背景イメージを指定します。   
  
## <a name="syntax"></a>構文  
  
```  
class CDialogEx : public CDialog  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogEx::CDialogEx](#cdialogex)|`CDialogEx` オブジェクトを構築します。|  
|`CDialogEx::~CDialogEx`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDialogEx::SetBackgroundColor](#setbackgroundcolor)|ダイアログ ボックスの背景色を設定します。|  
|[CDialogEx::SetBackgroundImage](#setbackgroundimage)|ダイアログ ボックスの背景イメージを設定します。|  
  
## <a name="remarks"></a>Remarks  
 `CDialogEx` クラスを使用するには、ダイアログ ボックス クラスを `CDialogEx` クラスではなく `CDialog` クラスから派生させます。  
  
 ダイアログ ボックス イメージは、リソース ファイルに格納されます。 フレームワークは、リソース ファイルから読み込まれたイメージを自動的に削除します。 現在の背景イメージをプログラムで削除するを呼び出して、 [CDialogEx::SetBackgroundImage](#setbackgroundimage)メソッドまたは実装、`OnDestroy`イベント ハンドラー。 呼び出すと、 [CDialogEx::SetBackgroundImage](#setbackgroundimage)メソッド、パス、`HBITMAP`イメージ ハンドルとしてパラメーター。 `CDialogEx` オブジェクトがイメージの所有権を取得し、`m_bAutoDestroyBmp` フラグが `TRUE` である場合は、そのイメージを削除します。  
  
 A`CDialogEx`オブジェクトの親になることができます、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクト。 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトの呼び出し、`CDialogEx::SetActiveMenu`メソッドと、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが表示されます。 その後、`CDialogEx`オブジェクトが処理されるまで、あらゆるメニュー イベント、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)オブジェクトが閉じられています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdialogex.h  
  
##  <a name="cdialogex"></a>  CDialogEx::CDialogEx  
 `CDialogEx` オブジェクトを構築します。  
  
```  
CDialogEx(
    UINT nIDTemplate,  
    CWnd* pParent=NULL);

 
CDialogEx(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nIDTemplate*  
 ダイアログ ボックス テンプレートのリソース ID です。  
  
 [in]*lpszTemplateName*  
 ダイアログ ボックス テンプレートのリソースの名前。  
  
 [in]*pParent*  
 親ウィンドウへのポインター。 既定値は `NULL` です。  
  
 [in]*pParentWnd*  
 親ウィンドウへのポインター。 既定値は `NULL` です。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setbackgroundcolor"></a>  CDialogEx::SetBackgroundColor  
 ダイアログ ボックスの背景色を設定します。  
  
```  
void SetBackgroundColor(
    COLORREF color,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*色*  
 色の RGB 値。  
  
 [in]*bRepaint*  
 `TRUE` 画面をすぐに更新するにはそれ以外の場合、`FALSE`です。 既定値は `TRUE` です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setbackgroundimage"></a>  CDialogEx::SetBackgroundImage  
 ダイアログ ボックスの背景イメージを設定します。  
  
```  
void SetBackgroundImage(
    HBITMAP hBitmap,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bAutoDestroy=TRUE,  
    BOOL bRepaint=TRUE);

 
BOOL SetBackgroundImage(
    UINT uiBmpResId,  
    BackgroundLocation location=BACKGR_TILE,  
    BOOL bRepaint=TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hBitmap*  
 背景イメージへのハンドル。  
  
 [in]*uiBmpResId*  
 背景画像のリソース ID です。  
  
 [in]*場所*  
 1 つ、`CDialogEx::BackgroundLocation`イメージの場所を指定する値。 有効な値には、BACKGR_TILE、BACKGR_TOPLEFT、BACKGR_TOPRIGHT、BACKGR_BOTTOMLEFT、および BACKGR_BOTTOMRIGHT が含まれます。 既定値は、BACKGR_TILE です。  
  
 [in]*bAutoDestroy*  
 `TRUE` 背景イメージを自動的に破棄するにはそれ以外の場合、`FALSE`です。  
  
 [in]*bRepaint*  
 `TRUE` ダイアログ ボックスをすぐに再描画するにはそれ以外の場合、`FALSE`です。  
  
### <a name="return-value"></a>戻り値  
 2 番目のメソッド オーバー ロード構文、`TRUE`メソッドが成功した、それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 指定したイメージは、ダイアログ ボックスのクライアント領域に合わせて伸縮されません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)   
 [CContextMenuManager クラス](../../mfc/reference/ccontextmenumanager-class.md)
