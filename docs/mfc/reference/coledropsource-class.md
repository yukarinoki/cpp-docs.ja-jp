---
title: COleDropSource クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0994eb1b0293bb31fdb1cd4659256b978ebd69d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219366"
---
# <a name="coledropsource-class"></a>COleDropSource クラス
によりデータがドロップ先にドラッグします。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|`COleDropSource` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|カーソルをドラッグ アンド ドロップ操作中に変更します。|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|ドラッグ アンド ドロップ操作中にマウスのキャプチャを処理します。|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|ドラッグするかどうかを確認するチェックを続行する必要があります。|  
  
## <a name="remarks"></a>Remarks  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)クラスは、ドラッグ アンド ドロップ操作の受信側の部分を処理します。 `COleDropSource`オブジェクトがドラッグ操作を開始するときの特定、ドラッグ操作中にフィードバックを提供して、ドラッグ操作の終了を決定する責任を負います。  
  
 使用する、`COleDropSource`オブジェクト、コンス トラクターを呼び出すだけです。 これは、マウス クリックなど、どのようなイベントの開始を使用してドラッグ操作を決定するプロセスを簡略化[された](../../mfc/reference/coledatasource-class.md#dodragdrop)、[クラス](../../mfc/reference/coleclientitem-class.md#dodragdrop)、または[判定できます](../../mfc/reference/coleserveritem-class.md#dodragdrop)関数。 これらの関数を作成、`COleDropSource`オブジェクト。 既定の動作を変更したい場合があります、`COleDropSource`オーバーライド可能な関数です。 これらのメンバー関数は、フレームワークによって、適切なタイミングで呼び出されます。  
  
 ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して、[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。  
  
 詳細については、次を参照してください。 [IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource) Windows SDK に含まれています。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="coledropsource"></a>  COleDropSource::COleDropSource  
 `COleDropSource` オブジェクトを構築します。  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback  
 フレームワークによって呼び出された後[COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover)または[COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter)します。  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 *dropEffect*  
 ユーザーに表示するには効果は、通常はどのようなことを示すこの時点で、選択したデータのドロップが発生した場合に起こりません。 通常、これは、最新の呼び出しによって返される値[CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)または[直前](../../mfc/reference/cview-class.md#ondragover)します。 次の 1 つ以上を指定できます。  
  
- せずドロップは許可されません。  
  
- DROPEFFECT_COPY コピー操作が実行されます。  
  
- 行った移動操作が実行されます。  
  
- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。  
  
- DROPEFFECT_SCROLL A ドラッグのスクロール操作では、発生するか、ターゲットで発生しています。  
  
### <a name="return-value"></a>戻り値  
 ドラッグする場合の操作が進行中、されていない場合は NOERROR を返します。  
  
### <a name="remarks"></a>Remarks  
 この時点で、ドロップが発生した場合、何が起こるかについてフィードバックを提供するには、この関数をオーバーライドします。 既定の実装では、OLE の既定のカーソルを使用します。 ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して、[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。  
  
 詳細については、次を参照してください。 [IDropSource::GiveFeedback](/windows/desktop/api/oleidl/nf-oleidl-idropsource-givefeedback)、 [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover)、および[IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK に含まれています。  
  
##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag  
 メソッドを呼び出して、イベントが発生したときに、フレームワークがマウスの左ボタンを押すなどのドラッグ操作を開始します。  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 *我が物*  
 選択したデータを含むウィンドウへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ドラッグすることができる場合、それ以外の場合 0 0 以外の値。  
  
### <a name="remarks"></a>Remarks  
 ドラッグの処理を開始する方法を変更する場合は、この関数をオーバーライドします。 既定の実装では、マウスをキャプチャし、ユーザーが左または右マウス ボタンをクリックしてまたはマウスを解放した時点で、esc キーをヒットするまでに、ドラッグ モードのままです。  
  
##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag  
 ドラッグが開始されたこの関数は、ドラッグ操作が取り消されたか完了するまで、framework によって繰り返し呼び出されます。  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>パラメーター  
 *bEscapePressed*  
 最後の呼び出し以降に ESC キーが押されたかどうかを示す`COleDropSource::QueryContinueDrag`します。  
  
 *ドロップ*  
 キーボードの修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせ: MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。  
  
### <a name="return-value"></a>戻り値  
 DRAGDROP_S_CANCEL、ESC キーまたは右ボタンが押された場合、または左ボタンがある場合は、ドラッグを開始する前に発生します。 DRAGDROP_S_DROP ドロップ操作が発生した場合。 それ以外の場合 s_ok を返します。  
  
### <a name="remarks"></a>Remarks  
 この関数がドラッグ ポイントを変更したい場合はキャンセル オーバーライドまたはドロップが発生します。  
  
 既定の実装では、ドロップを開始します。 または、次のように、ドラッグをキャンセルします。 ESC キーまたはマウスの右ボタンが押されたときに、ドラッグ操作をキャンセルします。 ドラッグの開始後、マウスの左ボタンが発生したときに、ドロップ操作が開始します。 それ以外の場合、S_OK を返し、さらに操作を実行しません。  
  
 この関数が頻繁に呼び出されるため、最適化してください可能な限りです。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル HIERSVR](../../visual-cpp-samples.md)   
 [MFC サンプルの OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)



