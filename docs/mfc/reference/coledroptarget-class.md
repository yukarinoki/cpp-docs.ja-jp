---
title: クラス
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
ms.openlocfilehash: 01eb277da029d06ee44d8e048cf3244f4371a9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374991"
---
# <a name="coledroptarget-class"></a>クラス

ウィンドウと OLE ライブラリの間の通信機構を提供します。

## <a name="syntax"></a>構文

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の値を指定します。](#coledroptarget)|`COleDropTarget` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[コレドロップターゲット::オンドラグエンター](#ondragenter)|カーソルが最初にウィンドウに入ったときに呼び出されます。|
|[コレドロップターゲット::オンドラッグリーブ](#ondragleave)|カーソルがウィンドウの外にドラッグされたときに呼び出されます。|
|[コレドロップターゲット::オンドラッグオーバー](#ondragover)|カーソルがウィンドウ上にドラッグされたときに繰り返し呼び出されます。|
|[次の値を指定します。](#ondragscroll)|カーソルがウィンドウのスクロール領域にドラッグされているかどうかを調べます。|
|[コレドロップターゲット::オンドロップ](#ondrop)|データがウィンドウにドロップされるときに呼び出されます。|
|[コレドロップターゲット::オンドロップエックス](#ondropex)|データがウィンドウにドロップされたときに呼び出されます。|
|[をクリックします。](#register)|ウィンドウを有効なドロップ ターゲットとして登録します。|
|[取り消し](#revoke)|ウィンドウが有効なドロップ ターゲットでなくなる。|

## <a name="remarks"></a>解説

このクラスのオブジェクトを作成すると、ウィンドウは OLE ドラッグ アンド ドロップ機構を使用してデータを受け入れられます。

ドロップ コマンドを受け取るウィンドウを取得するには、まず`COleDropTarget`クラスのオブジェクトを作成し、その後、目的の`CWnd`オブジェクトへのポインターを含む[Register](#register)関数を呼び出します。

OLE を使用したドラッグ アンド ドロップ操作の詳細については[、「OLE ドラッグ アンド ドロップ](../../mfc/drag-and-drop-ole.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coledroptargetcoledroptarget"></a><a name="coledroptarget"></a>次の値を指定します。

クラス`COleDropTarget`のオブジェクトを構築します。

```
COleDropTarget();
```

### <a name="remarks"></a>解説

[Register](#register)を呼び出して、このオブジェクトをウィンドウに関連付けます。

## <a name="coledroptargetondragenter"></a><a name="ondragenter"></a>コレドロップターゲット::オンドラグエンター

カーソルが最初にウィンドウにドラッグされたときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
カーソルが入力するウィンドウへのポインタ。

*オブジェクト*<br/>
ドロップできるデータを含むデータ オブジェクトへのポイント。

*州*<br/>
修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

*ポイント*<br/>
クライアント座標でのカーソルの現在の位置を格納します。

### <a name="return-value"></a>戻り値

*ポイント*で指定された場所でドロップが試行された場合に生じる効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE ドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

- DROPEFFECT_SCROLLドラッグスクロール操作が発生しようとしているか、ターゲットで実行されています。

### <a name="remarks"></a>解説

ウィンドウでドロップ操作を実行できるようにするには、この関数をオーバーライドします。 既定の実装では[、CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)を呼び出 DROPEFFECT_NONEします。

詳細については、Windows SDK の[「IDropTarget::DragEnter」](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter)を参照してください。

## <a name="coledroptargetondragleave"></a><a name="ondragleave"></a>コレドロップターゲット::オンドラッグリーブ

ドラッグ操作が有効な状態でカーソルがウィンドウから離れたときに、フレームワークによって呼び出されます。

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
カーソルが離れるウィンドウへのポインタ。

### <a name="remarks"></a>解説

指定したウィンドウからドラッグ操作を行うときに特別な動作をする場合は、この関数をオーバーライドします。 この関数の既定の実装は[、CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)を呼び出します。

詳細については、Windows SDK[の IDropTarget::DragLeave](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave)を参照してください。

## <a name="coledroptargetondragover"></a><a name="ondragover"></a>コレドロップターゲット::オンドラッグオーバー

カーソルがウィンドウ上にドラッグされたときに、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
カーソルが置かのあるウィンドウへのポインタ。

*オブジェクト*<br/>
ドロップするデータを含むデータ オブジェクトへのポイント。

*州*<br/>
修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

*ポイント*<br/>
クライアント座標でのカーソルの現在の位置を格納します。

### <a name="return-value"></a>戻り値

*ポイント*で指定された場所でドロップが試行された場合に生じる効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE ドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

- DROPEFFECT_SCROLLドラッグ スクロール操作が発生しようとしているか、ターゲットで発生していることを示します。

### <a name="remarks"></a>解説

この関数は、ウィンドウでドロップ操作を行えるようにオーバーライドする必要があります。 この関数の既定の実装では[、CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover)が呼び出され、既定でDROPEFFECT_NONEが返されます。 この関数はドラッグ アンド ドロップ操作中に頻繁に呼び出されるため、できるだけ最適化する必要があります。

詳細については、Windows SDK[の IDropTarget::DragOver を](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover)参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

## <a name="coledroptargetondragscroll"></a><a name="ondragscroll"></a>次の値を指定します。

[OnDragEnter](#ondragenter)または[OnDragOver](#ondragover)を呼び出す前に、スクロール領域内の*ポイント*かどうかを判断する前に、フレームワークによって呼び出されます。

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
カーソルが現在置かれているウィンドウへのポインタ。

*州*<br/>
修飾子キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

*ポイント*<br/>
画面を基準としたカーソルの位置をピクセル単位で指定します。

### <a name="return-value"></a>戻り値

*ポイント*で指定された場所でドロップが試行された場合に生じる効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE ドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

- DROPEFFECT_SCROLLドラッグ スクロール操作が発生しようとしているか、ターゲットで発生していることを示します。

### <a name="remarks"></a>解説

このイベントに対して特別な動作を指定する場合は、この関数をオーバーライドします。 この関数の既定の実装では[、cView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll)を呼び出し、カーソルがウィンドウの境界線内の既定のスクロール領域にドラッグされたときに、DROPEFFECT_NONEを返し、ウィンドウをスクロールします。

## <a name="coledroptargetondrop"></a><a name="ondrop"></a>コレドロップターゲット::オンドロップ

ドロップ操作が発生するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
カーソルが現在置かれているウィンドウへのポインタ。

*オブジェクト*<br/>
ドロップするデータを含むデータ オブジェクトへのポイント。

*ドロップエフェクト*<br/>
ユーザーがドロップ操作に対して選択した効果。 次の 1 つ以上を指定できます。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

*ポイント*<br/>
画面を基準としたカーソルの位置をピクセル単位で指定します。

### <a name="return-value"></a>戻り値

ドロップが成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

フレームワークは最初[に OnDropEx](#ondropex)を呼び出します。 関数が`OnDropEx`ドロップを処理しない場合、フレームワークはこのメンバー関数`OnDrop`を呼び出します。 通常、アプリケーションは、マウスの右ボタンのドラッグ アンド ドロップを処理するために、ビュー クラスの[OnDropEx](../../mfc/reference/cview-class.md#ondropex)をオーバーライドします。 通常、ビュー クラス[OnDrop](../../mfc/reference/cview-class.md#ondrop)は、単純なドラッグ アンド ドロップを処理するために使用されます。

`COleDropTarget::OnDrop` [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop)を呼び出す既定の実装では、既定では FALSE を返します。

詳細については、Windows SDK[の「IDropTarget::Drop」](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop)を参照してください。

## <a name="coledroptargetondropex"></a><a name="ondropex"></a>コレドロップターゲット::オンドロップエックス

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

*Pwnd*<br/>
カーソルが現在置かれているウィンドウへのポインタ。

*オブジェクト*<br/>
ドロップするデータを含むデータ オブジェクトへのポイント。

*ドロップデフォルト*<br/>
現在のキーの状態に基づいて、既定のドロップ操作に対してユーザーが選択した効果。 DROPEFFECT_NONEすることができます。 ドロップ効果については、「解説」で説明します。

*ドロップリスト*<br/>
ドロップ ソースがサポートするドロップ効果のリスト。 ドロップ効果の値は、ビットごとの OR (**&#124;**) 演算を使用して組み合わせることができます。 ドロップ効果については、「解説」で説明します。

*ポイント*<br/>
画面を基準としたカーソルの位置をピクセル単位で指定します。

### <a name="return-value"></a>戻り値

*point*で指定された位置でのドロップ試行から生じたドロップ効果。 ドロップ効果については、「解説」で説明します。

### <a name="remarks"></a>解説

フレームワークは、最初にこの関数を呼び出します。 ドロップを処理しない場合、フレームワークは[OnDrop](#ondrop)を呼び出します。 通常、マウスの右ボタンのドラッグ アンド ドロップをサポートするために、ビュー クラスの[OnDropEx](../../mfc/reference/cview-class.md#ondropex)をオーバーライドします。 通常、ビュー クラス[OnDrop](../../mfc/reference/cview-class.md#ondrop)は、単純なドラッグ アンド ドロップのサポートの場合に使用されます。

呼び出し`COleDropTarget::OnDropEx`の既定の実装[CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). 既定では[、CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)は、単に[OnDrop](#ondrop)メンバー関数を呼び出す必要があることを示すダミー値を返します。

ドロップ効果は、ドロップ操作に関連付けられたアクションを表します。 ドロップ効果の次のリストを参照してください。

- DROPEFFECT_NONE ドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

- DROPEFFECT_SCROLLドラッグ スクロール操作が発生しようとしているか、ターゲットで発生していることを示します。

詳細については、Windows SDK[の「IDropTarget::Drop」](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop)を参照してください。

## <a name="coledroptargetregister"></a><a name="register"></a>をクリックします。

ウィンドウを有効なドロップ ターゲットとして OLE DLL に登録します。

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
ドロップ ターゲットとして登録するウィンドウへのポイント。

### <a name="return-value"></a>戻り値

登録が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

ドロップ操作を受け入れるには、この関数を呼び出す必要があります。

詳細については、Windows SDK[の「RegisterDragDrop」](/windows/win32/api/ole2/nf-ole2-registerdragdrop)を参照してください。

## <a name="coledroptargetrevoke"></a><a name="revoke"></a>取り消し

[Register](#register)の呼び出しを通じてドロップ ターゲットとして登録されているウィンドウを破棄する前に、この関数を呼び出して、ドロップ ターゲットの一覧から削除します。

```
virtual void Revoke();
```

### <a name="remarks"></a>解説

この関数は登録されたウィンドウの[OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy)ハンドラから自動的に呼び出されるため、通常、この関数を明示的に呼び出す必要はありません。

詳細については、Windows SDK の[「取り消しドラッグ ドロップ](/windows/win32/api/ole2/nf-ole2-revokedragdrop)」を参照してください。

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource クラス](../../mfc/reference/coledropsource-class.md)
