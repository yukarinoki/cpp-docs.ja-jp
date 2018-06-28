---
title: CMFCDropDownFrame クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::Create
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentMenuBar
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::GetParentPopupMenu
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::RecalcLayout
- AFXDROPDOWNTOOLBAR/CMFCDropDownFrame::SetAutoDestroy
dev_langs:
- C++
helpviewer_keywords:
- CMFCDropDownFrame [MFC], Create
- CMFCDropDownFrame [MFC], GetParentMenuBar
- CMFCDropDownFrame [MFC], GetParentPopupMenu
- CMFCDropDownFrame [MFC], RecalcLayout
- CMFCDropDownFrame [MFC], SetAutoDestroy
ms.assetid: 09ff81a9-de00-43ec-9df9-b626f7728c4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c7264273f3db1dab1e6cab72333c0629a802e28
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041995"
---
# <a name="cmfcdropdownframe-class"></a>CMFCDropDownFrame クラス
ドロップダウン ツールバーとツールバーのドロップダウン ボタンにドロップダウン フレーム ウィンドウの機能を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCDropDownFrame : public CMiniFrameWnd  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCDropDownFrame::CMFCDropDownFrame`|既定のコンストラクター|  
|`CMFCDropDownFrame::~CMFCDropDownFrame`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCDropDownFrame::Create](#create)|`CMFCDropDownFrame` オブジェクトを作成します。|  
|`CMFCDropDownFrame::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|  
|[CMFCDropDownFrame::GetParentMenuBar](#getparentmenubar)|ドロップダウンのフレームの親のメニュー バーを取得します。|  
|[CMFCDropDownFrame::GetParentPopupMenu](#getparentpopupmenu)|ドロップダウンのフレームの親のポップアップ メニューを取得します。|  
|`CMFCDropDownFrame::GetThisClass`|ポインターを取得するために、フレームワークで使用される、 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)このクラス型に関連付けられているオブジェクト。|  
|[CMFCDropDownFrame::RecalcLayout](#recalclayout)|ドロップダウンのフレームを再配置します。|  
|[CMFCDropDownFrame::SetAutoDestroy](#setautodestroy)|子のツールバーのドロップダウン ウィンドウが自動的に破棄されるかどうかを設定します。|  
  
### <a name="remarks"></a>Remarks  
 このクラスは、コードから直接使用するものではありません。  
  
 フレームワークでは、このクラスを使用するフレームの動作を提供する、`CMFCDropDownToolbar`と`CMFCDropDownToolbarButton`クラスです。 これらのクラスの詳細については、次を参照してください。 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)と[CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)です。  
  
## <a name="example"></a>例  
 次の例へのポインターを取得する方法を示します、`CMFCDropDownFrame`オブジェクトから、`CFrameWnd`クラス、および自動的に破棄するツールバーのドロップダウン ウィンドウの子を設定する方法です。  
  
 [!code-cpp[NVC_MFC_RibbonApp#36](../../mfc/reference/codesnippet/cpp/cmfcdropdownframe-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CFrameWnd](../../mfc/reference/cframewnd-class.md)  
  
 [CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)  
  
 [CMFCDropDownFrame](../../mfc/reference/cmfcdropdownframe-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxdropdowntoolbar.h  
  
##  <a name="create"></a>  CMFCDropDownFrame::Create  
 `CMFCDropDownFrame` オブジェクトを作成します。  
  
```  
virtual BOOL Create(
    CWnd* pWndParent,  
    int x,  
    int y,  
    CMFCDropDownToolBar* pWndOriginToolbar);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pWndParent*|ドロップダウンのフレームの親ウィンドウです。|  
|[in]*x*|ドロップダウンのフレームの場所の水平画面座標。|  
|[in]*y*|ドロップダウンのフレームの場所の垂直画面座標。|  
|[in]*pWndOriginToolbar*|このメソッドを使用して新しいドロップダウン フレーム オブジェクトを設定するドロップダウン ボタンを持つツールバー。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 場合は、ドロップダウンのフレームが正常に作成されました。それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ベース[CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex)でドロップダウンのフレーム ウィンドウを作成する方法、`WS_POPUP`スタイル。 指定した画面座標にあるドロップダウンのフレーム ウィンドウが表示されます。 このメソッドは失敗、 [CMiniFrameWnd::CreateEx](../../mfc/reference/cminiframewnd-class.md#createex)メソッドを返します。`FALSE`です。  
  
 `CMFCDropDownFrame`クラスは、指定されたコピーを作成`CMFCDropDownToolBar`パラメーター。 このメソッドは、ボタンのイメージとボタンの状態から、コピー、`pWndOriginToolbar`パラメーターを`m_pWndOriginToolbar`データ メンバーです。  
  
##  <a name="getparentmenubar"></a>  CMFCDropDownFrame::GetParentMenuBar  
 ドロップダウンのフレームの親のメニュー バーを取得します。  
  
```  
CMFCMenuBar* GetParentMenuBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドロップダウンのフレームの親のメニュー バーへのポインターまたは`NULL`フレームに親があるない場合。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、親ボタンから親メニュー バーを取得します。 このメソッドが戻る`NULL`ドロップダウン フレームには親ボタンがないか、親のボタンがメニュー バーの親を持たない場合。  
  
##  <a name="getparentpopupmenu"></a>  CMFCDropDownFrame::GetParentPopupMenu  
 ドロップダウンのフレームの親のポップアップ メニューを取得します。  
  
```  
CMFCDropDownFrame* GetParentPopupMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ドロップダウンのフレームの親のドロップダウン メニューへのポインターまたは`NULL`フレームに親があるない場合。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、親ボタンから、親メニューを取得します。 このメソッドが戻る`NULL`ドロップダウン フレームには親ボタンがないか、親ボタンには、親メニューがない場合。  
  
##  <a name="recalclayout"></a>  CMFCDropDownFrame::RecalcLayout  
 ドロップダウンのフレームを再配置します。  
  
```  
virtual void RecalcLayout(BOOL bNotify = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*bNotify*|使用されません。|  
  
### <a name="remarks"></a>Remarks  
 フレームワークは、ドロップダウンのフレームが作成されるか、親ウィンドウのサイズが変更されるときに、このメソッドを呼び出します。 このメソッドは、親ウィンドウのサイズと位置を使用して、ドロップ ダウン フレームのサイズと位置を計算します。  
  
##  <a name="setautodestroy"></a>  CMFCDropDownFrame::SetAutoDestroy  
 子のツールバーのドロップダウン ウィンドウが自動的に破棄されるかどうかを設定します。  
  
```  
void SetAutoDestroy(BOOL bAutoDestroy = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bAutoDestroy*  
 `TRUE` 自動的にウィンドウを破棄する、関連付けられたドロップダウン ツールバーです。それ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
 場合*bAutoDestroy*は`TRUE`、続いて、`CMFCDropDownFrame`デストラクターは、ドロップダウン ツールバーが関連付けられているウィンドウを破棄します。 既定値は `TRUE` です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCDropDownToolBar クラス](../../mfc/reference/cmfcdropdowntoolbar-class.md)   
 [CMFCDropDownToolbarButton クラス](../../mfc/reference/cmfcdropdowntoolbarbutton-class.md)
