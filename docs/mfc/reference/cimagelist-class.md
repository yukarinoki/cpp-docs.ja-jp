---
title: CImageList クラス
ms.date: 11/04/2016
f1_keywords:
- CImageList
- AFXCMN/CImageList
- AFXCMN/CImageList::CImageList
- AFXCMN/CImageList::Add
- AFXCMN/CImageList::Attach
- AFXCMN/CImageList::BeginDrag
- AFXCMN/CImageList::Copy
- AFXCMN/CImageList::Create
- AFXCMN/CImageList::DeleteImageList
- AFXCMN/CImageList::DeleteTempMap
- AFXCMN/CImageList::Detach
- AFXCMN/CImageList::DragEnter
- AFXCMN/CImageList::DragLeave
- AFXCMN/CImageList::DragMove
- AFXCMN/CImageList::DragShowNolock
- AFXCMN/CImageList::Draw
- AFXCMN/CImageList::DrawEx
- AFXCMN/CImageList::DrawIndirect
- AFXCMN/CImageList::EndDrag
- AFXCMN/CImageList::ExtractIcon
- AFXCMN/CImageList::FromHandle
- AFXCMN/CImageList::FromHandlePermanent
- AFXCMN/CImageList::GetBkColor
- AFXCMN/CImageList::GetDragImage
- AFXCMN/CImageList::GetImageCount
- AFXCMN/CImageList::GetImageInfo
- AFXCMN/CImageList::GetSafeHandle
- AFXCMN/CImageList::Read
- AFXCMN/CImageList::Remove
- AFXCMN/CImageList::Replace
- AFXCMN/CImageList::SetBkColor
- AFXCMN/CImageList::SetDragCursorImage
- AFXCMN/CImageList::SetImageCount
- AFXCMN/CImageList::SetOverlayImage
- AFXCMN/CImageList::Write
- AFXCMN/CImageList::m_hImageList
helpviewer_keywords:
- CImageList [MFC], CImageList
- CImageList [MFC], Add
- CImageList [MFC], Attach
- CImageList [MFC], BeginDrag
- CImageList [MFC], Copy
- CImageList [MFC], Create
- CImageList [MFC], DeleteImageList
- CImageList [MFC], DeleteTempMap
- CImageList [MFC], Detach
- CImageList [MFC], DragEnter
- CImageList [MFC], DragLeave
- CImageList [MFC], DragMove
- CImageList [MFC], DragShowNolock
- CImageList [MFC], Draw
- CImageList [MFC], DrawEx
- CImageList [MFC], DrawIndirect
- CImageList [MFC], EndDrag
- CImageList [MFC], ExtractIcon
- CImageList [MFC], FromHandle
- CImageList [MFC], FromHandlePermanent
- CImageList [MFC], GetBkColor
- CImageList [MFC], GetDragImage
- CImageList [MFC], GetImageCount
- CImageList [MFC], GetImageInfo
- CImageList [MFC], GetSafeHandle
- CImageList [MFC], Read
- CImageList [MFC], Remove
- CImageList [MFC], Replace
- CImageList [MFC], SetBkColor
- CImageList [MFC], SetDragCursorImage
- CImageList [MFC], SetImageCount
- CImageList [MFC], SetOverlayImage
- CImageList [MFC], Write
- CImageList [MFC], m_hImageList
ms.assetid: b6d1a704-1c82-4548-8a8f-77972adc98a5
ms.openlocfilehash: 2fc92858f84826e2b953fcbc9de020741e97b007
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346367"
---
# <a name="cimagelist-class"></a>CImageList クラス

Windows コモン イメージ リスト コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CImageList : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CImageList::CImageList](#cimagelist)|`CImageList` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CImageList::Add](#add)|イメージ リストに、イメージまたはイメージを追加します。|
|[CImageList::Attach](#attach)|イメージ リストのアタッチ、`CImageList`オブジェクト。|
|[CImageList::BeginDrag](#begindrag)|イメージのドラッグを開始します。|
|[CImageList::Copy](#copy)|内のイメージのコピーを`CImageList`オブジェクト。|
|[CImageList::Create](#create)|イメージ リストを初期化しにアタッチします、`CImageList`オブジェクト。|
|[CImageList::DeleteImageList](#deleteimagelist)|イメージ リストを削除します。|
|[CImageList::DeleteTempMap](#deletetempmap)|メソッドを呼び出して、 [CWinApp](../../mfc/reference/cwinapp-class.md)一時を削除するアイドル処理ハンドラー`CImageList`によって作成されたオブジェクト`FromHandle`します。|
|[CImageList::Detach](#detach)|イメージ リスト オブジェクトからのデタッチ、`CImageList`オブジェクトし、イメージ リストへのハンドルを返します。|
|[CImageList::DragEnter](#dragenter)|ドラッグ操作中に更新プログラムをロックし、指定した位置にドラッグ イメージを表示します。|
|[生じたとき](#dragleave)|ウィンドウのロックを解除し、ウィンドウを更新できるように、ドラッグ イメージを非表示にします。|
|[CImageList::DragMove](#dragmove)|ドラッグ アンド ドロップ操作中にドラッグされているイメージを移動します。|
|[CImageList::DragShowNolock](#dragshownolock)|表示とウィンドウをロックしないで、ドラッグ操作中のドラッグ イメージを非表示。|
|[:Draw](#draw)|ドラッグ アンド ドロップ操作中にドラッグされているイメージを描画します。|
|[CImageList::DrawEx](#drawex)|指定したデバイス コンテキストでは、イメージ リストのアイテムを描画します。 関数は、指定の描画スタイルを使用し、指定した色とイメージをブレンドします。|
|[CImageList::DrawIndirect](#drawindirect)|イメージの一覧からイメージを描画します。|
|[CImageList::EndDrag](#enddrag)|ドラッグ操作を終了します。|
|[CImageList::ExtractIcon](#extracticon)|アイコンのイメージとイメージ リスト内のマスクに基づいて作成します。|
|[CImageList::FromHandle](#fromhandle)|ポインターを返します、`CImageList`イメージ リストへのハンドルが指定されるとします。 `CImageList` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CImageList` オブジェクトが生成され、関連付けられます。|
|[CImageList::FromHandlePermanent](#fromhandlepermanent)|ポインターを返します、`CImageList`イメージ リストへのハンドルが指定されるとします。 場合、`CImageList`ハンドルには、オブジェクトはアタッチされていない、NULL が返されます。|
|[CImageList::GetBkColor](#getbkcolor)|イメージ リストの現在の背景色を取得します。|
|[CImageList::GetDragImage](#getdragimage)|ドラッグで使用する一時イメージ リストを取得します。|
|[CImageList::GetImageCount](#getimagecount)|イメージ リスト内のイメージの数を取得します。|
|[CImageList::GetImageInfo](#getimageinfo)|イメージに関する情報を取得します。|
|[CImageList::GetSafeHandle](#getsafehandle)|取得`m_hImageList`します。|
|[CImageList::Read](#read)|アーカイブからのイメージ リストを読み取ります。|
|[CImageList::Remove](#remove)|イメージ リストからイメージを削除します。|
|[CImageList::Replace](#replace)|イメージ リスト内のイメージを新しいイメージで置き換えます。|
|[CImageList::SetBkColor](#setbkcolor)|イメージ リストの背景色を設定します。|
|[CImageList::SetDragCursorImage](#setdragcursorimage)|新しいドラッグ イメージを作成します。|
|[CImageList::SetImageCount](#setimagecount)|イメージ リスト内のイメージの数をリセットします。|
|[CImageList::SetOverlayImage](#setoverlayimage)|オーバーレイ マスクとして使用するイメージの一覧にイメージの 0 から始まるインデックスを追加します。|
|[CImageList::Write](#write)|イメージ リストをアーカイブに書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CImageList::operator HIMAGELIST](#operator_himagelist)|アタッチされている返します、HIMAGELIST、`CImageList`します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CImageList::m_hImageList](#m_himagelist)|このオブジェクトにアタッチされているイメージ リストのハンドル。|

## <a name="remarks"></a>Remarks

「イメージ リスト」とは、それぞれの 0 から始まるインデックスを使用してを参照できます、同じサイズのイメージのコレクションです。 イメージ リストを使用して、アイコンまたはビットマップの大規模なセットを効率的に管理できます。 イメージ リストのすべてのイメージは、単一のワイド画面デバイス形式のビットマップに格納されます。 イメージ リストは、透過的にイメージを描画するために使用されるマスク (アイコンのスタイル) を含むモノクロ ビットマップを含めることもできます。 Microsoft Win32 アプリケーション プログラミング インターフェイス (API) を使用すると、イメージの描画、作成しイメージ リストを破棄、追加しイメージを削除する、イメージの置換、イメージのマージ、およびイメージのドラッグ イメージ リストの関数を提供します。

このコントロール (つまり、`CImageList`クラス) は以降、Windows 95/98 および Windows NT version 3.51 で実行するプログラムにのみ使用できます。

使用しての詳細については`CImageList`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CImageList](../../mfc/using-cimagelist.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="add"></a>  CImageList::Add

イメージ リストに 1 つまたは複数のイメージまたはアイコンを追加するには、この関数を呼び出します。

```
int Add(
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Add(
    CBitmap* pbmImage,
    COLORREF crMask);

int Add(HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*pbmImage*<br/>
イメージまたはイメージを含むビットマップへのポインター。 イメージの数は、ビットマップの幅から推論されます。

*pbmMask*<br/>
マスクを含むビットマップへのポインター。 イメージ リスト、マスクが使用されていない場合は、このパラメーターは無視されます。

*crMask*<br/>
マスクを生成するために使用する色です。 各ピクセルの指定したビットマップでは、この色が黒に変更され、マスク内の対応するビットがいずれかに設定します。

*hIcon*<br/>
ビットマップと、新しいイメージのマスクを含むアイコンのハンドル。

### <a name="return-value"></a>戻り値

成功した場合は、最初の新しいイメージの 0 から始まるインデックスそれ以外の場合 - 1。

### <a name="remarks"></a>Remarks

終了するときにアイコンのハンドルを解放するためにあります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

##  <a name="attach"></a>  CImageList::Attach

イメージ リストをアタッチするには、この関数を呼び出し、`CImageList`オブジェクト。

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>パラメーター

*hImageList*<br/>
イメージ リスト オブジェクトへのハンドル。

### <a name="return-value"></a>戻り値

添付ファイルが成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

##  <a name="begindrag"></a>  CImageList::BeginDrag

イメージのドラッグを開始するには、この関数を呼び出します。

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
ドラッグするイメージの 0 から始まるインデックス。

*ptHotSpot*<br/>
ドラッグの開始位置 (通常は、カーソルの位置) の座標。 座標は、イメージの左上隅を基準としました。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

この関数は、ドラッグすることに使用される一時イメージ リストを作成します。 イメージは、現在のカーソルに指定したイメージとマスクを結合します。 後続の WM_MOUSEMOVE メッセージに応答してを使用してドラッグ イメージを移動できる、`DragMove`メンバー関数。 ドラッグ操作の終了を使用することができます、`EndDrag`メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

##  <a name="cimagelist"></a>  CImageList::CImageList

`CImageList` オブジェクトを構築します。

```
CImageList();
```

##  <a name="copy"></a>  CImageList::Copy

このメンバー関数は、Win32 関数の動作を実装[ImageList_Copy](/windows/desktop/api/commctrl/nf-commctrl-imagelist_copy)」の説明に従って、Windows SDK。

```
BOOL Copy(
    int iDst,
    int iSrc,
    UINT uFlags = ILCF_MOVE);

BOOL Copy(
    int iDst,
    CImageList* pSrc,
    int iSrc,
    UINT uFlags = ILCF_MOVE);
```

### <a name="parameters"></a>パラメーター

*iDst*<br/>
コピー操作のコピー先として使用するイメージの 0 から始まるインデックス。

*iSrc*<br/>
コピー操作のソースとして使用するイメージの 0 から始まるインデックス。

*uFlags*<br/>
ビット フラグの値にするコピー操作の種類を指定します。 このパラメーターには、次の値のいずれかを指定できます。

|[値]|説明|
|-----------|-------------|
|ILCF_MOVE|ソース イメージは、描画するイメージのインデックスにコピーされます。 この操作は、特定のイメージの複数のインスタンスの結果します。 ILCF_MOVE では、既定値です。|
|ILCF_SWAP|ソースとコピー先のイメージのイメージ リスト内の位置を交換します。|

*pSrc*<br/>
ポインター、`CImageList`コピー操作の対象となっているオブジェクト。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

##  <a name="create"></a>  CImageList::Create

イメージ リストを初期化しにアタッチします、 [CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。

```
BOOL Create(
    int cx,
    int cy,
    UINT nFlags,
    int nInitial,
    int nGrow);

BOOL Create(
    UINT nBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    LPCTSTR lpszBitmapID,
    int cx,
    int nGrow,
    COLORREF crMask);

BOOL Create(
    CImageList& imagelist1,
    int nImage1,
    CImageList& imagelist2,
    int nImage2,
    int dx,
    int dy);

BOOL Create(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*cx*<br/>
各イメージには、ピクセルのサイズ。

*cy*<br/>
各イメージには、ピクセルのサイズ。

*nFlags*<br/>
作成するイメージ リストの種類を指定します。 このパラメーターは、次の値の組み合わせを指定できますが、1 つだけ含めることができます、`ILC_COLOR`値。

|[値]|説明|
|-----------|-------------|
|ILC_COLOR|指定されていない他の組み合わせて指定 * フラグの場合は、既定の動作を使用します。 通常、既定では ILC_COLOR4;以前のディスプレイ ドライバーでは、既定値は ILC_COLORDDB します。|
|ILC_COLOR4|イメージの一覧については、ビットマップとして 4 ビット (16 色) のデバイスに依存しないビットマップ (DIB) セクションを使用します。|
|ILC_COLOR8|8 ビット DIB のセクションを使用します。 カラー テーブルに使用される色は、ハーフトーン パレットの色と同じです。|
|ILC_COLOR16|16 ビット (32/64 k の色) DIB セクション。|
|ILC_COLOR24|24 ビット DIB セクションを使用します。|
|ILC_COLOR32|32 ビットの DIB セクションを使用します。|
|ILC_COLORDDB|デバイス依存ビットマップを使用します。|
|ILC_MASK|マスクを使用します。 イメージ リストには、マスクとして使用されるモノクロ ビットマップは、その 1 つ、2 つのビットマップが含まれています。 この値が含まれない場合、イメージ リストには、1 つだけのビットマップが含まれています。 参照してください[イメージの一覧からイメージを描画](../../mfc/drawing-images-from-an-image-list.md)マスクされたイメージの詳細についてはします。|

*nInitial*<br/>
最初にイメージのリストを含むイメージの数。

*nGrow*<br/>
イメージ リストのシステムは、新しいイメージを格納するためにリストのサイズを変更する必要があるときに拡張可能イメージの数。 このパラメーターは、イメージのサイズを変更したリストに含めることができます、新しいイメージの数を表します。

*nBitmapID*<br/>
イメージ リストに関連するビットマップのリソース Id。

*crMask*<br/>
マスクの生成に使用される色。 指定したビットマップでは、この色の各ピクセルは黒に変更し、マスク内の対応するビットがいずれかに設定します。

*lpszBitmapID*<br/>
イメージのリソース Id を含む文字列。

*imagelist1*<br/>
`CImageList` オブジェクトへの参照。

*nImage1*<br/>
最初の既存のイメージのインデックス。

*imagelist2*<br/>
`CImageList` オブジェクトへの参照。

*nImage2*<br/>
2 つ目の既存のイメージのインデックス。

*dx*<br/>
最初のイメージには、ピクセルの関係における 2 番目の画像の x 軸のオフセットします。

*dy*<br/>
最初のイメージには、ピクセルの関係における 2 番目の画像の y 軸のオフセットします。

*pImageList*<br/>
`CImageList` オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

構築する、`CImageList`で 2 つの手順。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、イメージ リストを作成しにアタッチする`CImageList`オブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

##  <a name="deleteimagelist"></a>  CImageList::DeleteImageList

イメージ リストを削除するには、この関数を呼び出します。

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

##  <a name="deletetempmap"></a>  CImageList::DeleteTempMap

によって自動的に呼び出されます、`CWinApp`アイドル処理ハンドラー、`DeleteTempMap`削除一時`CImageList`によって作成されたオブジェクト[FromHandle](#fromhandle)がすべてのハンドルを破棄しません ( `hImageList`) 一時的に関連付けられています。`ImageList`オブジェクト。

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

##  <a name="detach"></a>  CImageList::Detach

イメージ リスト オブジェクトをデタッチするには、この関数を呼び出し、`CImageList`オブジェクト。

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>戻り値

イメージ リスト オブジェクトへのハンドル。

### <a name="remarks"></a>Remarks

この関数は、イメージ リスト オブジェクトを識別するハンドルを返します。

### <a name="example"></a>例

  例をご覧ください[CImageList::Attach](#attach)します。

##  <a name="dragenter"></a>  CImageList::DragEnter

ドラッグ操作中にロック更新で指定されたウィンドウを*pWndLock*で指定した位置にドラッグ イメージを表示します。*ポイント*します。

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*pWndLock*<br/>
ドラッグ イメージを所有しているウィンドウへのポインター。

*ポイント*<br/>
ドラッグ イメージを表示する位置。 (クライアント領域ではなく) ウィンドウの左上隅に対する相対座標とは。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

座標は、座標を指定するときに、境界線、タイトル バー、メニュー バーなどのウィンドウの要素の幅を補正する必要がありますので、ウィンドウの左上隅を基準としました。

場合*pWndLock*が NULL で、この関数は、デスクトップのウィンドウに関連付けられている表示コンテキストでイメージを描画、座標は画面の左上隅を基準とします。

この関数は、ドラッグ操作中に指定されたウィンドウにその他のすべての更新プログラムをロックします。 使用して、ドラッグしたイメージを一時的に非、ドラッグ アンド ドロップ操作のターゲットを強調表示などのドラッグ操作中に描画を実行する必要がある場合、[生じたとき](#dragleave)関数。

### <a name="example"></a>例

  例をご覧ください[CImageList::BeginDrag](#begindrag)します。

##  <a name="dragleave"></a>  生じたとき

指定されたウィンドウのロックを解除*pWndLock*し、ドラッグ イメージを更新するウィンドウを非表示にします。

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>パラメーター

*pWndLock*<br/>
ドラッグ イメージを所有しているウィンドウへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CImageList::EndDrag](#enddrag)します。

##  <a name="dragmove"></a>  CImageList::DragMove

ドラッグ アンド ドロップ操作中にドラッグされているイメージを移動するには、この関数を呼び出します。

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
新しい位置にドラッグします。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

この関数は通常 WM_MOUSEMOVE メッセージへの応答で呼び出されます。 ドラッグ操作を開始するには、使用、`BeginDrag`メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

##  <a name="dragshownolock"></a>  CImageList::DragShowNolock

表示とウィンドウをロックしないで、ドラッグ操作中のドラッグ イメージを非表示。

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bShow*<br/>
ドラッグ イメージを表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

[CImageList::DragEnter](#dragenter)関数は、ドラッグ操作中に、ウィンドウにすべての更新プログラムをロックします。 ただし、この関数では、ウィンドウはロックされません。

##  <a name="draw"></a>  :Draw

ドラッグ アンド ドロップ操作中にドラッグされているイメージを描画するには、この関数を呼び出します。

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コピー先のデバイス コンテキストへのポインター。

*nImage*<br/>
描画するイメージの 0 から始まるインデックス。

*pt*<br/>
指定したデバイス コンテキスト内で描画する場所です。

*nStyle*<br/>
描画スタイルを指定するフラグ。 これらの値の 1 つ以上を指定できます。

|[値]|説明|
|-----------|-------------|
|ILD_BLEND25、ILD_FOCUS|システムの強調表示色を 25% を混合して、イメージを描画します。 イメージ リストには、マスクが含まれていない場合は、この値を指定しても効果はありません。|
|ILD_BLEND50, ILD_SELECTED, ILD_BLEND|システムの強調表示色を 50% を混合して、イメージを描画します。 イメージ リストには、マスクが含まれていない場合は、この値を指定しても効果はありません。|
|ILD_MASK|マスクを描画します。|
|に|イメージ リストの背景色を使用してイメージを描画します。 しますの背景色は、透過的にマスクを使用して、イメージが描画されます。|
|ILD_TRANSPARENT|透過的に背景色に関係なく、マスクを使用してイメージを描画します。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CImageList::SetOverlayImage](#setoverlayimage)します。

##  <a name="drawex"></a>  CImageList::DrawEx

指定したデバイス コンテキストでは、イメージ リストのアイテムを描画します。

```
BOOL DrawEx(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    COLORREF clrBk,
    COLORREF clrFg,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
コピー先のデバイス コンテキストへのポインター。

*nImage*<br/>
描画するイメージの 0 から始まるインデックス。

*pt*<br/>
指定したデバイス コンテキスト内で描画する場所です。

*sz*<br/>
イメージの左上隅に対して相対的に描画するイメージの部分のサイズ。 参照してください*dx*と*dy*で[ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK に含まれています。

*clrBk*<br/>
イメージの背景色です。 参照してください*rgbBk*で[ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK に含まれています。

*clrFg*<br/>
イメージの前景色。 参照してください*rgbFg*で[ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK に含まれています。

*nStyle*<br/>
描画スタイルを指定するフラグ。 参照してください*は*で[ImageList_DrawEx](/windows/desktop/api/commctrl/nf-commctrl-imagelist_drawex) Windows SDK に含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

関数は、指定の描画スタイルを使用し、指定した色とイメージをブレンドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

##  <a name="drawindirect"></a>  CImageList::DrawIndirect

イメージの一覧からイメージを描画するには、このメンバー関数を呼び出します。

```
BOOL DrawIndirect(IMAGELISTDRAWPARAMS* pimldp);

BOOL DrawIndirect(
    CDC* pDC,
    int nImage,
    POINT pt,
    SIZE sz,
    POINT ptOrigin,
    UINT fStyle = ILD_NORMAL,
    DWORD dwRop = SRCCOPY,
    COLORREF rgbBack = CLR_DEFAULT,
    COLORREF rgbFore = CLR_DEFAULT,
    DWORD fState = ILS_NORMAL,
    DWORD Frame = 0,
    COLORREF crEffect = CLR_DEFAULT);
```

### <a name="parameters"></a>パラメーター

*pimldp*<br/>
ポインター、[された](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams)描画操作に関する情報を含む構造体。

*pDC*<br/>
コピー先のデバイス コンテキストへのポインター。 これを削除する必要があります[CDC](../../mfc/reference/cdc-class.md)でそれが済んだらオブジェクトします。

*nImage*<br/>
描画するイメージの 0 から始まるインデックス。

*pt*<br/>
A[ポイント](/previous-versions/dd162805\(v=vs.85\))イメージを描画する x 座標と y 座標を含む構造体。

*sz*<br/>
A[サイズ](/windows/desktop/api/windef/ns-windef-tagsize)構造体を描画するイメージのサイズを示します。

*ptOrigin*<br/>
A[ポイント](/previous-versions/dd162805\(v=vs.85\))イメージ自体に関して描画操作の左上隅を指定する x 座標と y 座標を含む構造体。 左側の x 座標と y 座標の上にある画像のピクセルは描画されません。

*fStyle*<br/>
描画スタイルと、必要に応じて、オーバーレイのイメージを指定するフラグ。 オーバーレイ画像では、「解説」を参照してください。 MFC の既定の実装に、イメージ リストの背景色を使用してイメージを描画します。 しますの背景色は、透過的にマスクを使用して、イメージが描画されます。

可能なその他のスタイルは、「、*は*のメンバー、[された](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams)構造体。

*dwRop*<br/>
ラスター オペレーション コードを指定する値。 これらのコードでは、最終的な色を実現するために、移行先の四角形の色データのソースの四角形に対するカラー データの結合方法を定義します。 SRCCOPY、MFC の既定の実装では、先の四角形に直接ソースの四角形をコピーします。 場合、このパラメーターは無視されます、*は*ILD_ROP フラグにパラメーターは含まれません。

その他の使用可能な値は、「、 *dwRop*のメンバー、[された](/windows/desktop/api/commctrl/ns-commctrl-_imagelistdrawparams)構造体。

*rgbBack*<br/>
イメージ背景の色、既定ではときです。 このパラメーターには、アプリケーション定義の RGB 値または値は次のいずれかを指定できます。

|[値]|説明|
|-----------|-------------|
|とき|既定の背景色。 イメージ リストの背景色を使用して、イメージが描画されます。|
|CLR_NONE|背景色がありません。 イメージが透過的に描画します。|

*rgbFore*<br/>
イメージときの既定で初期化します。 このパラメーターには、アプリケーション定義の RGB 値または値は次のいずれかを指定できます。

|[値]|説明|
|-----------|-------------|
|とき|既定の前景の色。 イメージは、システムの強調表示色を使用して、前景の色として描画されます。|
|CLR_NONE|Blend の色はなし。 イメージは、コピー先デバイス コンテキストの色とブレンドされます。|

場合にのみ、このパラメーターが使用される*は*ILD_BLEND25 または ILD_BLEND50 フラグが含まれています。

*fState*<br/>
描画の状態を指定するフラグ。 このメンバーは、1 つまたは複数のイメージ リストの状態フラグを含めることができます。

*Frame*<br/>
飽和とアルファ ブレンド効果の動作に影響します。

Ils_saturate 使用して、このメンバーは、アイコン内の各ピクセルの RGB トリプレットの各色コンポーネントに追加される値を保持します。

Ils_aplha 使用して、このメンバーは、アルファ チャネルの値を保持します。 この値は、255 0 が完全に透明、255 は完全に不透明の 0 から指定できます。

*crEffect*<br/>
A [COLORREF](/windows/desktop/gdi/colorref)光彩とシャドウ効果に使用される値。

### <a name="return-value"></a>戻り値

イメージが描画できた場合は TRUE。それ以外の場合は FALSE です。

### <a name="remarks"></a>Remarks

自分で Win32 構造体を格納する場合は、最初のバージョンを使用します。 MFC の既定の引数の 1 つ以上の利用、または構造の管理を回避したい場合は、2 番目のバージョンを使用します。

オーバーレイ イメージでは、このメンバー関数で指定された、プライマリのイメージの上に描画されるイメージとは、*あり*パラメーター。 使用してオーバーレイ マスクを描画、[描画](#draw)、オーバーレイのマスクを使用して指定の 1 から始まるインデックスを持つメンバー関数、[から](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask)マクロ。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

##  <a name="enddrag"></a>  CImageList::EndDrag

ドラッグ操作を終了するには、この関数を呼び出します。

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>Remarks

ドラッグ操作を開始するには、使用、`BeginDrag`メンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

##  <a name="extracticon"></a>  CImageList::ExtractIcon

イメージとイメージ リストに関連するマスクに基づいてアイコンを作成するには、この関数を呼び出します。

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
イメージの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

成功した場合は、アイコンのハンドルそれ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

このメソッドは、の動作に依存、 [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon)マクロをアイコンを作成します。 参照してください、 [ImageList_ExtractIcon](/windows/desktop/api/commctrl/nf-commctrl-imagelist_extracticon)アイコンの作成とクリーンアップの詳細についてはマクロです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

##  <a name="fromhandle"></a>  CImageList::FromHandle

ポインターを返します、`CImageList`イメージ リストへのハンドルが指定されるとします。

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>パラメーター

*hImageList*<br/>
イメージ リストを指定します。

### <a name="return-value"></a>戻り値

ポインター、`CImageList`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks

場合、`CImageList`ハンドル、一時的に既にアタッチされていない`CImageList`オブジェクトを作成し、接続されています。 この一時`CImageList`のみがある終わるまで、次回アプリケーション アイドル イベント ループで、どの時点ですべての一時オブジェクトは削除、オブジェクトが無効です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

##  <a name="fromhandlepermanent"></a>  CImageList::FromHandlePermanent

ポインターを返します、`CImageList`イメージ リストへのハンドルが指定されるとします。

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>パラメーター

*hImageList*<br/>
イメージ リストを指定します。

### <a name="return-value"></a>戻り値

ポインター、`CImageList`成功。 それ以外の場合に NULL の場合は、オブジェクト。

### <a name="remarks"></a>Remarks

場合、`CImageList`ハンドルには、オブジェクトはアタッチされていない、NULL が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

##  <a name="getbkcolor"></a>  CImageList::GetBkColor

イメージ リストの現在の背景色を取得するには、この関数を呼び出します。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

RGB カラー値、`CImageList`オブジェクトの背景色。

### <a name="example"></a>例

  例をご覧ください[CImageList::SetBkColor](#setbkcolor)します。

##  <a name="getdragimage"></a>  CImageList::GetDragImage

ドラッグで使用する一時イメージ リストを取得します。

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>パラメーター

*lpPoint*<br/>
アドレスを[ポイント](/previous-versions/dd162805\(v=vs.85\))受け取る現在位置にドラッグします。

*lpPointHotSpot*<br/>
アドレスを`POINT`ドラッグ位置を基準としてドラッグ イメージのオフセットを受け取る。

### <a name="return-value"></a>戻り値

かどうかは成功すると、一時的なイメージへのポインターを一覧表示する; をドラッグするために使用それ以外の場合は NULL です。

##  <a name="getimagecount"></a>  CImageList::GetImageCount

イメージ リスト内のイメージの数を取得するには、この関数を呼び出します。

```
int GetImageCount() const;
```

### <a name="return-value"></a>戻り値

イメージの数。

### <a name="example"></a>例

  例をご覧ください[CImageList::ExtractIcon](#extracticon)します。

##  <a name="getimageinfo"></a>  CImageList::GetImageInfo

イメージに関する情報を取得するには、この関数を呼び出します。

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
イメージの 0 から始まるインデックス。

*pImageInfo*<br/>
ポインター、 [IMAGEINFO](/windows/desktop/api/commctrl/ns-commctrl-_imageinfo)イメージに関する情報を受け取る構造体。 イメージのビットマップを直接操作は、この構造体の情報を使用できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

`IMAGEINFO`構造体には、イメージ リスト内のイメージに関する情報が含まれています。

##  <a name="getsafehandle"></a>  CImageList::GetSafeHandle

取得するには、この関数を呼び出し、`m_hImageList`データ メンバー。

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>戻り値

添付された画像リストへのハンドルオブジェクトがアタッチされていない場合は NULL それ以外の場合です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

##  <a name="m_himagelist"></a>  CImageList::m_hImageList

このオブジェクトにアタッチされているイメージ リストのハンドル。

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>Remarks

`m_hImageList`データ メンバーが型 HIMAGELIST のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

##  <a name="operator_himagelist"></a>  CImageList::operator HIMAGELIST

この演算子を使用して、添付のハンドルを取得する、`CImageList`オブジェクト。

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>戻り値

かどうかは成功すると、イメージ リストを識別するハンドルで表される、`CImageList`オブジェクト。 それ以外の場合は NULL です。

### <a name="remarks"></a>Remarks

この演算子は、キャスト演算子です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

##  <a name="read"></a>  CImageList::Read

アーカイブからのイメージ リストを読み取るには、この関数を呼び出します。

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>パラメーター

*pArchive*<br/>
ポインターを`CArchive`イメージ リストを読み取るの元のオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

##  <a name="remove"></a>  CImageList::Remove

イメージ リスト オブジェクトからイメージを削除するには、この関数を呼び出します。

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
削除するイメージの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

次のすべての項目*あり*現在位置を 1 つ下へ移動します。 たとえば、イメージ リストに 2 つの項目が含まれている場合の最初の項目を削除によりを今すぐ最初の位置で残りの項目。 *あり*の最初の位置の項目の 0 を = です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

##  <a name="replace"></a>  CImageList::Replace

この関数では、イメージ リスト内のイメージを新しいイメージで置き換えます。

```
BOOL Replace(
    int nImage,
    CBitmap* pbmImage,
    CBitmap* pbmMask);

int Replace(
    int nImage,
    HICON hIcon);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
置換するイメージの 0 から始まるインデックス。

*pbmImage*<br/>
イメージを含むビットマップへのポインター。

*pbmMask*<br/>
マスクを含むビットマップへのポインター。 イメージ リスト、マスクが使用されていない場合は、このパラメーターは無視されます。

*hIcon*<br/>
ビットマップと、新しいイメージのマスクを含むアイコンへのハンドル。

### <a name="return-value"></a>戻り値

ブール値を返すバージョンが成功した場合、0 以外の値を返しますそれ以外の場合 0 を返します。

返すバージョン**int**成功した場合は、イメージの 0 から始まるインデックスを返します 1。

### <a name="remarks"></a>Remarks

このメンバー関数を呼び出した後に呼び出す[呼び出す前](#setimagecount)プレース ホルダーを有効なイメージを新しいに割り当てるには、するには、イメージのインデックス番号。

### <a name="example"></a>例

  例をご覧ください[CImageList::SetImageCount](#setimagecount)します。

##  <a name="setbkcolor"></a>  CImageList::SetBkColor

イメージ リストの背景色を設定するには、この関数を呼び出します。

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>パラメーター

*cr*<br/>
背景色を設定します。 CLR_NONE になります。 その場合は、イメージは、透過的にマスクを使用して描画されます。

### <a name="return-value"></a>戻り値

成功した場合、前の背景色それ以外の場合 CLR_NONE します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

##  <a name="setdragcursorimage"></a>  CImageList::SetDragCursorImage

現在のドラッグ イメージと指定したイメージ (通常はマウス カーソル イメージ) を組み合わせることによって新しいドラッグ イメージを作成します。

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>パラメーター

*nDrag*<br/>
ドラッグ イメージと結合する新しいイメージのインデックス。

*ptHotSpot*<br/>
新しいイメージ内のホット スポットの位置。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ドラッグの関数は、ドラッグ操作中に、新しいイメージを使用するため、Windows を使用する必要があります[ShowCursor](/windows/desktop/api/winuser/nf-winuser-showcursor)関数を呼び出した後、実際のマウス カーソルを非表示に`CImageList::SetDragCursorImage`します。 それ以外の場合、システムがドラッグ操作中にマウス カーソルが 2 つあります。

##  <a name="setimagecount"></a>  CImageList::SetImageCount

内のイメージの番号をリセットするには、このメンバー関数を呼び出す、`CImageList`オブジェクト。

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>パラメーター

*uNewCount*<br/>
イメージ リストのイメージの新しいの合計数を指定する値。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

イメージ リストのイメージの数を増やすには、このメンバー関数を呼び出す場合、呼び出す[置換](#replace)の有効なイメージに新しいインデックスを割り当てる各追加のイメージ。 有効なイメージに、インデックスの割り当てに失敗した場合は、新しいイメージを作成する描画操作は予測できません。

イメージ リストのサイズを小さくには、この関数を使用して、切り捨てられたイメージが解放されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

##  <a name="setoverlayimage"></a>  CImageList::SetOverlayImage

オーバーレイ マスクとして使用するイメージの一覧にイメージの 0 から始まるインデックスを追加するには、この関数を呼び出します。

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>パラメーター

*nImage*<br/>
オーバーレイ マスクとして使用するイメージの 0 から始まるインデックス。

*nOverlay*<br/>
オーバーレイのマスクの 1 から始まるインデックス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

一覧には、最大で 4 つのインデックスを追加できます。

オーバーレイ マスクは、別のイメージの上に透過的に描画されるイメージです。 使用してイメージ上のオーバーレイ マスクを描画、 [:draw](#draw)からマクロを使用して、指定されたオーバーレイ マスクの 1 から始まるインデックスを持つメンバー関数。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

##  <a name="write"></a>  CImageList::Write

アーカイブをイメージ リスト オブジェクトを記述するには、この関数を呼び出します。

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>パラメーター

*pArchive*<br/>
ポインターを`CArchive`イメージ リストが格納されるオブジェクト。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>関連項目

[CObject クラス](../../mfc/reference/cobject-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)<br/>
[CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)
