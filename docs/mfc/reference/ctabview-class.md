---
title: CTabView クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
dev_langs:
- C++
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08c0cff2f6586ab5e385808fb806ed435b00bfc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375224"
---
# <a name="ctabview-class"></a>CTabView クラス
`CTabView`クラス タブのコントロール クラスの使用を簡略化 ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) MFC のドキュメント/ビュー アーキテクチャを使用するアプリケーションでします。  
  
## <a name="syntax"></a>構文  
  
```  
class CTabbedView : public CView  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabView::AddView](#addview)|タブ コントロールに新しいビューを追加します。|  
|[CTabView::FindTab](#findtab)|タブ コントロールで、指定されたビューのインデックスを返します。|  
|[CTabView::GetActiveView](#getactiveview)|現在アクティブなビューへのポインターを返します|  
|[CTabView::GetTabControl](#gettabcontrol)|ビューに関連付けられているタブ コントロールへの参照を返します。|  
|[CTabView::RemoveView](#removeview)|タブ コントロールからビューを削除します。|  
|[CTabView::SetActiveView](#setactiveview)|ビューをアクティブになります。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTabView::IsScrollBar](#isscrollbar)|タブのビューに共有の水平スクロール バーがあるかどうかを確認する タブのビューを作成するときに、フレームワークによって呼び出されます。|  
|[CTabView::OnActivateView](#onactivateview)|アクティブまたは非アクティブなタブの表示が行われたときに、フレームワークによって呼び出されます。|  
  
## <a name="remarks"></a>コメント  
 このクラスでは、簡単にドキュメント/ビュー アプリケーションにタブ付きビューを追加します。 `CTabView` `CView`の埋め込みを含むクラスを派生`CMFCTabCtrl`オブジェクト。 `CTabView` サポートするために必要なすべてのメッセージ処理、`CMFCTabCtrl`オブジェクト。 単にからクラスを派生`CTabView`、アプリケーションに接続し、追加`CView`-派生したクラスを使用して、`AddView`メソッドです。 タブ コントロールのタブとしてそれらのビューが表示されます。  
  
 たとえば、さまざまな方法で表すことができるドキュメントがあります: として、スプレッドシート、グラフ、編集可能なフォーム、およびなどです。 作成できます。 必要に応じて、データの描画の個々 のビューに挿入、 `CTabView`-オブジェクトを派生し、追加のコーディングなしタブ付きことができます。  
  
 [TabbedView サンプル: MFC タブ付きビュー アプリケーション](../../visual-cpp-samples.md)の使用方法を示します`CTabView`です。  
  
## <a name="example"></a>例  
 例を次にどのように`CTabView`TabbedView サンプルで使用します。  
  
 [!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxTabView.h  
  
##  <a name="addview"></a>  CTabView::AddView  
 タブ コントロールにビューを追加します。  
  
```  
int AddView(
    CRuntimeClass* pViewClass,  
    const CString& strViewLabel,  
    int iIndex=-1,  
    CCreateContext* pContext=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pViewClass`  
 挿入されたビューのランタイム クラスへのポインター。  
  
 [入力] `strViewLabel`  
 タブのテキストを指定します。  
  
 [入力] `iIndex`  
 ビューを挿入する位置を示す 0 から始まる位置を指定します。 位置が-1 の場合、新しいタブが最後に挿入されます。  
  
 [入力] `pContext`  
 ポインター、`CCreateContext`ビューのです。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合、ビューのインデックス。 それ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 ビューをフレームに埋め込まれているタブ コントロールに追加するには、この関数を呼び出します。  
  
##  <a name="findtab"></a>  CTabView::FindTab  
 タブ コントロールで、指定されたビューのインデックスを返します。  
  
```  
int FindTab(HWND hWndView) const;  
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `hWndView`  
 ビューのハンドルです。  
  
### <a name="return-value"></a>戻り値  
 見つかった場合は、ビューのインデックスそれ以外の場合、-1 を返します。  
  
### <a name="remarks"></a>コメント  
 指定したハンドルを持つビューのインデックスを取得するには、この関数を呼び出します。  
  
##  <a name="getactiveview"></a>  CTabView::GetActiveView  
 現在アクティブなビューへのポインターを返します。  
  
```  
CView* GetActiveView() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のビューでは、有効なポインターまたは`NULL`アクティブなビューが存在しない場合。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="gettabcontrol"></a>  CTabView::GetTabControl  
 ビューに関連付けられているタブ コントロールへの参照を返します。  
  
```  
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```  
  
### <a name="return-value"></a>戻り値  
 ビューに関連付けられているタブ コントロールへの参照。  
  
##  <a name="isscrollbar"></a>  CTabView::IsScrollBar  
 タブのビューに共有の水平スクロール バーがあるかどうかを確認する タブのビューを作成するときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL IsScrollBar() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` タブのビューは、共有のスクロール バーと共に作成する必要がある場合。 それ以外の場合は `FALSE`。  
  
### <a name="remarks"></a>コメント  
 フレームワークがこのメソッドを呼び出すときに、`CTabView`オブジェクトが作成されます。  
  
 上書き、`IsScrollBar`メソッドで、 `CTabView`-クラスと戻り値を派生`TRUE`共有の水平スクロール バーを持つビューを作成する場合。  
  
##  <a name="onactivateview"></a>  CTabView::OnActivateView  
 アクティブまたは非アクティブなタブの表示が行われたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnActivateView(CView* view);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `view`  
 ビューへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、何も行われません。 このメソッドをオーバーライドする`CTabView`-この通知を処理するクラスを派生します。  
  
##  <a name="removeview"></a>  CTabView::RemoveView  
 タブ コントロールからビューを削除します。  
  
```  
BOOL RemoveView(int iTabNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTabNum`  
 削除するビューのインデックス。  
  
### <a name="return-value"></a>戻り値  
 このメソッドが成功した場合、削除されたビューのインデックス。 それ以外の場合は-1。  
  
### <a name="remarks"></a>コメント  
  
##  <a name="setactiveview"></a>  CTabView::SetActiveView  
 ビューをアクティブになります。  
  
```  
BOOL SetActiveView(int iTabNum);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iTabNum`  
 タブのビューの 0 から始まるインデックス。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` 指定されたビューがアクティブで行われた場合`FALSE`場合は、ビューのインデックスが無効です。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。 [CMFCTabCtrl::SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)   
 [CView クラス](../../mfc/reference/cview-class.md)
