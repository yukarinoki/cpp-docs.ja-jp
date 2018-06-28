---
title: CMFCTabDropTarget クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68d78e221b9bcdbffbfc80ba26c6106498c4fa41
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040988"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget クラス
タブ コントロールと OLE ライブラリ間の通信機構を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|既定のコンストラクター|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|ユーザーがタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter))。|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|ユーザーは、フォーカスのあるタブ ウィンドウ外でオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave))。|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|ユーザーは、フォーカスのあるタブ ウィンドウ上にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover))。|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|ユーザーがドラッグ操作の最後に、マウス ボタンを離したときに、フレームワークによって呼び出されます。 (上書き[COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex))。|  
|[CMFCTabDropTarget::Register](#register)|OLE ドラッグ アンド ドロップ操作の対象にできる 1 つとして、コントロールを登録します。|  
  
### <a name="remarks"></a>Remarks  
 このクラスにドラッグ アンド ドロップのサポートを提供する、`CMFCBaseTabCtrl`クラスです。 使用して、アプリケーションが OLE ライブラリを初期化する場合、 [AfxOleInit](ole-initialization.md#afxoleinit)関数、`CMFCBaseTabCtrl`オブジェクトにドラッグ アンド ドロップ操作を登録します。  
  
 `CMFCTabDropTarget`クラスがドラッグ操作がアクティブなが発生すると、カーソルの下にあるタブをすることで、基本クラスを拡張します。 ドラッグ アンド ドロップ操作の詳細については、次を参照してください。[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)です。  
  
## <a name="example"></a>例  
 `CMFCTabDropTarget` オブジェクトを構築して、その `Register` メソッドを使用する方法を、次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [関数](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxbasetabctrl.h  
  
##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter  
 ユーザーがタブ ウィンドウにオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pWnd*|使用されません。|  
|[in]*pDataObject*|ユーザーがドラッグされるオブジェクトへのポインター。|  
|[in]*ドロップ*|修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。|  
|[in]*ポイント*|クライアント座標で、カーソルの場所です。|  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが発生した場合に発生する影響*ポイント*です。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Remarks  
 このメソッドが戻る`DROPEFFECT_NONE`ツールバー フレームワークがカスタマイズ モードではない、またはクリップボード データ形式が使用できない場合。 それ以外の場合、呼び出しの結果を返します`CMFCBaseTabCtrl::OnDragEnter`指定されたパラメーターを使用します。  
  
 カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)です。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)です。  
  
##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave  
 ユーザーは、フォーカスのあるタブ ウィンドウ外でオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pWnd*|使用されません。|  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、`CMFCBaseTabCtrl::OnDragLeave`ドラッグ操作を実行するメソッド。  
  
##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver  
 ユーザーは、フォーカスのあるタブ ウィンドウ上にオブジェクトをドラッグしたときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pWnd*|使用されません。|  
|[in]*pDataObject*|ユーザーがドラッグされるオブジェクトへのポインター。|  
|[in]*ドロップ*|修飾子キーの状態を格納します。 これは、次の任意の数の組み合わせ: `MK_CONTROL`、 `MK_SHIFT`、 `MK_ALT`、 `MK_LBUTTON`、 `MK_MBUTTON`、および`MK_RBUTTON`です。|  
|[in]*ポイント*|クライアント座標でマウス ポインターの場所です。|  
  
### <a name="return-value"></a>戻り値  
 によって指定された位置にドロップが発生した場合に発生する影響*ポイント*です。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、ドラッグ操作がアクティブなが発生すると、カーソルの下にあるタブを使用します。 返します`DROPEFFECT_NONE`ツールバー フレームワークがカスタマイズ モードではない、またはクリップボード データ形式が使用できない場合。 それ以外の場合、呼び出しの結果を返します`CMFCBaseTabCtrl::OnDragOver`指定されたパラメーターを使用します。  
  
 カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)です。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)です。  
  
##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx  
 ユーザーがドラッグ操作の最後に、マウス ボタンを離したときに、フレームワークによって呼び出されます。  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pWnd*|使用されません。|  
|[in]*pDataObject*|ユーザーがドラッグされるオブジェクトへのポインター。|  
|[in]*dropEffect*|既定のドロップ操作です。|  
|[in]*ドロップダウン リスト*|使用されません。|  
|[in]*ポイント*|クライアント座標でマウス ポインターの場所です。|  
  
### <a name="return-value"></a>戻り値  
 結果として得られるドロップ効果。 次の 1 つ以上を指定できます。  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す`CMFCBaseTabCtrl::OnDrop`ツールバー フレームワークがカスタマイズ モードであり、クリップボード データ形式が使用可能な場合です。 場合に呼び出し`CMFCBaseTabCtrl::OnDrop`0 以外の値、このメソッドを返しますで指定された既定のドロップの結果を返します*dropEffect*です。 このメソッドを返しますそれ以外の場合、`DROPEFFECT_NONE`です。 ドロップ効果の詳細については、次を参照してください。 [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex)です。  
  
 カスタマイズ モードの詳細については、次を参照してください。 [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)です。 クリップボード データ形式の詳細については、次を参照してください。 [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)です。  
  
##  <a name="register"></a>  CMFCTabDropTarget::Register  
 OLE ドラッグ アンド ドロップ操作の対象にできる 1 つとして、コントロールを登録します。  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>パラメーター  
  
|||  
|-|-|  
|パラメーター|説明|  
|[in]*pOwner*|ドロップ先として登録するタブ コントロールです。|  
  
### <a name="return-value"></a>戻り値  
 登録が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを呼び出す[COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register)ドラッグ アンド ドロップ操作のコントロールを登録します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)



