---
title: 関数クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
dev_langs:
- C++
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb52739977b641cd5d52f018efcd30a51ecf1e32
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="coledroptarget-class"></a>関数クラス
ウィンドウと OLE ライブラリの間の通信機構を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|`COleDropTarget` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|カーソルがウィンドウを最初に入ったときに呼び出されます。|  
|[COleDropTarget::OnDragLeave](#ondragleave)|カーソルがウィンドウ外にドラッグされたときに呼び出されます。|  
|[COleDropTarget::OnDragOver](#ondragover)|ウィンドウの上でカーソルをドラッグするときに繰り返し呼び出されます。|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされるかどうかを決定するには、呼び出されます。|  
|[COleDropTarget::OnDrop](#ondrop)|ウィンドウでは、既定のハンドラーにデータが削除されるときに呼び出されます。|  
|[COleDropTarget::OnDropEx](#ondropex)|ウィンドウ、最初のハンドラーにデータが削除されるときに呼び出されます。|  
|[COleDropTarget::Register](#register)|有効なドロップ先として、ウィンドウを登録します。|  
|[COleDropTarget::Revoke](#revoke)|によって有効なドロップ ターゲットの中を中断するウィンドウです。|  
  
## <a name="remarks"></a>コメント  
 OLE のドラッグ アンド ドロップ メカニズムによりデータをそのまま使用するためのウィンドウは、このクラスのオブジェクトを作成できます。  
  
 コマンドの drop コマンドをそのまま使用するためのウィンドウを取得するのオブジェクトを作成する必要があります最初、`COleDropTarget`クラス、およびを呼び出す、[登録](#register)目的へのポインターを持つ関数`CWnd`唯一のパラメーターとしてオブジェクト。  
  
 ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して、[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropTarget`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coledroptarget"></a>  COleDropTarget::COleDropTarget  
 クラスのオブジェクトを構築`COleDropTarget`です。  
  
```  
COleDropTarget();
```  
  
### <a name="remarks"></a>コメント  
 呼び出す[登録](#register)ウィンドウにこのオブジェクトを関連付ける。  
  
##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter  
 カーソルがウィンドウに最初にドラッグされたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソル ウィンドウへのポインターを開始しています。  
  
 `pDataObject`  
 削除するデータを含むデータ オブジェクトへのポインター。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**です。  
  
 `point`  
 クライアント座標で、カーソルの現在の場所が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが行われた場合に発生する影響`point`です。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_NONE` ドロップは許可されていません。  
  
- `DROPEFFECT_COPY` コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE` 移動操作が実行されます。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクが確立できません。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作では、発生するか、ターゲットで発生しています。  
  
### <a name="remarks"></a>コメント  
 ウィンドウのドロップ操作を許可するには、この関数をオーバーライドします。 既定の実装[CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)、単に返す`DROPEFFECT_NONE`既定です。  
  
 詳細については、次を参照してください。 [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) Windows SDK に含まれています。  
  
##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave  
 ドラッグ操作の実行中に、カーソルがウィンドウを離れたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ウィンドウへのポインター、カーソルのままです。  
  
### <a name="remarks"></a>コメント  
 ドラッグ操作が指定されたウィンドウを離れると、特別な動作をする場合は、この関数をオーバーライドします。 この関数の既定の実装を呼び出す[CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)です。  
  
 詳細については、次を参照してください。 [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) Windows SDK に含まれています。  
  
##  <a name="ondragover"></a>  COleDropTarget::OnDragOver  
 カーソルがウィンドウの上にドラッグされたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に、ウィンドウへのポインター。  
  
 `pDataObject`  
 削除するデータを格納するデータ オブジェクトへのポインター。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**です。  
  
 `point`  
 クライアント座標で、カーソルの現在の場所が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが行われた場合に発生する影響`point`です。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_NONE` ドロップは許可されていません。  
  
- `DROPEFFECT_COPY` コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE` 移動操作が実行されます。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクが確立できません。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
### <a name="remarks"></a>コメント  
 この関数は、ドロップ操作 ウィンドウで使用できるようにオーバーライドする必要があります。 この関数の既定の実装を呼び出す[直前](../../mfc/reference/cview-class.md#ondragover)、返された`DROPEFFECT_NONE`既定。 この関数が呼び出されるため、ドラッグ アンド ドロップ操作中に頻繁に、必要があります最適化することが可能な限りです。  
  
 詳細については、次を参照してください。 [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) Windows SDK に含まれています。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll  
 呼び出しの前にフレームワークによって呼び出されます[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)を決定するかどうか`point`スクロール可能な領域はします。  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に現在のウィンドウへのポインター。  
  
 `dwKeyState`  
 修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: **MK_CONTROL**、 **MK_SHIFT**、 **MK_ALT**、 **MK_LBUTTON**、 **MK_MBUTTON**、および**MK_RBUTTON**です。  
  
 `point`  
 画面に対して相対的ピクセル単位で、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが行われた場合に発生する影響`point`です。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_NONE` ドロップは許可されていません。  
  
- `DROPEFFECT_COPY` コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE` 移動操作が実行されます。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクが確立できません。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
### <a name="remarks"></a>コメント  
 このイベントの特別な動作を提供する場合は、この関数をオーバーライドします。 この関数の既定の実装を呼び出す[CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll)を返す`DROPEFFECT_NONE`し、カーソルがウィンドウの境界内の既定のスクロール領域にドラッグされると、ウィンドウをスクロールします。  
  
##  <a name="ondrop"></a>  COleDropTarget::OnDrop  
 ドロップ操作が行われるときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に現在のウィンドウへのポインター。  
  
 `pDataObject`  
 削除するデータを格納するデータ オブジェクトへのポインター。  
  
 `dropEffect`  
 Drop 操作のユーザーが選択した結果。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_COPY` コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE` 移動操作が実行されます。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクが確立できません。  
  
 `point`  
 画面に対して相対的ピクセル単位で、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 ドロップダウンが成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 最初のフレームワーク[OnDropEx](#ondropex)です。 場合、`OnDropEx`関数は、削除を処理しません、フレームワークが、このメンバー関数を呼び出す`OnDrop`です。 通常、アプリケーションがよりも優先[OnDropEx](../../mfc/reference/cview-class.md#ondropex)マウスの右ボタンを処理するビュー クラスでは、ドラッグ アンド ドロップします。 ビュー クラスでは通常、 [OnDrop](../../mfc/reference/cview-class.md#ondrop)単純なドラッグ アンド ドロップの処理に使用します。  
  
 既定の実装`COleDropTarget::OnDrop`呼び出し[この関数](../../mfc/reference/cview-class.md#ondrop)、単に返す**FALSE**既定です。  
  
 詳細については、次を参照してください。 [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) Windows SDK に含まれています。  
  
##  <a name="ondropex"></a>  COleDropTarget::OnDropEx  
 ドロップ操作が行われるときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 カーソルを上に現在のウィンドウへのポインター。  
  
 `pDataObject`  
 削除するデータを格納するデータ オブジェクトへのポインター。  
  
 `dropDefault`  
 現在のキーの状態に基づく既定のドロップ操作のユーザーが選択した結果。 できます`DROPEFFECT_NONE`です。 ドロップ効果は、「解説」セクションで説明します。  
  
 `dropList`  
 ドロップ ソースでサポートされる、ドロップ効果の一覧。 ビットごとの OR を使用して、ドロップ効果の値を結合することができます ( **&#124;**) 操作です。 ドロップ効果は、「解説」セクションで説明します。  
  
 `point`  
 画面に対して相対的ピクセル単位で、カーソルの位置が含まれています。  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップしようとしたときの原因となったドロップ効果`point`です。 ドロップ効果は、「解説」セクションで説明します。  
  
### <a name="remarks"></a>コメント  
 フレームワークは、まず、この関数を呼び出します。 これで、削除が処理しない場合、フレームワーク[OnDrop](#ondrop)です。 通常がオーバーライドされます[OnDropEx](../../mfc/reference/cview-class.md#ondropex)マウスの右ボタンをサポートするためにビュー クラスでは、ドラッグ アンド ドロップします。 ビュー クラスでは通常、 [OnDrop](../../mfc/reference/cview-class.md#ondrop)単純なドラッグ アンド ドロップのサポートのケースを処理するために使用します。  
  
 既定の実装`COleDropTarget::OnDropEx`呼び出し[CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)です。 既定では、 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)ダミーの値を示す値を返します、 [OnDrop](#ondrop)メンバー関数を呼び出す必要があります。  
  
 ドロップ効果には、drop 操作に関連付けられたアクションがについて説明します。 次のようなドロップ効果の一覧を参照してください。  
  
- `DROPEFFECT_NONE` ドロップは許可されていません。  
  
- `DROPEFFECT_COPY` コピー操作が実行されます。  
  
- `DROPEFFECT_MOVE` 移動操作が実行されます。  
  
- `DROPEFFECT_LINK` ドロップされたデータから、元のデータへのリンクが確立できません。  
  
- `DROPEFFECT_SCROLL` ドラッグ スクロール操作が発生するか、ターゲットで発生していることを示します。  
  
 詳細については、次を参照してください。 [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) Windows SDK に含まれています。  
  
##  <a name="register"></a>  COleDropTarget::Register  
 有効なドロップ先として OLE Dll を現在のウィンドウを登録するには、この関数を呼び出します。  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 ドロップ先として登録するのには、ウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 登録が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は、受け入れられるをドロップ操作を呼び出す必要があります。  
  
 詳細については、次を参照してください。 [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) Windows SDK に含まれています。  
  
##  <a name="revoke"></a>  COleDropTarget::Revoke  
 この関数を呼び出すことによって、ドロップ先として登録されている任意のウィンドウを破棄する前に[登録](#register)ドロップ ターゲットの一覧から削除します。  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>コメント  
 この関数から自動的に呼び出されます、 [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)が登録されている場合は、この関数を明示的に呼び出す必要は通常、ウィンドウのハンドラー。  
  
 詳細については、次を参照してください。 [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) Windows SDK に含まれています。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプル OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDropSource クラス](../../mfc/reference/coledropsource-class.md)
