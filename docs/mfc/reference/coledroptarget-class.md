---
title: COleDropTarget クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 9a1633ed48c763b986f3421c33589a05f8bba126
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781641"
---
# <a name="coledroptarget-class"></a>COleDropTarget クラス

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
|[COleDropTarget::OnDragEnter](#ondragenter)|カーソルが最初に、ウィンドウに入ったときに呼び出されます。|
|[COleDropTarget::OnDragLeave](#ondragleave)|カーソルがウィンドウ外にドラッグされるときに呼び出されます。|
|[COleDropTarget::OnDragOver](#ondragover)|ウィンドウの上でカーソルをドラッグするときに繰り返し呼び出されます。|
|[COleDropTarget::OnDragScroll](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされるかどうかを判断するには、呼び出されます。|
|[COleDropTarget::OnDrop](#ondrop)|ウィンドウの既定のハンドラーにデータが削除されるときに呼び出されます。|
|[COleDropTarget::OnDropEx](#ondropex)|ウィンドウでは、最初のハンドラーにデータがドロップされたときに呼び出されます。|
|[COleDropTarget::Register](#register)|有効なドロップ先として、ウィンドウを登録します。|
|[COleDropTarget::Revoke](#revoke)|有効なドロップ ターゲットの中を中断するウィンドウをによりします。|

## <a name="remarks"></a>Remarks

このクラスのオブジェクトを作成すると、OLE のドラッグ アンド ドロップ メカニズムを通じてデータをそのまま使用するためのウィンドウができます。

Drop コマンドも受け入れるように、ウィンドウを取得するのオブジェクトを作成する必要があります最初、`COleDropTarget`クラスを呼び出して、[登録](#register)目的へのポインターを関数`CWnd`唯一のパラメーターとしてオブジェクト。

ドラッグ アンド ドロップ操作の詳細については、OLE を使用して記事を参照して、[ドラッグ アンド ドロップ (OLE)](../../mfc/drag-and-drop-ole.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

##  <a name="coledroptarget"></a>  COleDropTarget::COleDropTarget

クラスのオブジェクトを構築`COleDropTarget`します。

```
COleDropTarget();
```

### <a name="remarks"></a>Remarks

呼び出す[登録](#register)ウィンドウにこのオブジェクトを関連付ける。

##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter

カーソルが最初に、ウィンドウにドラッグされたときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
カーソル ウィンドウへのポインターを入力します。

*pDataObject*<br/>
ドロップ可能なデータを含むデータ オブジェクトへのポインター。

*dwKeyState*<br/>
修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせです。MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。

*ポイント*<br/>
クライアント座標でのカーソルの現在の場所が含まれています。

### <a name="return-value"></a>戻り値

によって指定された場所にドロップが行われた場合に発生する影響*ポイント*します。 次の 1 つ以上を指定できます。

- せずドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- 行った移動操作が実行されます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。

- DROPEFFECT_SCROLL A ドラッグのスクロール操作では、発生するか、ターゲットで発生しています。

### <a name="remarks"></a>Remarks

ウィンドウにドロップ操作を許可するには、この関数をオーバーライドします。 既定の実装[CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)、単に既定でせずが返されます。

詳細については、次を参照してください。 [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK に含まれています。

##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave

ドラッグ操作の実行中に、カーソルがウィンドウを離れたときに、フレームワークによって呼び出されます。

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
カーソルが離れることをウィンドウにポイントします。

### <a name="remarks"></a>Remarks

ドラッグ操作が指定したウィンドウを離れるときに特別な動作が必要な場合は、この関数をオーバーライドします。 この関数の既定の実装を呼び出す[CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)します。

詳細については、次を参照してください。 [IDropTarget::DragLeave](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragleave) Windows SDK に含まれています。

##  <a name="ondragover"></a>  COleDropTarget::OnDragOver

カーソルがウィンドウの上にドラッグされるときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
上にカーソルがウィンドウへのポインター。

*pDataObject*<br/>
削除するデータを含むデータ オブジェクトへのポインター。

*dwKeyState*<br/>
修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせです。MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。

*ポイント*<br/>
クライアント座標でのカーソルの現在の場所が含まれています。

### <a name="return-value"></a>戻り値

によって指定された場所にドロップが行われた場合に発生する影響*ポイント*します。 次の 1 つ以上を指定できます。

- せずドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- 行った移動操作が実行されます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。

- DROPEFFECT_SCROLL を使用して、ドラッグのスクロール操作が実行されるときに、またはターゲットで発生していることを示します。

### <a name="remarks"></a>Remarks

この関数は、ウィンドウにドロップ操作を許可するオーバーライドする必要があります。 この関数の既定の実装を呼び出す[直前](../../mfc/reference/cview-class.md#ondragover)既定でせずが返されます。 この関数は、ドラッグ アンド ドロップ操作中に頻繁に呼び出されると、ため、最適化してください可能な限りです。

詳細については、次を参照してください。 [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover) Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll

呼び出す前にフレームワークによって呼び出されます[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)を決定するかどうか*ポイント*がスクロール可能な領域。

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
カーソルが上に現在のウィンドウへのポインター。

*dwKeyState*<br/>
修飾子キーの状態が含まれています。 これは、次の任意の数の組み合わせです。MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、および MK_RBUTTON します。

*ポイント*<br/>
画面を基準 (ピクセル単位)、カーソルの位置が含まれています。

### <a name="return-value"></a>戻り値

によって指定された場所にドロップが行われた場合に発生する影響*ポイント*します。 次の 1 つ以上を指定できます。

- せずドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- 行った移動操作が実行されます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。

- DROPEFFECT_SCROLL を使用して、ドラッグのスクロール操作が実行されるときに、またはターゲットで発生していることを示します。

### <a name="remarks"></a>Remarks

このイベントの特別な動作を提供したい場合は、この関数をオーバーライドします。 この関数の既定の実装を呼び出す[CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll)せずを返すし、カーソルがウィンドウの枠線内で、既定のスクロール領域にドラッグされるときに、ウィンドウをスクロールします。

##  <a name="ondrop"></a>  COleDropTarget::OnDrop

ドロップ操作が発生するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
カーソルが上に現在のウィンドウへのポインター。

*pDataObject*<br/>
削除するデータを含むデータ オブジェクトへのポインター。

*dropEffect*<br/>
ドロップ操作に対して、ユーザーが選択した結果。 次の 1 つ以上を指定できます。

- DROPEFFECT_COPY コピー操作が実行されます。

- 行った移動操作が実行されます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。

*ポイント*<br/>
画面を基準 (ピクセル単位)、カーソルの位置が含まれています。

### <a name="return-value"></a>戻り値

ドロップダウンに成功した場合は 0 以外それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

フレームワークの最初の呼び出し[OnDropEx](#ondropex)します。 場合、`OnDropEx`関数は、削除を処理しない、フレームワークはこのメンバー関数を呼び出して`OnDrop`します。 通常、アプリケーションがよりも優先[OnDropEx](../../mfc/reference/cview-class.md#ondropex)マウスの右ボタンを処理するためにビュー クラスでは、ドラッグ アンド ドロップします。 ビュー クラスでは通常、 [OnDrop](../../mfc/reference/cview-class.md#ondrop)単純なドラッグ アンド ドロップを処理するために使用します。

既定の実装`COleDropTarget::OnDrop`呼び出し[この関数](../../mfc/reference/cview-class.md#ondrop)既定で FALSE を返しますこれだけです。

詳細については、次を参照してください。 [IDropTarget::Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) Windows SDK に含まれています。

##  <a name="ondropex"></a>  COleDropTarget::OnDropEx

ドロップ操作が発生するときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
カーソルが上に現在のウィンドウへのポインター。

*pDataObject*<br/>
削除するデータを含むデータ オブジェクトへのポインター。

*dropDefault*<br/>
現在のキーの状態に基づいて既定のドロップ操作に対して、ユーザーが選択した結果。 せずになります。 ドロップ効果は、「解説」で説明します。

*dropList*<br/>
ドロップ ソースがサポートしているドロップ効果の一覧。 ビットごとの OR を使用して、ドロップ効果の値を結合することができます (**&#124;**) 操作。 ドロップ効果は、「解説」で説明します。

*ポイント*<br/>
画面を基準 (ピクセル単位)、カーソルの位置が含まれています。

### <a name="return-value"></a>戻り値

によって指定された場所にドロップしようとしたときの原因となったドロップ効果*ポイント*します。 ドロップ効果は、「解説」で説明します。

### <a name="remarks"></a>Remarks

フレームワークは、まず、この関数を呼び出します。 ドロップ、ハンドルされない場合、フレームワーク[OnDrop](#ondrop)します。 オーバーライドして、通常[OnDropEx](../../mfc/reference/cview-class.md#ondropex)マウスの右ボタンをサポートするためにビュー クラスでは、ドラッグ アンド ドロップします。 ビュー クラスでは通常、 [OnDrop](../../mfc/reference/cview-class.md#ondrop)の単純なドラッグ アンド ドロップのサポート ケースを処理するために使用します。

既定の実装`COleDropTarget::OnDropEx`呼び出し[CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)します。 既定では、 [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)だけを示すダミー値を返します、 [OnDrop](#ondrop)メンバー関数を呼び出す必要があります。

ドロップ効果には、drop 操作に関連付けられたアクションについて説明します。 次のドロップ効果の一覧を参照してください。

- せずドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- 行った移動操作が実行されます。

- 元のデータをドロップしたデータから DROPEFFECT_LINK A リンクが確立されます。

- DROPEFFECT_SCROLL を使用して、ドラッグのスクロール操作が実行されるときに、またはターゲットで発生していることを示します。

詳細については、次を参照してください。 [IDropTarget::Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) Windows SDK に含まれています。

##  <a name="register"></a>  COleDropTarget::Register

有効なドロップ先として OLE Dll で、ウィンドウを登録するには、この関数を呼び出します。

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
ドロップ先として登録するのには、ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

登録が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

この関数は、受け入れドロップ操作を呼び出す必要があります。

詳細については、次を参照してください。 [RegisterDragDrop](/windows/desktop/api/ole2/nf-ole2-registerdragdrop) Windows SDK に含まれています。

##  <a name="revoke"></a>  COleDropTarget::Revoke

この関数を呼び出すことによって、ドロップ先として登録されている任意のウィンドウを破棄する前に[登録](#register)ドロップ ターゲットの一覧から削除します。

```
virtual void Revoke();
```

### <a name="remarks"></a>Remarks

この関数から自動的に呼び出される、 [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)が登録されている場合は、この関数を明示的に呼び出す必要は通常、ウィンドウのハンドラー。

詳細については、次を参照してください。 [RevokeDragDrop](/windows/desktop/api/ole2/nf-ole2-revokedragdrop) Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[MFC サンプル HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプルの OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource クラス](../../mfc/reference/coledropsource-class.md)
