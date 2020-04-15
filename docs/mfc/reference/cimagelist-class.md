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
ms.openlocfilehash: eff2d0c1de88ebd9d949ebe197563c87c17e5b05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372446"
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
|[次のリストを使用します。](#cimagelist)|`CImageList` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を追加します。](#add)|イメージリストにイメージを追加します。|
|[Cイメージリスト::アタッチ](#attach)|イメージ リストをオブジェクトに`CImageList`アタッチします。|
|[::開始ドラッグ](#begindrag)|イメージのドラッグを開始します。|
|[Cイメージリスト::コピー](#copy)|オブジェクト内のイメージを`CImageList`コピーします。|
|[作成](#create)|イメージ リストを初期化し、`CImageList`オブジェクトにアタッチします。|
|[イメージリスト::D](#deleteimagelist)|イメージ リストを削除します。|
|[一覧::D一覧](#deletetempmap)|によって作成された一時`CImageList`オブジェクトを削除するために[CWinApp](../../mfc/reference/cwinapp-class.md)アイドルタイム`FromHandle`ハンドラによって呼び出されます。|
|[イメージリスト::Dエタッハ](#detach)|イメージ リスト オブジェクトを`CImageList`オブジェクトからデタッチし、イメージ リストへのハンドルを返します。|
|[次のリストを:Dラージ](#dragenter)|ドラッグ操作中に更新をロックし、指定した位置にドラッグイメージを表示します。|
|[イメージリスト::Dラグリーブ](#dragleave)|ウィンドウのロックを解除し、ドラッグイメージを非表示にして、ウィンドウを更新できるようにします。|
|[イメージリスト::Dラグムーブ](#dragmove)|ドラッグ アンド ドロップ操作中にドラッグされているイメージを移動します。|
|[Cイメージリスト::Dラグショーノロック](#dragshownolock)|ドラッグ操作中に、ウィンドウをロックせずにドラッグ イメージの表示と非表示を切り替えます。|
|[イメージリスト::Dロー](#draw)|ドラッグ アンド ドロップ操作中にドラッグされるイメージを描画します。|
|[イメージリスト::Dローエックス](#drawex)|指定したデバイス コンテキストでイメージ リスト項目を描画します。 この関数は、指定した描画スタイルを使用し、指定した色でイメージをブレンドします。|
|[イメージリスト::Dローインダイレクト](#drawindirect)|イメージ リストからイメージを描画します。|
|[::エンドドラッグ](#enddrag)|ドラッグ操作を終了します。|
|[Cイメージリスト::抽出アイコン](#extracticon)|イメージ リスト内のイメージとマスクに基づいてアイコンを作成します。|
|[を使用します。](#fromhandle)|イメージ リストへのハンドル`CImageList`が与えられた場合、オブジェクトへのポインターを返します。 `CImageList` オブジェクトがハンドルに関連付けられていない場合は、一時的な `CImageList` オブジェクトが生成され、関連付けられます。|
|[を使用する](#fromhandlepermanent)|イメージ リストへのハンドル`CImageList`が与えられた場合、オブジェクトへのポインターを返します。 オブジェクトが`CImageList`ハンドルにアタッチされていない場合は、NULL が返されます。|
|[イメージリスト::ゲットブレクカラー](#getbkcolor)|イメージ リストの現在の背景色を取得します。|
|[イメージリスト::取得ドラッグイメージ](#getdragimage)|ドラッグに使用される一時的なイメージ リストを取得します。|
|[を使用します。](#getimagecount)|イメージ リスト内のイメージの数を取得します。|
|[を使用します。](#getimageinfo)|イメージに関する情報を取得します。|
|[を使用します。](#getsafehandle)|を取得`m_hImageList`します。|
|[イメージリスト::読み取り](#read)|アーカイブからイメージ リストを読み取ります。|
|[イメージリスト::削除](#remove)|イメージリストからイメージを削除します。|
|[置き換え](#replace)|イメージ リスト内のイメージを新しいイメージに置き換えます。|
|[一覧::セットBkカラー](#setbkcolor)|イメージ リストの背景色を設定します。|
|[イメージリスト::セットドラッグカーソルイメージ](#setdragcursorimage)|新しいドラッグ イメージを作成します。|
|[を使用します。](#setimagecount)|イメージ リスト内のイメージの数をリセットします。|
|[イメージリスト::イメージを設定します。](#setoverlayimage)|オーバーレイ マスクとして使用するイメージの一覧に、イメージの 0 から始まるインデックスを追加します。|
|[書き込み](#write)|イメージ リストをアーカイブに書き込みます。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[イメージリスト::オペレーター・ヒマージュリスト](#operator_himagelist)|にアタッチされている HIMAGELIST`CImageList`を返します。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[イメージリスト::m_hImageList](#m_himagelist)|このオブジェクトにアタッチされたイメージ リストを含むハンドル。|

## <a name="remarks"></a>解説

"イメージ リスト" は同じサイズのイメージのコレクションで、各イメージは 0 から始まるインデックスで参照できます。 イメージ リストは、大きなアイコンやビットマップのセットを効率的に管理するために使用されます。 イメージ リスト内のすべてのイメージは、画面デバイス形式の単一のワイド ビットマップに含まれています。 イメージ リストには、イメージを透明に描画するために使用されるマスク (アイコン スタイル) を含むモノクロ ビットマップも含まれます。 Microsoft Win32 アプリケーション プログラミング インターフェイス (API) は、イメージの描画、イメージ リストの作成と破棄、イメージの追加と削除、イメージの置換、イメージのマージ、およびドラッグイメージのドラッグを可能にするイメージ リスト関数を提供します。

このコントロール (および`CImageList`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

の使用方法`CImageList`の詳細については、「[コントロール](../../mfc/controls-mfc.md)」および[「CImageList を使用する](../../mfc/using-cimagelist.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CImageList`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cimagelistadd"></a><a name="add"></a>次の項目を追加します。

1 つ以上のイメージまたはアイコンをイメージ リストに追加します。

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

*イメージ*<br/>
イメージを含むビットマップへのポインター。 ビットマップの幅からイメージの数が推測されます。

*pbmマスク*<br/>
マスクを含むビットマップへのポインター。 イメージ リストでマスクを使用しない場合、このパラメーターは無視されます。

*クマスク*<br/>
マスクの生成に使用される色。 指定されたビットマップのこの色の各ピクセルは黒に変更され、マスク内の対応するビットは 1 に設定されます。

*Hicon*<br/>
新しいイメージのビットマップとマスクを含むアイコンのハンドル。

### <a name="return-value"></a>戻り値

成功した場合は、最初の新しいイメージの 0 から始まるインデックス。それ以外の場合 - 1。

### <a name="remarks"></a>解説

アイコン ハンドルを解放する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#1](../../mfc/reference/codesnippet/cpp/cimagelist-class_1.cpp)]

## <a name="cimagelistattach"></a><a name="attach"></a>Cイメージリスト::アタッチ

`CImageList`オブジェクトにイメージ リストをアタッチします。

```
BOOL Attach(HIMAGELIST hImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
イメージ リスト オブジェクトへのハンドル。

### <a name="return-value"></a>戻り値

添付ファイルが正常に終了した場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#2](../../mfc/reference/codesnippet/cpp/cimagelist-class_2.cpp)]

## <a name="cimagelistbegindrag"></a><a name="begindrag"></a>::開始ドラッグ

イメージのドラッグを開始します。

```
BOOL BeginDrag(
    int nImage,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>パラメーター

*nイメージ*<br/>
ドラッグするイメージの 0 から始まるインデックス。

*プットホットスポット*<br/>
開始ドラッグ位置の座標 (通常はカーソル位置)。 座標は、イメージの左上隅を基準にしています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、ドラッグに使用される一時イメージ リストを作成します。 イメージは、指定されたイメージとそのマスクを現在のカーソルと結合します。 後続のWM_MOUSEMOVE メッセージに応答して、メンバー関数を使用してドラッグ`DragMove`イメージを移動できます。 ドラッグ操作を終了するには、メンバー関数を`EndDrag`使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#3](../../mfc/reference/codesnippet/cpp/cimagelist-class_3.cpp)]

## <a name="cimagelistcimagelist"></a><a name="cimagelist"></a>次のリストを使用します。

`CImageList` オブジェクトを構築します。

```
CImageList();
```

## <a name="cimagelistcopy"></a><a name="copy"></a>Cイメージリスト::コピー

このメンバー関数は、Windows SDK で説明されているように、関数[ImageList_Copy](/windows/win32/api/commctrl/nf-commctrl-imagelist_copy)Win32 の動作を実装します。

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
コピー操作のコピー先として使用されるイメージの 0 から始まるインデックス。

*Isrc*<br/>
コピー操作のソースとして使用されるイメージの 0 から始まるインデックス。

*uフラグ*<br/>
作成するコピー操作の種類を指定するビット フラグ値。 このパラメーターには、次のいずれかの値を指定できます。

|[値]|意味|
|-----------|-------------|
|ILCF_MOVE|ソース イメージがコピー先イメージのインデックスにコピーされます。 この操作により、特定のイメージの複数のインスタンスが作成されます。 ILCF_MOVEがデフォルトです。|
|ILCF_SWAP|ソース イメージとターゲット イメージは、イメージ リスト内の位置を交換します。|

*pSrc*<br/>
コピー操作の`CImageList`ターゲットであるオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#6](../../mfc/reference/codesnippet/cpp/cimagelist-class_4.cpp)]

## <a name="cimagelistcreate"></a><a name="create"></a>作成

イメージ リストを初期化し[、CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトにアタッチします。

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

*Cx*<br/>
各画像のサイズ (ピクセル単位)。

*Cy*<br/>
各画像のサイズ (ピクセル単位)。

*Nflags*<br/>
作成するイメージ リストの種類を指定します。 このパラメーターは、次の値の組み合わせでも使用できますが、値の`ILC_COLOR`1 つだけを含めることができます。

|[値]|意味|
|-----------|-------------|
|ILC_COLOR|他の ILC_COLOR* フラグが指定されていない場合は、デフォルトの動作を使用します。 通常、デフォルトはILC_COLOR4です。ただし、古いディスプレイ ドライバの場合、デフォルトはILC_COLORDDBです。|
|ILC_COLOR4|イメージ リストのビットマップとして 4 ビット (16 色) のデバイスに依存しないビットマップ (DIB) セクションを使用します。|
|ILC_COLOR8|8 ビット DIB セクションを使用します。 カラーテーブルに使用される色は、ハーフトーンパレットと同じ色です。|
|ILC_COLOR16|16 ビット (32/64k カラー) の DIB セクションを使用します。|
|ILC_COLOR24|24 ビット DIB セクションを使用します。|
|ILC_COLOR32|32 ビット DIB セクションを使用します。|
|ILC_COLORDDB|デバイスに依存するビットマップを使用します。|
|ILC_MASK|マスクを使用します。 イメージ リストには 2 つのビットマップが含まれており、そのうちの 1 つはマスクとして使用されるモノクロ ビットマップです。 この値を含まない場合、イメージ リストにはビットマップが 1 つだけ含まれます。 マスクされたイメージの詳細については、「[イメージ リストからのイメージの描画](../../mfc/drawing-images-from-an-image-list.md)」を参照してください。|

*n初期*<br/>
イメージ リストに最初に含まれるイメージの数。

*nグロー*<br/>
新しいイメージ用のスペースを作るために、システムがリストのサイズを変更する必要がある場合にイメージ リストが大きくなるイメージの数。 このパラメーターは、サイズ変更されたイメージ リストに含めることができる新しいイメージの数を表します。

*を示す*<br/>
イメージ リストに関連付けるビットマップのリソース ID。

*クマスク*<br/>
マスクの生成に使用される色。 指定したビットマップのこの色の各ピクセルは黒に変更され、マスク内の対応するビットは 1 に設定されます。

*をクリックします。*<br/>
イメージのリソース ID を含む文字列。

*イメージリスト1*<br/>
`CImageList` オブジェクトへの参照です。

*nイメージ1*<br/>
最初の既存のイメージのインデックスです。

*イメージリスト2*<br/>
`CImageList` オブジェクトへの参照です。

*nイメージ2*<br/>
2 番目の既存のイメージのインデックス。

*Dx*<br/>
最初のイメージとの関係での 2 番目のイメージの x 軸のオフセット (ピクセル単位)。

*Dy*<br/>
最初のイメージとの関係での 2 番目のイメージの y 軸のオフセット (ピクセル単位)。

*一覧*<br/>
`CImageList` オブジェクトを指すポインターです。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

を`CImageList`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次にイメージ リストを作成して`CImageList`オブジェクトにアタッチする を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#7](../../mfc/reference/codesnippet/cpp/cimagelist-class_5.cpp)]

## <a name="cimagelistdeleteimagelist"></a><a name="deleteimagelist"></a>イメージリスト::D

イメージ リストを削除します。

```
BOOL DeleteImageList();
```

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#8](../../mfc/reference/codesnippet/cpp/cimagelist-class_6.cpp)]

## <a name="cimagelistdeletetempmap"></a><a name="deletetempmap"></a>一覧::D一覧

`CWinApp`アイドル時ハンドラによって自動的に呼び出`DeleteTempMap`され[、FromHandle](#fromhandle)によって作成された一時`hImageList``ImageList``CImageList`オブジェクトは削除されますが、オブジェクトに一時的に関連付けられたハンドル ( ) は破棄されません。

```
static void PASCAL DeleteTempMap();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#9](../../mfc/reference/codesnippet/cpp/cimagelist-class_7.cpp)]

## <a name="cimagelistdetach"></a><a name="detach"></a>イメージリスト::Dエタッハ

イメージ リスト オブジェクトを`CImageList`オブジェクトからデタッチします。

```
HIMAGELIST Detach();
```

### <a name="return-value"></a>戻り値

イメージ リスト オブジェクトへのハンドル。

### <a name="remarks"></a>解説

この関数は、イメージ リスト オブジェクトへのハンドルを返します。

### <a name="example"></a>例

  [次](#attach)の例を参照してください。

## <a name="cimagelistdragenter"></a><a name="dragenter"></a>次のリストを:Dラージ

ドラッグ操作中に *、pWndLock*で指定されたウィンドウの更新をロックし、*ポイント*で指定された位置にドラッグイメージを表示します。

```
static BOOL PASCAL DragEnter(
    CWnd* pWndLock,
    CPoint point);
```

### <a name="parameters"></a>パラメーター

*ドロック*<br/>
ドラッグ イメージを所有するウィンドウへのポインター。

*ポイント*<br/>
ドラッグイメージを表示する位置。 座標は、ウィンドウの左上隅を基準にしています(クライアント領域ではありません)。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

座標はウィンドウの左上隅を基準にするため、座標を指定する場合は、境界線、タイトル バー、メニュー バーなどのウィンドウ要素の幅を補正する必要があります。

*pWndLock*が NULL の場合、この関数はデスクトップ ウィンドウに関連付けられた表示コンテキストにイメージを描画し、座標は画面の左上隅を基準にします。

この関数は、ドラッグ操作中に、指定されたウィンドウに対するその他すべての更新をロックします。 ドラッグ アンド ドロップ操作のターゲットを強調表示するなど、ドラッグ操作中に描画を行う必要がある場合は[、CImageList::DragLeave](#dragleave)関数を使用して、ドラッグしたイメージを一時的に非表示にすることができます。

### <a name="example"></a>例

  [次](#begindrag)の例を参照してください。

## <a name="cimagelistdragleave"></a><a name="dragleave"></a>イメージリスト::Dラグリーブ

*pWndLock*で指定されたウィンドウのロックを解除し、ドラッグイメージを非表示にして、ウィンドウを更新できるようにします。

```
static BOOL PASCAL DragLeave(CWnd* pWndLock);
```

### <a name="parameters"></a>パラメーター

*ドロック*<br/>
ドラッグ イメージを所有するウィンドウへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [次](#enddrag)の例を参照してください。

## <a name="cimagelistdragmove"></a><a name="dragmove"></a>イメージリスト::Dラグムーブ

ドラッグ アンド ドロップ操作中にドラッグされているイメージを移動します。

```
static BOOL PASCAL DragMove(CPoint pt);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
新しいドラッグ位置。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、通常、WM_MOUSEMOVEメッセージに応答して呼び出されます。 ドラッグ操作を開始するには、メンバー関数`BeginDrag`を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#4](../../mfc/reference/codesnippet/cpp/cimagelist-class_8.cpp)]

## <a name="cimagelistdragshownolock"></a><a name="dragshownolock"></a>Cイメージリスト::Dラグショーノロック

ドラッグ操作中に、ウィンドウをロックせずにドラッグ イメージの表示と非表示を切り替えます。

```
static BOOL PASCAL DragShowNolock(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
ドラッグ イメージを表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

[CImageList::DragEnter](#dragenter)関数は、ドラッグ操作中にウィンドウへのすべての更新をロックします。 ただし、この関数はウィンドウをロックしません。

## <a name="cimagelistdraw"></a><a name="draw"></a>イメージリスト::Dロー

ドラッグ アンド ドロップ操作中にドラッグされるイメージを描画します。

```
BOOL Draw(
    CDC* pDC,
    int nImage,
    POINT pt,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
ターゲット デバイス コンテキストへのポインター。

*nイメージ*<br/>
描画するイメージの 0 から始まるインデックス。

*Pt*<br/>
指定したデバイス コンテキスト内で描画する位置。

*nStyle*<br/>
図面スタイルを指定するフラグ。 次の値の 1 つ以上を指定できます。

|[値]|意味|
|-----------|-------------|
|ILD_BLEND25、ILD_FOCUS|イメージを描画し、システムのハイライト カラーと 25% をブレンドします。 イメージ リストにマスクが含まれていない場合、この値は無効です。|
|ILD_BLEND50、ILD_SELECTED、ILD_BLEND|イメージを描画し、システムのハイライト カラーと 50% をブレンドします。 イメージ リストにマスクが含まれていない場合、この値は無効です。|
|ILD_MASK|マスクを描画します。|
|ILD_NORMAL|イメージ リストの背景色を使用してイメージを描画します。 背景色がCLR_NONE値の場合、マスクを使用して画像が透過的に描画されます。|
|ILD_TRANSPARENT|背景色に関係なく、マスクを使用してイメージを透過的に描画します。|

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  の例[を](#setoverlayimage)参照してください。

## <a name="cimagelistdrawex"></a><a name="drawex"></a>イメージリスト::Dローエックス

指定したデバイス コンテキストでイメージ リスト項目を描画します。

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
ターゲット デバイス コンテキストへのポインター。

*nイメージ*<br/>
描画するイメージの 0 から始まるインデックス。

*Pt*<br/>
指定したデバイス コンテキスト内で描画する位置。

*Sz*<br/>
イメージの左上隅を基準にして描画するイメージの部分のサイズ。 Windows SDK の[ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex)で*dx*と*dy*を参照してください。

*clrBk*<br/>
イメージの背景色です。 Windows SDK の[ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex)の*rgbBk*を参照してください。

*clrFg*<br/>
イメージの前景色です。 Windows SDK の[ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex)の*rgbFg*を参照してください。

*nStyle*<br/>
図面スタイルを指定するフラグ。 Windows SDK の[ImageList_DrawEx](/windows/win32/api/commctrl/nf-commctrl-imagelist_drawex)で*fStyle*を参照してください。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、指定した描画スタイルを使用し、指定した色でイメージをブレンドします。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#10](../../mfc/reference/codesnippet/cpp/cimagelist-class_9.cpp)]

## <a name="cimagelistdrawindirect"></a><a name="drawindirect"></a>イメージリスト::Dローインダイレクト

イメージ リストからイメージを描画します。

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

*ピムルド*<br/>
描画操作に関する情報を含む[、イメージリスト描画パラメータの](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams)構造体へのポインター。

*pDC*<br/>
対象デバイス コンテキストへのポインター。 この[CDC](../../mfc/reference/cdc-class.md)オブジェクトを削除する必要があります。

*nイメージ*<br/>
描画されるイメージの 0 から始まるインデックス。

*Pt*<br/>
イメージが描画される x 座標と y 座標を含む[POINT](/previous-versions/dd162805\(v=vs.85\))構造体。

*Sz*<br/>
描画するイメージのサイズを示す[SIZE](/windows/win32/api/windef/ns-windef-size)構造体。

*ptオリジン*<br/>
イメージ自体に対して描画操作の左上隅を指定する x 座標と y 座標を含む[POINT](/previous-versions/dd162805\(v=vs.85\))構造体。 x 座標の左側、y 座標より上のイメージのピクセルは描画されません。

*fStyle*<br/>
図面スタイルを指定するフラグと、必要に応じてオーバーレイ イメージを指定します。 オーバーレイ イメージの詳細については、「解説」を参照してください。 MFC の既定の実装ILD_NORMALは、イメージ リストの背景色を使用してイメージを描画します。 背景色がCLR_NONE値の場合、イメージはマスクを使用して透過的に描画されます。

その他の可能なスタイルについては、[イメージリストドローパラム](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams)構造体の*fStyle*メンバーに記述されています。

*dwRop*<br/>
ラスターオペレーション コードを指定する値。 これらのコードは、ソースの四角形の色データを、最終的な色を実現するために、コピー先の四角形の色データと結合する方法を定義します。 MFC の既定の実装である SRCCOPY は、コピー元の四角形をコピー先の四角形に直接コピーします。 *fStyle*パラメーターにILD_ROP フラグが含まれていない場合、このパラメーターは無視されます。

その他の可能な値は、構造体の*dwRop*メンバーの下で説明[されています](/windows/win32/api/commctrl/ns-commctrl-imagelistdrawparams)。

*RGBバック*<br/>
イメージの背景色 (既定ではCLR_DEFAULT)。 このパラメーターには、アプリケーション定義の RGB 値、または次のいずれかの値を指定できます。

|[値]|意味|
|-----------|-------------|
|CLR_DEFAULT|既定の背景色。 イメージは、イメージ リストの背景色を使用して描画されます。|
|CLR_NONE|背景色なし。 画像は透明に描画されます。|

*rgbフォー*<br/>
イメージの前景色 (既定ではCLR_DEFAULT)。 このパラメーターには、アプリケーション定義の RGB 値、または次のいずれかの値を指定できます。

|[値]|意味|
|-----------|-------------|
|CLR_DEFAULT|既定の前景色。 イメージは、システムのハイライトカラーを前景色として描画します。|
|CLR_NONE|ブレンドカラーなし。 イメージは、ターゲット デバイス コンテキストの色とブレンドされます。|

このパラメーターは *、fStyle*にILD_BLEND25フラグまたはILD_BLEND50フラグが含まれている場合にのみ使用されます。

*fステート*<br/>
図面の状態を指定するフラグ。 このメンバーには、1 つ以上のイメージ リスト状態フラグを含めることができます。

*フレーム*<br/>
飽和およびアルファブレンド効果の動作に影響します。

ILS_SATURATEと共に使用すると、このメンバーは、アイコン内の各ピクセルの RGB トリプレットの各カラー コンポーネントに追加される値を保持します。

ILS_APLHAと共に使用する場合、このメンバーはアルファ チャネルの値を保持します。 この値は 0 から 255 までで、0 は完全に透明で、255 は完全に不透明です。

*クレエフェクト*<br/>
グロー効果とシャドウ効果に使用される[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="return-value"></a>戻り値

イメージが正常に描画された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Win32 構造を自分で埋める場合は、最初のバージョンを使用します。 MFC の既定の引数を 1 つ以上利用する場合や、構造体の管理を避ける場合は、2 番目のバージョンを使用します。

オーバーレイ イメージは、このメンバー関数で*nImage*パラメーターで指定された、プライマリ イメージの上に描画されるイメージです。 [INDEXTOOVERLAYMASK](/windows/win32/api/commctrl/nf-commctrl-indextooverlaymask)マクロを使用して指定されたオーバーレイ マスクの 1 から始まるインデックスを持つ[Draw](#draw)メンバー関数を使用して、オーバーレイ マスクを描画します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#11](../../mfc/reference/codesnippet/cpp/cimagelist-class_10.cpp)]

## <a name="cimagelistenddrag"></a><a name="enddrag"></a>::エンドドラッグ

ドラッグ操作を終了します。

```
static void PASCAL EndDrag();
```

### <a name="remarks"></a>解説

ドラッグ操作を開始するには、メンバー関数`BeginDrag`を使用します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#5](../../mfc/reference/codesnippet/cpp/cimagelist-class_11.cpp)]

## <a name="cimagelistextracticon"></a><a name="extracticon"></a>Cイメージリスト::抽出アイコン

イメージ リスト内のイメージと関連するマスクに基づいてアイコンを作成します。

```
HICON ExtractIcon(int nImage);
```

### <a name="parameters"></a>パラメーター

*nイメージ*<br/>
イメージの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

正常終了した場合はアイコンのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

このメソッドは、アイコンを作成する[ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon)マクロの動作に依存します。 アイコンの作成とクリーンアップの詳細については[、ImageList_ExtractIcon](/windows/win32/api/commctrl/nf-commctrl-imagelist_extracticon)マクロを参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#12](../../mfc/reference/codesnippet/cpp/cimagelist-class_12.cpp)]

## <a name="cimagelistfromhandle"></a><a name="fromhandle"></a>を使用します。

イメージ リストへのハンドル`CImageList`が与えられた場合、オブジェクトへのポインターを返します。

```
static CImageList* PASCAL FromHandle(HIMAGELIST hImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
イメージ リストを指定します。

### <a name="return-value"></a>戻り値

成功した場合は`CImageList`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

ハンドルに`CImageList`a がアタッチされていない場合は、一`CImageList`時オブジェクトが作成され、アタッチされます。 この一`CImageList`時オブジェクトは、アプリケーションがイベント ループで次にアイドル時間を持つまで有効で、その時点ですべての一時オブジェクトが削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#13](../../mfc/reference/codesnippet/cpp/cimagelist-class_13.cpp)]

## <a name="cimagelistfromhandlepermanent"></a><a name="fromhandlepermanent"></a>を使用する

イメージ リストへのハンドル`CImageList`が与えられた場合、オブジェクトへのポインターを返します。

```
static CImageList* PASCAL FromHandlePermanent(HIMAGELIST hImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
イメージ リストを指定します。

### <a name="return-value"></a>戻り値

成功した場合は`CImageList`オブジェクトへのポインター。それ以外の場合は NULL。

### <a name="remarks"></a>解説

オブジェクトが`CImageList`ハンドルにアタッチされていない場合は、NULL が返されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#14](../../mfc/reference/codesnippet/cpp/cimagelist-class_14.cpp)]

## <a name="cimagelistgetbkcolor"></a><a name="getbkcolor"></a>イメージリスト::ゲットブレクカラー

イメージ リストの現在の背景色を取得します。

```
COLORREF GetBkColor() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの背景色の`CImageList`RGB カラー値。

### <a name="example"></a>例

  [の](#setbkcolor)例を参照してください。

## <a name="cimagelistgetdragimage"></a><a name="getdragimage"></a>イメージリスト::取得ドラッグイメージ

ドラッグに使用される一時的なイメージ リストを取得します。

```
static CImageList* PASCAL GetDragImage(
    LPPOINT lpPoint,
    LPPOINT lpPointHotSpot);
```

### <a name="parameters"></a>パラメーター

*lpPoint*<br/>
現在のドラッグ位置を受け取る[POINT](/previous-versions/dd162805\(v=vs.85\))構造体のアドレス。

*スポット*<br/>
ドラッグ位置に`POINT`対するドラッグ イメージのオフセットを受け取る構造体のアドレス。

### <a name="return-value"></a>戻り値

正常に実行された場合は、ドラッグに使用される一時イメージ リストへのポインター。それ以外の場合は NULL。

## <a name="cimagelistgetimagecount"></a><a name="getimagecount"></a>を使用します。

イメージ リスト内のイメージの数を取得します。

```
int GetImageCount() const;
```

### <a name="return-value"></a>戻り値

イメージの数。

### <a name="example"></a>例

  [次](#extracticon)の例を参照してください。

## <a name="cimagelistgetimageinfo"></a><a name="getimageinfo"></a>を使用します。

イメージに関する情報を取得します。

```
BOOL GetImageInfo(
    int nImage,
    IMAGEINFO* pImageInfo) const;
```

### <a name="parameters"></a>パラメーター

*nイメージ*<br/>
イメージの 0 から始まるインデックス。

*イメージインフォ*<br/>
イメージに関する情報を受け取る[IMAGEINFO](/windows/win32/api/commctrl/ns-commctrl-imageinfo)構造体へのポインター。 この構造体の情報を使用して、イメージのビットマップを直接操作できます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

構造`IMAGEINFO`には、イメージ リスト内のイメージに関する情報が含まれています。

## <a name="cimagelistgetsafehandle"></a><a name="getsafehandle"></a>を使用します。

データ メンバーを取得します`m_hImageList`。

```
HIMAGELIST GetSafeHandle() const;
```

### <a name="return-value"></a>戻り値

アタッチされたイメージ リストへのハンドル。オブジェクトがアタッチされていない場合は NULL。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#15](../../mfc/reference/codesnippet/cpp/cimagelist-class_15.cpp)]

## <a name="cimagelistm_himagelist"></a><a name="m_himagelist"></a>イメージリスト::m_hImageList

このオブジェクトにアタッチされているイメージ リストのハンドル。

`HIMAGELIST m_hImageList;`

### <a name="remarks"></a>解説

データ`m_hImageList`メンバーは、型が HIMAGELIST のパブリック変数です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#23](../../mfc/reference/codesnippet/cpp/cimagelist-class_16.cpp)]

## <a name="cimagelistoperator-himagelist"></a><a name="operator_himagelist"></a>イメージリスト::オペレーター・ヒマージュリスト

この演算子を使用して、オブジェクトのアタッチされた`CImageList`ハンドルを取得します。

```
operator HIMAGELIST() const;
```

### <a name="return-value"></a>戻り値

成功した場合は、オブジェクトによって表されるイメージ リスト`CImageList`へのハンドル。それ以外の場合は NULL。

### <a name="remarks"></a>解説

この演算子は、HIMAGELIST オブジェクトの直接使用をサポートするキャスト演算子です。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#16](../../mfc/reference/codesnippet/cpp/cimagelist-class_17.cpp)]

## <a name="cimagelistread"></a><a name="read"></a>イメージリスト::読み取り

アーカイブからイメージ リストを読み取る場合は、この関数を呼び出します。

```
BOOL Read(CArchive* pArchive);
```

### <a name="parameters"></a>パラメーター

*アーカイブ*<br/>
イメージ リストの`CArchive`読み込み元のオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#18](../../mfc/reference/codesnippet/cpp/cimagelist-class_18.cpp)]

## <a name="cimagelistremove"></a><a name="remove"></a>イメージリスト::削除

イメージ リスト オブジェクトからイメージを削除します。

```
BOOL Remove(int nImage);
```

### <a name="parameters"></a>パラメーター

*nイメージ*<br/>
削除するイメージの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*nImage*に続くすべての項目が 1 つ下の位置に移動するようになりました。 たとえば、イメージ リストに 2 つの項目が含まれている場合、最初の項目を削除すると、残りの項目が最初の位置になります。 *nImage*=0 最初の位置の項目。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#19](../../mfc/reference/codesnippet/cpp/cimagelist-class_19.cpp)]

## <a name="cimagelistreplace"></a><a name="replace"></a>置き換え

イメージ リスト内のイメージを新しいイメージに置き換えます。

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

*nイメージ*<br/>
置き換えるイメージの 0 から始まるインデックス。

*イメージ*<br/>
イメージを含むビットマップへのポインター。

*pbmマスク*<br/>
マスクを含むビットマップへのポインター。 イメージ リストでマスクを使用しない場合、このパラメーターは無視されます。

*Hicon*<br/>
新しいイメージのビットマップとマスクを含むアイコンへのハンドル。

### <a name="return-value"></a>戻り値

BOOL を返すバージョンは、成功した場合は 0 以外を返します。それ以外の場合は 0。

**int**を返すバージョンは、イメージの 0 から始まるインデックスを返します。それ以外の場合 - 1。

### <a name="remarks"></a>解説

[SetImageCount](#setimagecount)を呼び出した後、このメンバー関数を呼び出して、新しい有効なイメージをプレースホルダー イメージ インデックス番号に割り当てます。

### <a name="example"></a>例

  の例を参照[してください](#setimagecount)。

## <a name="cimagelistsetbkcolor"></a><a name="setbkcolor"></a>一覧::セットBkカラー

イメージ リストの背景色を設定します。

```
COLORREF SetBkColor(COLORREF cr);
```

### <a name="parameters"></a>パラメーター

*Cr*<br/>
設定する背景色。 それはCLR_NONEすることができます。 その場合、マスクを使用して画像が透明に描画されます。

### <a name="return-value"></a>戻り値

正常終了した場合は前の背景色。それ以外の場合はCLR_NONE。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#20](../../mfc/reference/codesnippet/cpp/cimagelist-class_20.cpp)]

## <a name="cimagelistsetdragcursorimage"></a><a name="setdragcursorimage"></a>イメージリスト::セットドラッグカーソルイメージ

指定したイメージ (通常はマウス カーソル イメージ) と現在のドラッグ イメージを組み合わせて、新しいドラッグ イメージを作成します。

```
BOOL SetDragCursorImage(
    int nDrag,
    CPoint ptHotSpot);
```

### <a name="parameters"></a>パラメーター

*ドラッグ*<br/>
ドラッグイメージと組み合わせる新しいイメージのインデックス。

*プットホットスポット*<br/>
新しいイメージ内のホット スポットの位置。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ドラッグ関数はドラッグ操作中に新しいイメージを使用するため、 を呼び出`CImageList::SetDragCursorImage`した後に、Windows [ShowCursor](/windows/win32/api/winuser/nf-winuser-showcursor)関数を使用して実際のマウス カーソルを非表示にする必要があります。 そうしないと、ドラッグ操作中にマウス カーソルが 2 つ表示されることがあります。

## <a name="cimagelistsetimagecount"></a><a name="setimagecount"></a>を使用します。

`CImageList`オブジェクト内のイメージの数をリセットします。

```
BOOL SetImageCount(UINT uNewCount);
```

### <a name="parameters"></a>パラメーター

*新しいカウント*<br/>
イメージ リスト内のイメージの新しい総数を指定する値。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数を呼び出してイメージ リスト内のイメージの数を増やす場合は、追加の各イメージに対して[Replace](#replace)を呼び出して、新しいインデックスを有効なイメージに割り当てます。 有効なイメージにインデックスを割り当てられなかった場合、新しいイメージを作成する描画操作は予測できません。

この関数を使用してイメージ リストのサイズを小さくすると、切り捨てられたイメージは解放されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#21](../../mfc/reference/codesnippet/cpp/cimagelist-class_21.cpp)]

## <a name="cimagelistsetoverlayimage"></a><a name="setoverlayimage"></a>イメージリスト::イメージを設定します。

オーバーレイ マスクとして使用するイメージの一覧に、イメージの 0 から始まるインデックスを追加します。

```
BOOL SetOverlayImage(
    int nImage,
    int nOverlay);
```

### <a name="parameters"></a>パラメーター

*nイメージ*<br/>
オーバーレイ マスクとして使用するイメージの 0 から始まるインデックス。

*nオーバーレイ*<br/>
オーバーレイ マスクの 1 から始まるインデックス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

リストには最大 4 つのインデックスを追加できます。

オーバーレイ マスクは、別のイメージの上に透明に描画されるイメージです。 [CImageList::Draw](#draw)メンバー関数を使用して、INDEXTOOVERLAYMASK マクロを使用して指定したオーバーレイ マスクの 1 から始まるインデックスを使用して、イメージ上にオーバーレイ マスクを描画します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#22](../../mfc/reference/codesnippet/cpp/cimagelist-class_22.cpp)]

## <a name="cimagelistwrite"></a><a name="write"></a>書き込み

イメージ リスト オブジェクトをアーカイブに書き込みます。

```
BOOL Write(CArchive* pArchive);
```

### <a name="parameters"></a>パラメーター

*アーカイブ*<br/>
イメージ リストが`CArchive`格納されるオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CImageList#17](../../mfc/reference/codesnippet/cpp/cimagelist-class_23.cpp)]

## <a name="see-also"></a>関連項目

[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)<br/>
[CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)
