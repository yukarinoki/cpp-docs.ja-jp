---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CHeaderCtrl
- AFXCMN/CHeaderCtrl
- AFXCMN/CHeaderCtrl::CHeaderCtrl
- AFXCMN/CHeaderCtrl::ClearAllFilters
- AFXCMN/CHeaderCtrl::ClearFilter
- AFXCMN/CHeaderCtrl::Create
- AFXCMN/CHeaderCtrl::CreateDragImage
- AFXCMN/CHeaderCtrl::CreateEx
- AFXCMN/CHeaderCtrl::DeleteItem
- AFXCMN/CHeaderCtrl::DrawItem
- AFXCMN/CHeaderCtrl::EditFilter
- AFXCMN/CHeaderCtrl::GetBitmapMargin
- AFXCMN/CHeaderCtrl::GetFocusedItem
- AFXCMN/CHeaderCtrl::GetImageList
- AFXCMN/CHeaderCtrl::GetItem
- AFXCMN/CHeaderCtrl::GetItemCount
- AFXCMN/CHeaderCtrl::GetItemDropDownRect
- AFXCMN/CHeaderCtrl::GetItemRect
- AFXCMN/CHeaderCtrl::GetOrderArray
- AFXCMN/CHeaderCtrl::GetOverflowRect
- AFXCMN/CHeaderCtrl::HitTest
- AFXCMN/CHeaderCtrl::InsertItem
- AFXCMN/CHeaderCtrl::Layout
- AFXCMN/CHeaderCtrl::OrderToIndex
- AFXCMN/CHeaderCtrl::SetBitmapMargin
- AFXCMN/CHeaderCtrl::SetFilterChangeTimeout
- AFXCMN/CHeaderCtrl::SetFocusedItem
- AFXCMN/CHeaderCtrl::SetHotDivider
- AFXCMN/CHeaderCtrl::SetImageList
- AFXCMN/CHeaderCtrl::SetItem
- AFXCMN/CHeaderCtrl::SetOrderArray
helpviewer_keywords:
- CHeaderCtrl [MFC], CHeaderCtrl
- CHeaderCtrl [MFC], ClearAllFilters
- CHeaderCtrl [MFC], ClearFilter
- CHeaderCtrl [MFC], Create
- CHeaderCtrl [MFC], CreateDragImage
- CHeaderCtrl [MFC], CreateEx
- CHeaderCtrl [MFC], DeleteItem
- CHeaderCtrl [MFC], DrawItem
- CHeaderCtrl [MFC], EditFilter
- CHeaderCtrl [MFC], GetBitmapMargin
- CHeaderCtrl [MFC], GetFocusedItem
- CHeaderCtrl [MFC], GetImageList
- CHeaderCtrl [MFC], GetItem
- CHeaderCtrl [MFC], GetItemCount
- CHeaderCtrl [MFC], GetItemDropDownRect
- CHeaderCtrl [MFC], GetItemRect
- CHeaderCtrl [MFC], GetOrderArray
- CHeaderCtrl [MFC], GetOverflowRect
- CHeaderCtrl [MFC], HitTest
- CHeaderCtrl [MFC], InsertItem
- CHeaderCtrl [MFC], Layout
- CHeaderCtrl [MFC], OrderToIndex
- CHeaderCtrl [MFC], SetBitmapMargin
- CHeaderCtrl [MFC], SetFilterChangeTimeout
- CHeaderCtrl [MFC], SetFocusedItem
- CHeaderCtrl [MFC], SetHotDivider
- CHeaderCtrl [MFC], SetImageList
- CHeaderCtrl [MFC], SetItem
- CHeaderCtrl [MFC], SetOrderArray
ms.assetid: b847ac90-5fae-4a87-88e0-ca45f77b8b3b
ms.openlocfilehash: de1705d47c5692d3563bc7d9cb2646531819197a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750920"
---
# <a name="cheaderctrl-class"></a>クラス

Windows コモン ヘッダー コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次のヘッダーCtrl::CヘッダーCtrl](#cheaderctrl)|`CHeaderCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#clearallfilters)|ヘッダー コントロールのすべてのフィルターをクリアします。|
|[をクリックします。](#clearfilter)|ヘッダー コントロールのフィルターをクリアします。|
|[作成](#create)|ヘッダー コントロールを作成し、`CHeaderCtrl`オブジェクトにアタッチします。|
|[をクリックします。](#createdragimage)|ヘッダー コントロール内に、アイテムのイメージの透明なバージョンを作成します。|
|[をクリックします。](#createex)|指定した Windows 拡張スタイルを使用してヘッダー コントロールを作成し`CListCtrl`、オブジェクトにアタッチします。|
|[:Dエレテアイテム](#deleteitem)|ヘッダー コントロールから項目を削除します。|
|[をクリック :Dします。](#drawitem)|ヘッダー コントロールの指定した項目を描画します。|
|[をクリックします。](#editfilter)|ヘッダー コントロールの指定されたフィルターの編集を開始します。|
|[を取得します。](#getbitmapmargin)|ヘッダー コントロール内のビットマップの余白の幅を取得します。|
|[をクリックします。](#getfocuseditem)|フォーカスのある現在のヘッダー コントロール内の項目の識別子を取得します。|
|[をクリックします。](#getimagelist)|ヘッダー コントロールのヘッダー項目の描画に使用されるイメージ リストのハンドルを取得します。|
|[をクリックします。](#getitem)|ヘッダー コントロール内の項目に関する情報を取得します。|
|[をクリックします。](#getitemcount)|ヘッダー コントロール内の項目の数を取得します。|
|[をクリックします。](#getitemdropdownrect)|ヘッダー コントロール内の指定したドロップダウン ボタンの外接する四角形情報を取得します。|
|[をクリックします。](#getitemrect)|ヘッダー コントロール内の指定した項目に外接する四角形を取得します。|
|[を並べ替えます。](#getorderarray)|ヘッダー コントロール内の項目の左から右への順序を取得します。|
|[をクリックします。](#getoverflowrect)|現在のヘッダー コントロールのオーバーフロー ボタンの外接する四角形を取得します。|
|[ヒットテスト](#hittest)|指定したポイントに配置されているヘッダー項目 (存在する場合) を決定します。|
|[アイテムを挿入します。](#insertitem)|ヘッダー コントロールに新しい項目を挿入します。|
|[レイアウト](#layout)|指定された四角形内のヘッダー コントロールのサイズと位置を取得します。|
|[注文を作成します。](#ordertoindex)|ヘッダー コントロール内の順序に基づいて、項目のインデックス値を取得します。|
|[を設定します。](#setbitmapmargin)|ヘッダー コントロール内のビットマップの余白の幅を設定します。|
|[を変更します。](#setfilterchangetimeout)|フィルター属性で変更が行われる時間と通知の投稿のタイムアウト間隔を設定します`HDN_FILTERCHANGE`。|
|[をクリックします。](#setfocuseditem)|現在のヘッダー コントロールの指定したヘッダー項目にフォーカスを設定します。|
|[をクリックします。](#sethotdivider)|ヘッダー項目間の区切り線を変更して、ヘッダー項目の手動ドラッグ アンド ドロップを示します。|
|[をクリックします。](#setimagelist)|ヘッダー コントロールにイメージ リストを割り当てます。|
|[を設定します。](#setitem)|ヘッダー コントロール内の指定した項目の属性を設定します。|
|[を指定します。](#setorderarray)|ヘッダー コントロール内の項目の左から右への順序を設定します。|

## <a name="remarks"></a>解説

ヘッダー コントロールは、通常、テキストまたは数値の列のセットの上に配置されるウィンドウです。 各列のタイトルが含まれ、各列を分割できます。 ユーザーは、各列の幅を設定するために、部品を区切る分割線をドラッグできます。 ヘッダー コントロールの例については、「[ヘッダー コントロール](/windows/win32/Controls/header-controls)」を参照してください。

このコントロール (および`CHeaderCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されるプログラムでのみ使用できます。

Windows 95/インターネット エクスプローラ 4.0 のコモン コントロールに追加された機能には、次のものがあります。

- ヘッダー項目のカスタム順序付け。

- ヘッダー項目の並べ替え用に、ヘッダー項目のドラッグアンドドロップ。 オブジェクトを作成するときは、HDS_DRAGDROPスタイルを`CHeaderCtrl`使用します。

- 列のサイズ変更中にヘッダー列のテキストを常に表示できます。 オブジェクトを作成するときは、HDS_FULLDRAGスタイルを`CHeaderCtrl`使用します。

- ヘッダーのホット トラッキング(  )は、ポインターがポインターをポイントしているときにヘッダー項目を強調表示します。 オブジェクトを作成するときは、HDS_HOTTRACKスタイルを`CHeaderCtrl`使用します。

- イメージ リストのサポート。 ヘッダー項目には、オブジェクトまたはテキストに`CImageList`格納されているイメージを含めることができます。

の詳細`CHeaderCtrl`については、「[コントロール](../../mfc/controls-mfc.md)と[CHeaderCtrl](../../mfc/using-cheaderctrl.md)の使用 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a>次のヘッダーCtrl::CヘッダーCtrl

`CHeaderCtrl` オブジェクトを構築します。

```
CHeaderCtrl();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a>をクリックします。

ヘッダー コントロールのすべてのフィルターをクリアします。

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、列の値が -1 の Win32 メッセージ[HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a>をクリックします。

ヘッダー コントロールのフィルターをクリアします。

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>パラメーター

*n列*<br/>
クリアするフィルタを示す列の値です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、Win32 メッセージ[HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a>作成

ヘッダー コントロールを作成し、`CHeaderCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
ヘッダー コントロールのスタイルを指定します。 ヘッダー コントロール スタイルの詳細については、Windows SDK の[ヘッダー コントロール スタイル](/windows/win32/Controls/header-control-styles)を参照してください。

*Rect*<br/>
ヘッダー コントロールのサイズと位置を指定します。 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](/windows/win32/api/windef/ns-windef-rect)構造体を指定できます。

*pParentWnd*<br/>
ヘッダー コントロールの親ウィンドウを指定します`CDialog`。 NULL にすることはできません。

*nID*<br/>
ヘッダー コントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は 0 以外。それ以外の場合は 0。

### <a name="remarks"></a>解説

オブジェクトは`CHeaderCtrl`2 つの手順で作成します。 まず、コンストラクタを呼び出し`Create`、次にヘッダー コントロールを作成して`CHeaderCtrl`オブジェクトにアタッチするを呼び出します。

ヘッダー コントロール スタイルに加えて、次の共通のコントロール スタイルを使用して、ヘッダー コントロールの位置とサイズ変更の方法を決定できます (詳細については、「[コモン コントロール スタイル](/windows/win32/Controls/common-control-styles)」を参照してください)。

- CCS_BOTTOM コントロールを親ウィンドウのクライアント領域の下部に配置し、幅を親ウィンドウの幅と同じに設定します。

- CCS_NODIVIDER コントロールの上部に 2 ピクセルのハイライトが描画されないようにします。

- CCS_NOMOVEY WM_SIZE メッセージに応じて、コントロールのサイズを変更し、垂直方向ではなく、水平方向に移動します。 CCS_NORESIZEスタイルを使用する場合、このスタイルは適用されません。 ヘッダー コントロールには、既定でこのスタイルがあります。

- CCS_NOPARENTALIGN コントロールが親ウィンドウの上部または下部に自動的に移動しないようにします。 代わりに、親ウィンドウのサイズが変更された場合も、コントロールは親ウィンドウ内での位置を保持します。 CCS_TOPまたはCCS_BOTTOMスタイルも使用する場合、高さはデフォルトに調整されますが、位置と幅は変更されません。

- CCS_NORESIZE コントロールの初期サイズまたは新しいサイズを設定するときに、コントロールが既定の幅と高さを使用できないようにします。 代わりに、コントロールは、作成またはサイズ変更の要求で指定された幅と高さを使用します。

- CCS_TOP コントロールが親ウィンドウのクライアント領域の先頭に配置され、幅が親ウィンドウの幅と同じになります。

ヘッダー コントロールに次のウィンドウ スタイルを適用することもできます (詳細については、「[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)」を参照してください)。

- WS_CHILD 子ウィンドウを作成します。 WS_POPUPスタイルでは使用できません。

- WS_VISIBLE 最初に表示されるウィンドウを作成します。

- WS_DISABLED最初に無効になっているウィンドウを作成します。

- WS_GROUP方向キーを使用してユーザーがコントロールを移動できるコントロールのグループの最初のコントロールを指定します。 最初のコントロールの後にWS_GROUPスタイルで定義されたすべてのコントロールが同じグループに属します。 WS_GROUPスタイルの次のコントロールは、スタイル グループを終了し、次のグループ (つまり、次のグループが開始する位置で 1 つのグループが終了する) を開始します。

- WS_TABSTOP Tab キーを使用してユーザーが移動できるコントロールの任意の数のいずれかを指定します。 Tab キーは、WS_TABSTOP スタイルで指定された次のコントロールにユーザーを移動します。

コントロールで拡張ウィンドウ スタイルを使用する場合は、 ではなく[CreateEx](#createex)を`Create`呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a>をクリックします。

コントロール (子ウィンドウ) を作成し、`CHeaderCtrl`オブジェクトに関連付けます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*ドウェエクススタイル*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

*Dwstyle*<br/>
ヘッダー コントロールのスタイル。 ヘッダー コントロール スタイルの詳細については、Windows SDK の[ヘッダー コントロール スタイル](/windows/win32/Controls/header-control-styles)を参照してください。 追加のスタイルのリストについては、「[作成](#create)」を参照してください。

*Rect*<br/>
作成するウィンドウのサイズと位置を記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照を *、 pParentWnd*のクライアント座標で指定します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

Windows`CreateEx`拡張`Create`スタイルの序文で指定された拡張 Windows スタイルを適用**する代わりに使用WS_EX_。**

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a>をクリックします。

ヘッダー コントロール内に、アイテムのイメージの透明なバージョンを作成します。

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ヘッダー コントロール内の項目の 0 から始まるインデックス。 このアイテムに割り当てられた画像は、透明な画像の基礎となります。

### <a name="return-value"></a>戻り値

成功した場合は[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。それ以外の場合は NULL。 返されるリストには、1 つのイメージのみが含まれています。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_CREATEDRAGIMAGE](/windows/win32/Controls/hdm-createdragimage)の動作を実装します。 ヘッダー項目のドラッグ アンド ドロップをサポートするために提供されます。

返`CImageList`されたポインターが指すオブジェクトは一時オブジェクトであり、次のアイドル時間処理で削除されます。

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a>:Dエレテアイテム

ヘッダー コントロールから項目を削除します。

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
削除する項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a>をクリック :Dします。

オーナー描画ヘッダー コントロールの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
描画する項目を記述する[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)へのポインター。

### <a name="remarks"></a>解説

構造`itemAction`のメンバーは`DRAWITEMSTRUCT`、実行される描画アクションを定義します。

既定では、このメンバー関数は何も実行しません。 オーナー描画`CHeaderCtrl`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。

アプリケーションは、このメンバー関数が終了する前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a>をクリックします。

ヘッダー コントロールの指定したフィルターの編集を開始します。

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>パラメーター

*n列*<br/>
編集する列。

*変更を破棄する*<br/>
[HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter)メッセージの送信時にユーザーがフィルターの編集中である場合に、ユーザーの編集変更を処理する方法を指定する値。

ユーザーが行った変更を破棄する場合は TRUE を指定し、ユーザーによる変更を受け入れる場合は FALSE を指定します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、Win32 メッセージ[HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a>を取得します。

ヘッダー コントロール内のビットマップの余白の幅を取得します。

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>戻り値

ビットマップの余白の幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a>をクリックします。

現在のヘッダー コントロールにフォーカスがある項目のインデックスを取得します。

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>戻り値

フォーカスのあるヘッダー項目の 0 から始まるインデックス。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_headerCtrl`現在のヘッダー コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

メソッドと メソッド`SetFocusedItem``GetFocusedItem`を次のコード例に示します。 コードの前のセクションでは、5 つの列を持つヘッダー コントロールを作成しました。 ただし、列が表示されないように、列の区切り記号をドラッグできます。 次の使用例は、フォーカス アイテムとして最後の列ヘッダーを設定し、確認します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a>をクリックします。

ヘッダー コントロールのヘッダー項目の描画に使用されるイメージ リストのハンドルを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

[オブジェクト](../../mfc/reference/cimagelist-class.md)へのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_GETIMAGELIST](/windows/win32/Controls/hdm-getimagelist)の動作を実装します。 返`CImageList`されたポインターが指すオブジェクトは一時オブジェクトであり、次のアイドル時間処理で削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a>をクリックします。

ヘッダー コントロール項目に関する情報を取得します。

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
取得する項目の 0 から始まるインデックスを指定します。

*アイテム*<br/>
新しい項目を受け取る[HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw)構造体へのポインター。 この構造体は`InsertItem`、 および`SetItem`メンバー関数で使用されます。 要素に設定された`mask`フラグは、対応する要素の値が返される際に適切に入力されるようにします。 要素が`mask`0 に設定されている場合、他の構造体要素の値は意味を持ちません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a>をクリックします。

ヘッダー コントロール内の項目の数を取得します。

```
int GetItemCount() const;
```

### <a name="return-value"></a>戻り値

成功した場合はヘッダー コントロール項目の数。それ以外の場合 - 1。

### <a name="example"></a>例

  [:D の](#deleteitem)例を参照してください。

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a>をクリックします。

現在のヘッダー コントロールのヘッダー項目のドロップダウン ボタンの外接する四角形を取得します。

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iItem*|[in]スタイルがHDF_SPLITBUTTONされるヘッダー項目の 0 から始まるインデックス。 詳しくは[、HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) `fmt`構造体のメンバーを参照してください。|
|*Lprect*|[アウト]外接する四角形の情報を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。|

### <a name="return-value"></a>戻り値

この関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_headerCtrl`現在のヘッダー コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

メソッドのコード例を次に`GetItemDropDownRect`示します。 コードの前のセクションでは、5 つの列を持つヘッダー コントロールを作成しました。 ヘッダー ドロップダウン ボタン用に予約されている最初の列の位置を 3D 四角形の周囲に描画するコード例を次に示します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a>をクリックします。

ヘッダー コントロール内の指定した項目に外接する四角形を取得します。

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ヘッダー コントロール項目の 0 から始まるインデックス。

*Lprect*<br/>
外接する四角形の情報を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体のアドレスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、Win32 メッセージ[HDM_GETITEMRECT](/windows/win32/Controls/hdm-getitemrect)の動作を実装します。

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a>を並べ替えます。

ヘッダー コントロール内の項目の左から右への順序を取得します。

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>パラメーター

*ピアレイ*<br/>
ヘッダー コントロール内の項目のインデックス値を左から右に表示する順序で受け取るバッファーのアドレスへのポインター。

*iカウント*<br/>
ヘッダー コントロール項目の数。 負以外の値である必要があります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_GETORDERARRAY](/windows/win32/Controls/hdm-getorderarray)の動作を実装します。 ヘッダー項目の順序付けをサポートするために提供されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a>をクリックします。

現在のヘッダー コントロールのオーバーフロー ボタンの外接する四角形を取得します。

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*Lprect*|[アウト]外接する四角形の情報を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。|

### <a name="return-value"></a>戻り値

この関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

ヘッダー コントロールに同時に表示できる項目数を超える項目が含まれている場合、コントロールは表示されていない項目までスクロールするオーバーフロー ボタンを表示できます。 ヘッダー コントロールには、オーバーフロー ボタンを表示するHDS_OVERFLOWスタイルとHDF_SPLITBUTTON スタイルが必要です。 外接する四角形は、オーバーフロー ボタンを囲み、オーバーフロー ボタンが表示されている場合にのみ存在します。 詳細については、「ヘッダー[コントロール スタイル](/windows/win32/Controls/header-control-styles)」を参照してください。

このメソッドは、Windows SDK で説明されている[HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_headerCtrl`現在のヘッダー コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

メソッドのコード例を次に`GetOverflowRect`示します。 コードの前のセクションでは、5 つの列を持つヘッダー コントロールを作成しました。 ただし、列が表示されないように、列の区切り記号をドラッグできます。 一部の列が表示されない場合、ヘッダー コントロールはオーバーフロー ボタンを描画します。 オーバーフロー ボタンの位置を囲む 3D 四角形を描画するコード例を次に示します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a>ヒットテスト

指定したポイントに配置されているヘッダー項目 (存在する場合) を決定します。

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*フドティ*|[イン、アウト]テストするポイントを指定し、テストの結果を受け取る[HDHITTESTINFO](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo)構造体へのポインター。|

### <a name="return-value"></a>戻り値

ヘッダー項目の 0 から始まるインデックス (存在する場合) の指定された位置。それ以外の場合は -1。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[HDM_HITTEST](/windows/win32/Controls/hdm-hittest)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_headerCtrl`現在のヘッダー コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

メソッドのコード例を次に`HitTest`示します。 このコード例の前のセクションでは、5 つの列を持つヘッダー コントロールを作成しました。 ただし、列が表示されないように、列の区切り記号をドラッグできます。 次の使用例は、列が表示されている場合は列のインデックスをレポートし、列が表示されていない場合は -1 をレポートします。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a>アイテムを挿入します。

ヘッダー コントロールの指定したインデックス位置に新しい項目を挿入します。

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
挿入する項目の 0 から始まるインデックス。 値が 0 の場合、項目はヘッダー コントロールの先頭に挿入されます。 値が最大値より大きい場合、項目はヘッダー コントロールの末尾に挿入されます。

*フディ*<br/>
挿入する項目に関する情報を含む[HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は新しい項目のインデックス。それ以外の場合 - 1。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a>レイアウト

指定された四角形内のヘッダー コントロールのサイズと位置を取得します。

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>パラメーター

*レイアウト*<br/>
ヘッダー コントロールのサイズと位置を設定するために使用される情報を含む[HDLAYOUT](/windows/win32/api/commctrl/ns-commctrl-hdlayout)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、指定された四角形を占有する新しいヘッダー コントロールの適切なサイズを決定するために使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a>注文を作成します。

ヘッダー コントロール内の順序に基づいて、項目のインデックス値を取得します。

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>パラメーター

*n注文*<br/>
項目がヘッダー コントロールに表示される、左から右への 0 から始まる順序。

### <a name="return-value"></a>戻り値

ヘッダー コントロール内での順序に基づく項目のインデックス。 インデックスは、左から右に 0 から始まる数です。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 マクロ[HDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex)の動作を実装します。 ヘッダー項目の順序付けをサポートするために提供されます。

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a>を設定します。

ヘッダー コントロール内のビットマップの余白の幅を設定します。

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>パラメーター

*n幅*<br/>
既存のヘッダー コントロール内のビットマップを囲む余白の幅 (ピクセル単位)。

### <a name="return-value"></a>戻り値

ビットマップの余白の幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_SETBITMAPMARGIN](/windows/win32/Controls/hdm-setbitmapmargin)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a>を変更します。

フィルター属性で変更が行われるまでのタイムアウト間隔と[、HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange)通知の投稿のタイムアウト間隔を設定します。

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>パラメーター

*を実行します。*<br/>
タイムアウト値 (ミリ秒単位)。

### <a name="return-value"></a>戻り値

変更するフィルター コントロールのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_SETFILTERCHANGETIMEOUT](/windows/win32/Controls/hdm-setfilterchangetimeout)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a>をクリックします。

現在のヘッダー コントロールの指定したヘッダー項目にフォーカスを設定します。

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iItem*|[in]ヘッダー項目の 0 から始まるインデックス。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている[HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem)メッセージを送信します。

### <a name="example"></a>例

次のコード例では、`m_headerCtrl`現在のヘッダー コントロールにアクセスするために使用される変数 を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

メソッドと メソッド`SetFocusedItem``GetFocusedItem`を次のコード例に示します。 コードの前のセクションでは、5 つの列を持つヘッダー コントロールを作成しました。 ただし、列が表示されないように、列の区切り記号をドラッグできます。 次の使用例は、フォーカス アイテムとして最後の列ヘッダーを設定し、確認します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a>をクリックします。

ヘッダー項目間の区切り線を変更して、ヘッダー項目の手動ドラッグ アンド ドロップを示します。

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>パラメーター

*Pt*<br/>
ポインターの位置。 ヘッダー コントロールは、ポインターの位置に基づいて適切な分割線を強調表示します。

*nIndex*<br/>
強調表示された区分線のインデックス。

### <a name="return-value"></a>戻り値

強調表示された区分線のインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_SETHOTDIVIDER](/windows/win32/Controls/hdm-sethotdivider)の動作を実装します。 ヘッダー項目のドラッグ アンド ドロップをサポートするために提供されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a>をクリックします。

ヘッダー コントロールにイメージ リストを割り当てます。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
ヘッダー コントロールに`CImageList`割り当てるイメージ リストを含むオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

ヘッダー コントロールに割り当てられた[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist)の動作を実装します。 返`CImageList`されたポインターが指すオブジェクトは一時オブジェクトであり、次のアイドル時間処理で削除されます。

### <a name="example"></a>例

  の[例を参照](#getimagelist)してください。

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a>を設定します。

ヘッダー コントロール内の指定した項目の属性を設定します。

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>パラメーター

*Npo*<br/>
操作する項目の 0 から始まるインデックス。

*アイテム*<br/>
新しい項目に関する情報を含む[HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [の](#getitem)例を参照してください。

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a>を指定します。

ヘッダー コントロール内の項目の左から右への順序を設定します。

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>パラメーター

*iカウント*<br/>
ヘッダー コントロール項目の数。

*ピアレイ*<br/>
ヘッダー コントロール内の項目のインデックス値を左から右に表示する順序で受け取るバッファーのアドレスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 マクロ[HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray)の動作を実装します。 ヘッダー項目の順序付けをサポートするために提供されます。

### <a name="example"></a>例

  の[例を参照](#getorderarray)してください。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList クラス](../../mfc/reference/cimagelist-class.md)
