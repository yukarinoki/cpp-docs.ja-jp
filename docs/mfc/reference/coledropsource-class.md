---
title: COleDropSource クラス
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: 324c4b7273f021b43c319fb0a494ac843856c78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375025"
---
# <a name="coledropsource-class"></a>COleDropSource クラス

データをドロップターゲットにドラッグできます。

## <a name="syntax"></a>構文

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ソースを指定します。](#coledropsource)|`COleDropSource` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ソース::ギブフィードバック](#givefeedback)|ドラッグ アンド ドロップ操作中にカーソルを変更します。|
|[ソース::オンビギドラ](#onbegindrag)|ドラッグ アンド ドロップ操作中にマウスキャプチャを処理します。|
|[ソース::クエリ継続ドラッグ](#querycontinuedrag)|ドラッグを続行するかどうかを確認します。|

## <a name="remarks"></a>解説

クラス[は](../../mfc/reference/coledroptarget-class.md)、ドラッグ アンド ドロップ操作の受信側部分を処理します。 オブジェクト`COleDropSource`は、ドラッグ操作の開始時期を決定し、ドラッグ操作中にフィードバックを提供し、ドラッグ操作がいつ終了したかの判断を行います。

オブジェクトを`COleDropSource`使用するには、コンストラクターを呼び出すだけです。 これにより、マウス クリックなどのイベントを決定するプロセスが簡単になり[、COleDataSource::DoDragDrop、COleDragDrop、:DoDragDrop、](../../mfc/reference/coledatasource-class.md#dodragdrop)または[COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop)関数を使用してドラッグ操作を開始します。 [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop) これらの関数はオブジェクトを`COleDropSource`作成します。 オーバーライド可能な関数の既定の動作を`COleDropSource`変更する場合があります。 これらのメンバー関数は、フレームワークによって適切な時間に呼び出されます。

OLE を使用したドラッグ アンド ドロップ操作の詳細については[、「OLE ドラッグ アンド ドロップ](../../mfc/drag-and-drop-ole.md)」を参照してください。

詳細については、Windows SDK[の「IDropSource」](/windows/win32/api/oleidl/nn-oleidl-idropsource)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxole.h

## <a name="coledropsourcecoledropsource"></a><a name="coledropsource"></a>ソースを指定します。

`COleDropSource` オブジェクトを構築します。

```
COleDropSource();
```

## <a name="coledropsourcegivefeedback"></a><a name="givefeedback"></a>ソース::ギブフィードバック

呼び出した後にフレームワークによって呼び出されます[::オンドラッグオーバー](../../mfc/reference/coledroptarget-class.md#ondragover)または[COleDropターゲット::Dラグエンター](../../mfc/reference/coledroptarget-class.md#ondragenter)。

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>パラメーター

*ドロップエフェクト*<br/>
ユーザーに表示する効果で、通常は選択したデータでこの時点でドロップが発生した場合の結果を示します。 通常、これは[CView:::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)または[CView::オンドラッグオーバー](../../mfc/reference/cview-class.md#ondragover)への最新の呼び出しによって返される値です。 次の 1 つ以上を指定できます。

- DROPEFFECT_NONE ドロップは許可されません。

- DROPEFFECT_COPY コピー操作が実行されます。

- DROPEFFECT_MOVE 移動操作が実行されます。

- DROPEFFECT_LINK ドロップされたデータから元のデータへのリンクが確立されます。

- DROPEFFECT_SCROLLドラッグスクロール操作が発生しようとしているか、ターゲットで実行されています。

### <a name="return-value"></a>戻り値

ドラッグが進行中の場合はDRAGDROP_S_USEDEFAULTCURSORSを返します。

### <a name="remarks"></a>解説

この時点でドロップが発生した場合に何が起こるかについてユーザーにフィードバックを提供するには、この関数をオーバーライドします。 既定の実装では、OLE の既定のカーソルが使用されます。 OLE を使用したドラッグ アンド ドロップ操作の詳細については[、「OLE ドラッグ アンド ドロップ](../../mfc/drag-and-drop-ole.md)」を参照してください。

詳細については[、「IDropSource::ギブフィードバック](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback)[、IDropTarget::Dラグオーバー](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover)、および[IDropTarget::Dラグエンター](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) 」を参照してください。

## <a name="coledropsourceonbegindrag"></a><a name="onbegindrag"></a>ソース::オンビギドラ

マウスの左ボタンを押すなどのドラッグ操作を開始する可能性のあるイベントが発生したときに、フレームワークによって呼び出されます。

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
選択したデータが含まれているウィンドウへのポイント。

### <a name="return-value"></a>戻り値

ドラッグが許可されている場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

ドラッグ処理の開始方法を変更する場合は、この関数をオーバーライドします。 既定の実装では、マウスをキャプチャし、ユーザーがマウスの左または右ボタンをクリックするか、Esc キーを押すまでドラッグ モードで、マウスを離す時間を取得します。

## <a name="coledropsourcequerycontinuedrag"></a><a name="querycontinuedrag"></a>ソース::クエリ継続ドラッグ

ドラッグが開始されると、この関数は、ドラッグ操作がキャンセルされるか完了するまで、フレームワークによって繰り返し呼び出されます。

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>パラメーター

*bエスケーププレス*<br/>
Esc キーが最後に呼び出されてから押されたかどうかを`COleDropSource::QueryContinueDrag`示します。

*州*<br/>
キーボードの修飾キーの状態を格納します。 これは、MK_CONTROL、MK_SHIFT、MK_ALT、MK_LBUTTON、MK_MBUTTON、およびMK_RBUTTONの任意の数の組み合わせです。

### <a name="return-value"></a>戻り値

DRAGDROP_S_CANCEL Esc キーまたは右ボタンを押した場合、または左ボタンが上げられた後にドラッグを開始する前に表示されます。 ドロップ操作が発生する必要があるかどうかをDRAGDROP_S_DROPします。 それ以外の場合はS_OK。

### <a name="remarks"></a>解説

ドラッグがキャンセルされたポイントまたはドロップが発生するポイントを変更する場合は、この関数をオーバーライドします。

デフォルトの実装では、ドロップを開始するか、次のようにドラッグをキャンセルします。 Esc キーまたはマウスの右ボタンを押すと、ドラッグ操作がキャンセルされます。 ドラッグを開始した後にマウスの左ボタンが上がると、ドロップ操作が開始されます。 それ以外の場合は、S_OKを返し、それ以上の操作は実行しません。

この関数は頻繁に呼び出されるため、できるだけ最適化する必要があります。

## <a name="see-also"></a>関連項目

[MFC サンプル ヒエルスヴル](../../overview/visual-cpp-samples.md)<br/>
[サンプル O クライアント](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
