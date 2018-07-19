---
title: CDockablePaneAdapter クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::GetWrappedWnd
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::LoadState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SaveState
- AFXDOCKABLEPANEADAPTER/CDockablePaneAdapter::SetWrappedWnd
dev_langs:
- C++
helpviewer_keywords:
- CDockablePaneAdapter [MFC], GetWrappedWnd
- CDockablePaneAdapter [MFC], LoadState
- CDockablePaneAdapter [MFC], SaveState
- CDockablePaneAdapter [MFC], SetWrappedWnd
ms.assetid: 6ed6cf82-f39c-4d0c-bf7c-8641495cf8f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e43f6704476879e1848ce82b3327b23efe2192a8
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026307"
---
# <a name="cdockablepaneadapter-class"></a>CDockablePaneAdapter クラス
`CWnd`の派生ペインのドッキングをサポートします。  
  
## <a name="syntax"></a>構文  
  
```  
class CDockablePaneAdapter : public CDockablePane  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDockablePaneAdapter::GetWrappedWnd](#getwrappedwnd)|ラップされたウィンドウを返します。|  
|[CDockablePaneAdapter::LoadState](#loadstate)|(上書き[cdockablepane::loadstate](http://msdn.microsoft.com/96110136-4f46-4764-8a76-3b4abaf77917))。|  
|[CDockablePaneAdapter::SaveState](#savestate)|(上書き[cdockablepane::savestate](http://msdn.microsoft.com/c5c24249-8d0d-46cb-96d9-9f5c6dc191db))。|  
|[CDockablePaneAdapter::SetWrappedWnd](#setwrappedwnd)||  
  
## <a name="remarks"></a>Remarks  
 通常、フレームワークでは使用すると、このクラスのオブジェクトがインスタンス化します、 [::addtab](../../mfc/reference/cmfcbasetabctrl-class.md#addtab)または[cmfcbasetabctrl::inserttab](../../mfc/reference/cmfcbasetabctrl-class.md#inserttab)メソッド。  
  
 カスタマイズする場合、`CDockablePaneAdapter`動作、そこから新しいクラスを派生して、ランタイム クラス情報を使用して、タブ付きウィンドウに設定だけ[cmfcbasetabctrl::setdockingbarwrapperrtc](../../mfc/reference/cmfcbasetabctrl-class.md#setdockingbarwrapperrtc)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md) [CCmdTarget](../../mfc/reference/ccmdtarget-class.md) [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CBasePane](../../mfc/reference/cbasepane-class.md) [CPane](../../mfc/reference/cpane-class.md) [CDockablePane](../../mfc/reference/cdockablepane-class.md)  
  
 [CDockablePaneAdapter](../../mfc/reference/cdockablepaneadapter-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxDockablePaneAdapter.h  
  
##  <a name="getwrappedwnd"></a>  CDockablePaneAdapter::GetWrappedWnd  
 ウィンドウのドッキング可能なアダプターの基になるウィンドウを返します。  
  
```  
virtual CWnd* GetWrappedWnd() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ラップされたウィンドウへのポインター。  
  
### <a name="remarks"></a>Remarks  
 ラップされたウィンドウにアクセスするのにには、この関数を使用します。  
  
##  <a name="loadstate"></a>  CDockablePaneAdapter::LoadState  
 レジストリからペインの状態を読み込みます。  
  
```  
virtual BOOL LoadState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 プロファイル名。  
  
 [in]*nIndex*  
 プロファイルのインデックス。  
  
 [in]*uiID*  
 ペインの ID  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="savestate"></a>  CDockablePaneAdapter::SaveState  
 レジストリにペインの状態を保存します。  
  
```  
virtual BOOL SaveState(
    LPCTSTR lpszProfileName = NULL,  
    int nIndex = -1,  
    UINT uiID = (UINT) -1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*lpszProfileName*  
 プロファイル名。  
  
 [in]*nIndex*  
 プロファイルのインデックス (既定値は、ウィンドウのコントロール ID)。  
  
 [in]*uiID*  
 ペインの ID  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setwrappedwnd"></a>  CDockablePaneAdapter::SetWrappedWnd  
 ウィンドウのドッキング可能なアダプターの基になるウィンドウを設定します。  
  
```  
virtual BOOL SetWrappedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*我が物*  
 ラップするウィンドウのアダプターは、ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
