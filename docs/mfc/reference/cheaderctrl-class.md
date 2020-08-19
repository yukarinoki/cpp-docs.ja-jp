---
title: CHeaderCtrl クラス
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
ms.openlocfilehash: f225d406ab1560b4308a468ebd71b3dfd88cfa2a
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562174"
---
# <a name="cheaderctrl-class"></a>CHeaderCtrl クラス

Windows コモン ヘッダー コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CHeaderCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHeaderCtrl:: CHeaderCtrl](#cheaderctrl)|`CHeaderCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHeaderCtrl:: ClearAllFilters](#clearallfilters)|ヘッダーコントロールのすべてのフィルターをクリアします。|
|[CHeaderCtrl:: ClearFilter](#clearfilter)|ヘッダーコントロールのフィルターをクリアします。|
|[CHeaderCtrl:: Create](#create)|ヘッダーコントロールを作成し、オブジェクトにアタッチし `CHeaderCtrl` ます。|
|[CHeaderCtrl:: CreateDragImage](#createdragimage)|ヘッダーコントロール内の項目のイメージの透明バージョンを作成します。|
|[CHeaderCtrl:: CreateEx](#createex)|指定した Windows 拡張スタイルを使用してヘッダーコントロールを作成し、オブジェクトに添付し `CListCtrl` ます。|
|[CHeaderCtrl::D eleteItem](#deleteitem)|ヘッダーコントロールから項目を削除します。|
|[CHeaderCtrl::D rawItem](#drawitem)|ヘッダーコントロールの指定された項目を描画します。|
|[CHeaderCtrl:: EditFilter](#editfilter)|ヘッダーコントロールの指定したフィルターの編集を開始します。|
|[CHeaderCtrl:: GetBitmapMargin](#getbitmapmargin)|ヘッダーコントロールのビットマップの余白の幅を取得します。|
|[CHeaderCtrl:: GetFocusedItem](#getfocuseditem)|フォーカスがある現在のヘッダーコントロール内の項目の識別子を取得します。|
|[CHeaderCtrl:: GetImageList](#getimagelist)|ヘッダーコントロールのヘッダー項目を描画するために使用されるイメージリストのハンドルを取得します。|
|[CHeaderCtrl:: GetItem](#getitem)|ヘッダーコントロールの項目に関する情報を取得します。|
|[CHeaderCtrl:: GetItemCount](#getitemcount)|ヘッダーコントロール内の項目の数を取得します。|
|[CHeaderCtrl:: GetItemDropDownRect](#getitemdropdownrect)|ヘッダーコントロールの指定されたドロップダウンボタンの外接する四角形の情報を取得します。|
|[CHeaderCtrl:: GetItemRect](#getitemrect)|ヘッダーコントロール内の指定された項目の外接する四角形を取得します。|
|[CHeaderCtrl:: GetOrderArray](#getorderarray)|ヘッダーコントロール内の項目の左から右の順序を取得します。|
|[CHeaderCtrl:: GetOverflowRect](#getoverflowrect)|現在のヘッダーコントロールのオーバーフローボタンの外接する四角形を取得します。|
|[CHeaderCtrl:: System.windows.media.visualtreehelper.hittest](#hittest)|指定したポイントに存在するヘッダー項目を判断します。|
|[CHeaderCtrl:: InsertItem](#insertitem)|新しい項目をヘッダーコントロールに挿入します。|
|[CHeaderCtrl:: Layout](#layout)|指定された四角形内のヘッダーコントロールのサイズと位置を取得します。|
|[CHeaderCtrl:: OrderToIndex](#ordertoindex)|ヘッダーコントロールの順序に基づいて、項目のインデックス値を取得します。|
|[CHeaderCtrl:: SetBitmapMargin](#setbitmapmargin)|ヘッダーコントロールのビットマップの余白の幅を設定します。|
|[CHeaderCtrl:: SetFilterChangeTimeout](#setfilterchangetimeout)|フィルター属性および通知の投稿で変更が行われるまでのタイムアウト間隔を設定し `HDN_FILTERCHANGE` ます。|
|[CHeaderCtrl:: SetFocusedItem](#setfocuseditem)|現在のヘッダーコントロール内の指定されたヘッダー項目にフォーカスを設定します。|
|[CHeaderCtrl:: SetHotDivider](#sethotdivider)|ヘッダー項目を手動でドラッグアンドドロップしたことを示すために、ヘッダー項目間の区分線を変更します。|
|[CHeaderCtrl:: SetImageList](#setimagelist)|イメージリストをヘッダーコントロールに割り当てます。|
|[CHeaderCtrl:: SetItem](#setitem)|ヘッダーコントロール内の指定された項目の属性を設定します。|
|[CHeaderCtrl:: SetOrderArray](#setorderarray)|ヘッダーコントロールの項目の左から右への順序を設定します。|

## <a name="remarks"></a>解説

ヘッダーコントロールは、通常、テキストまたは数値の列のセットの上に配置されるウィンドウです。 このファイルには、各列のタイトルが含まれており、それぞれの部分に分割できます。 ユーザーは、パーツを区切る分割線をドラッグして、各列の幅を設定できます。 ヘッダーコントロールの図解は、「 [ヘッダーコントロール](/windows/win32/Controls/header-controls)」を参照してください。

このコントロール (および `CHeaderCtrl` クラス) は、windows 95/98 および WINDOWS NT バージョン3.51 以降で実行されるプログラムに対してのみ使用できます。

Windows 95/Internet Explorer 4.0 コモンコントロールに追加された機能には、次のものが含まれます。

- ヘッダー項目のカスタムの順序付け。

- ヘッダー項目を並べ替えるための、ヘッダー項目のドラッグアンドドロップ。 オブジェクトを作成するときは、HDS_DRAGDROP スタイルを使用し `CHeaderCtrl` ます。

- ヘッダー列のテキストは、列のサイズ変更中に常に表示できます。 オブジェクトを作成するときは、HDS_FULLDRAG スタイルを使用し `CHeaderCtrl` ます。

- ヘッダーホットトラッキング。ポインターがその上にポインターを置いたときに、ヘッダー項目を強調表示します。 オブジェクトを作成するときは、HDS_HOTTRACK スタイルを使用し `CHeaderCtrl` ます。

- イメージリストのサポート。 ヘッダー項目には、オブジェクトまたはテキストに格納されているイメージを含めることができ `CImageList` ます。

の使用方法の詳細について `CHeaderCtrl` は、「 [Controls](../../mfc/controls-mfc.md) and [using CHeaderCtrl](../../mfc/using-cheaderctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="cheaderctrlcheaderctrl"></a><a name="cheaderctrl"></a> CHeaderCtrl:: CHeaderCtrl

`CHeaderCtrl` オブジェクトを構築します。

```
CHeaderCtrl();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

## <a name="cheaderctrlclearallfilters"></a><a name="clearallfilters"></a> CHeaderCtrl:: ClearAllFilters

ヘッダーコントロールのすべてのフィルターをクリアします。

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、列の値が-1 である Win32 メッセージ [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter) の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

## <a name="cheaderctrlclearfilter"></a><a name="clearfilter"></a> CHeaderCtrl:: ClearFilter

ヘッダーコントロールのフィルターをクリアします。

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>パラメーター

*n 列*<br/>
クリアするフィルターを示す列の値。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、Win32 メッセージ [HDM_CLEARFILTER](/windows/win32/Controls/hdm-clearfilter)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

## <a name="cheaderctrlcreate"></a><a name="create"></a> CHeaderCtrl:: Create

ヘッダーコントロールを作成し、オブジェクトにアタッチし `CHeaderCtrl` ます。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ヘッダーコントロールのスタイルを指定します。 ヘッダーコントロールスタイルの説明については、「Windows SDK の [ヘッダーコントロールスタイル](/windows/win32/Controls/header-control-styles) 」を参照してください。

*rect*<br/>
ヘッダーコントロールのサイズと位置を指定します。 これは、 [CRect](../../atl-mfc-shared/reference/crect-class.md) オブジェクトまたは [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体のいずれかになります。

*pParentWnd*<br/>
ヘッダーコントロールの親ウィンドウ (通常は) を指定し `CDialog` ます。 NULL にすることはできません。

*nID*<br/>
ヘッダーコントロールの ID を指定します。

### <a name="return-value"></a>戻り値

初期化が成功した場合は0以外の。それ以外の場合は0。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CHeaderCtrl` 2 つの手順を実行します。 まず、コンストラクターを呼び出し、次に `Create` を呼び出します。これにより、ヘッダーコントロールが作成され、オブジェクトにアタッチさ `CHeaderCtrl` れます。

ヘッダーコントロールスタイルに加えて、次のコモンコントロールスタイルを使用して、ヘッダーコントロールの位置とサイズの変更方法を決定できます (詳細については、「 [コモンコントロールスタイル](/windows/win32/Controls/common-control-styles) 」を参照してください)。

- CCS_BOTTOM により、コントロールは親ウィンドウのクライアント領域の下部に配置され、幅は親ウィンドウの幅と同じになるように設定されます。

- CCS_NODIVIDER を指定すると、コントロールの上部に2ピクセルの強調表示が描画されません。

- CCS_NOMOVEY を指定すると、コントロールのサイズが変更され、WM_SIZE メッセージに応答して垂直方向ではなく、水平方向に移動します。 CCS_NORESIZE スタイルが使用されている場合、このスタイルは適用されません。 既定では、ヘッダーコントロールにこのスタイルが設定されています。

- CCS_NOPARENTALIGN コントロールが親ウィンドウの上部または下部に自動的に移動しないようにします。 代わりに、親ウィンドウのサイズが変更されても、コントロールの位置は親ウィンドウ内で保持されます。 CCS_TOP または CCS_BOTTOM スタイルも使用されている場合は、高さが既定値に調整されますが、位置と幅は変わりません。

- CCS_NORESIZE は、初期サイズまたは新しいサイズを設定するときに、コントロールが既定の幅と高さを使用しないようにします。 代わりに、コントロールは要求で指定された幅と高さを使用して作成またはサイズ変更を行います。

- CCS_TOP により、コントロールは親ウィンドウのクライアント領域の上端に配置され、幅は親ウィンドウの幅と同じになるように設定されます。

次のウィンドウスタイルをヘッダーコントロールに適用することもできます (詳細については、「 [ウィンドウのスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles) 」を参照してください)。

- WS_CHILD 子ウィンドウを作成します。 WS_POPUP スタイルと共に使用することはできません。

- WS_VISIBLE、最初に表示されるウィンドウを作成します。

- WS_DISABLED は、最初は無効になっているウィンドウを作成します。

- WS_GROUP は、ユーザーが方向キーを使用して1つのコントロールから次のコントロールに移動できる、コントロールのグループの最初のコントロールを指定します。 最初のコントロールの後に WS_GROUP スタイルで定義されているすべてのコントロールが同じグループに属しています。 WS_GROUP スタイルの次のコントロールは、スタイルグループを終了し、次のグループを開始します (つまり、次の開始位置にある1つのグループが終了します)。

- WS_TABSTOP は、TAB キーを使用してユーザーが移動できるコントロールの1つを指定します。 Tab キーは、WS_TABSTOP スタイルで指定された次のコントロールにユーザーを移動します。

拡張 windows スタイルをコントロールで使用する場合は、ではなく [CreateEx](#createex) を呼び出し `Create` ます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

## <a name="cheaderctrlcreateex"></a><a name="createex"></a> CHeaderCtrl:: CreateEx

コントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CHeaderCtrl` ます。

```
virtual BOOL CreateEx(
    DWORD dwExStyle,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwExStyle*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の[CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の*dwexstyle*パラメーターを参照してください。

*dwStyle*<br/>
ヘッダーコントロールのスタイル。 ヘッダーコントロールスタイルの説明については、「Windows SDK の [ヘッダーコントロールスタイル](/windows/win32/Controls/header-control-styles) 」を参照してください。 追加のスタイルの一覧については、「 [作成](#create) 」を参照してください。

*rect*<br/>
*PParentWnd*のクライアント座標で、作成されるウィンドウのサイズと位置を記述する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`CreateEx` `Create` Windows 拡張スタイルの先頭**WS_EX_** によって指定された拡張 windows スタイルを適用するには、の代わりにを使用します。

## <a name="cheaderctrlcreatedragimage"></a><a name="createdragimage"></a> CHeaderCtrl:: CreateDragImage

ヘッダーコントロール内の項目のイメージの透明バージョンを作成します。

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ヘッダーコントロール内の項目の0から始まるインデックス。 この項目に割り当てられたイメージは、透明なイメージの基礎となります。

### <a name="return-value"></a>戻り値

成功した場合は、 [CImageList](../../mfc/reference/cimagelist-class.md) オブジェクトへのポインター。それ以外の場合は NULL。 返される一覧には、イメージが1つだけ含まれます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_CREATEDRAGIMAGE](/windows/win32/Controls/hdm-createdragimage)の動作を実装します。 ヘッダー項目のドラッグアンドドロップをサポートするために用意されています。

返された `CImageList` ポインターが指すオブジェクトは一時オブジェクトであり、次のアイドル時の処理で削除されます。

## <a name="cheaderctrldeleteitem"></a><a name="deleteitem"></a> CHeaderCtrl::D eleteItem

ヘッダーコントロールから項目を削除します。

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
削除する項目の0から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

## <a name="cheaderctrldrawitem"></a><a name="drawitem"></a> CHeaderCtrl::D rawItem

オーナー描画ヘッダーコントロールの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
描画する項目を記述する [DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) 構造体へのポインター。

### <a name="remarks"></a>解説

`itemAction`構造体のメンバーは、 `DRAWITEMSTRUCT` 実行する描画アクションを定義します。

既定では、このメンバー関数は何も行いません。 オーナー描画オブジェクトの描画を実装するには、このメンバー関数をオーバーライドし `CHeaderCtrl` ます。

このメンバー関数が終了する前に、アプリケーションでは、 *lpDrawItemStruct* で指定された表示コンテキスト用に選択されたすべてのグラフィックスデバイスインターフェイス (GDI) オブジェクトを復元する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

## <a name="cheaderctrleditfilter"></a><a name="editfilter"></a> CHeaderCtrl:: EditFilter

ヘッダーコントロールの指定されたフィルターの編集を開始します。

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>パラメーター

*n 列*<br/>
編集する列。

*bDiscardChanges*<br/>
[HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter)メッセージが送信されたときにユーザーがフィルターを編集する処理を行っている場合に、ユーザーの編集変更を処理する方法を指定する値。

ユーザーによって行われた変更を破棄する場合は TRUE を、ユーザーが行った変更を受け入れる場合は FALSE を指定します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、Win32 メッセージ [HDM_EDITFILTER](/windows/win32/Controls/hdm-editfilter)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

## <a name="cheaderctrlgetbitmapmargin"></a><a name="getbitmapmargin"></a> CHeaderCtrl:: GetBitmapMargin

ヘッダーコントロールのビットマップの余白の幅を取得します。

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>戻り値

ビットマップ余白の幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_GETBITMAPMARGIN](/windows/win32/Controls/hdm-getbitmapmargin)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

## <a name="cheaderctrlgetfocuseditem"></a><a name="getfocuseditem"></a> CHeaderCtrl:: GetFocusedItem

現在のヘッダーコントロールでフォーカスがある項目のインデックスを取得します。

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>戻り値

フォーカスがあるヘッダー項目の0から始まるインデックス。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [HDM_GETFOCUSEDITEM](/windows/win32/Controls/hdm-getfocuseditem) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、 `m_headerCtrl` 現在のヘッダーコントロールにアクセスするために使用される変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例は、 `SetFocusedItem` メソッドとメソッドを示して `GetFocusedItem` います。 コードの前のセクションでは、5つの列を持つヘッダーコントロールを作成しました。 ただし、列が表示されないようにするには、列の区切り線をドラッグします。 次の例では、を設定し、最後の列ヘッダーをフォーカス項目として確認します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlgetimagelist"></a><a name="getimagelist"></a> CHeaderCtrl:: GetImageList

ヘッダーコントロールのヘッダー項目を描画するために使用されるイメージリストのハンドルを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_GETIMAGELIST](/windows/win32/Controls/hdm-getimagelist)の動作を実装します。 返された `CImageList` ポインターが指すオブジェクトは一時オブジェクトであり、次のアイドル時の処理で削除されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

## <a name="cheaderctrlgetitem"></a><a name="getitem"></a> CHeaderCtrl:: GetItem

ヘッダーコントロール項目に関する情報を取得します。

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
取得する項目の0から始まるインデックスを指定します。

*pHeaderItem*<br/>
新しい項目を受け取る [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 構造体へのポインター。 この構造体は、およびメンバー関数と共に使用され `InsertItem` `SetItem` ます。 要素に設定されているフラグによっ `mask` て、返されるときに、対応する要素の値が正しく入力されます。 `mask`要素がゼロに設定されている場合、他の構造体要素の値は無意味になります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

## <a name="cheaderctrlgetitemcount"></a><a name="getitemcount"></a> CHeaderCtrl:: GetItemCount

ヘッダーコントロール内の項目の数を取得します。

```
int GetItemCount() const;
```

### <a name="return-value"></a>戻り値

成功した場合はヘッダーコントロール項目の数。それ以外の場合は-1。

### <a name="example"></a>例

  [CHeaderCtrl::D eleteitem](#deleteitem)の例を参照してください。

## <a name="cheaderctrlgetitemdropdownrect"></a><a name="getitemdropdownrect"></a> CHeaderCtrl:: GetItemDropDownRect

現在のヘッダーコントロールのヘッダー項目のドロップダウンボタンの外接する四角形を取得します。

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*iItem*\
からスタイルが HDF_SPLITBUTTON であるヘッダー項目の0から始まるインデックス。 詳細については、 `fmt` [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 構造体のメンバーを参照してください。

*lpRect*\
入出力外接する四角形の情報を受け取る [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。

### <a name="return-value"></a>戻り値

この関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [HDM_GETITEMDROPDOWNRECT](/windows/win32/Controls/hdm-getitemdropdownrect) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、 `m_headerCtrl` 現在のヘッダーコントロールにアクセスするために使用される変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例は、メソッドを示して `GetItemDropDownRect` います。 コードの前のセクションでは、5つの列を持つヘッダーコントロールを作成しました。 次のコード例では、ヘッダーのドロップダウンボタン用に予約されている最初の列の位置を囲む3D 四角形を描画します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

## <a name="cheaderctrlgetitemrect"></a><a name="getitemrect"></a> CHeaderCtrl:: GetItemRect

ヘッダーコントロール内の指定された項目の外接する四角形を取得します。

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ヘッダーコントロール項目の0から始まるインデックス。

*lpRect*<br/>
外接する四角形の情報を受け取る [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体のアドレスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されているように、Win32 メッセージ [HDM_GETITEMRECT](/windows/win32/Controls/hdm-getitemrect)の動作を実装します。

## <a name="cheaderctrlgetorderarray"></a><a name="getorderarray"></a> CHeaderCtrl:: GetOrderArray

ヘッダーコントロール内の項目の左から右の順序を取得します。

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>パラメーター

*piArray*<br/>
ヘッダーコントロール内の項目のインデックス値を、左から右へと表示される順序で受け取るバッファーのアドレスへのポインター。

*iCount*<br/>
ヘッダーコントロール項目の数。 負でない値である必要があります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_GETORDERARRAY](/windows/win32/Controls/hdm-getorderarray)の動作を実装します。 ヘッダー項目の順序付けをサポートするために用意されています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

## <a name="cheaderctrlgetoverflowrect"></a><a name="getoverflowrect"></a> CHeaderCtrl:: GetOverflowRect

現在のヘッダーコントロールのオーバーフローボタンの外接する四角形を取得します。

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*lpRect*\
入出力外接する四角形の情報を受け取る [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。

### <a name="return-value"></a>戻り値

この関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

同時に表示できない項目がヘッダーコントロールに含まれている場合、コントロールは、表示されていない項目にスクロールするオーバーフローボタンを表示できます。 オーバーフローボタンを表示するには、ヘッダーコントロールに HDS_OVERFLOW と HDF_SPLITBUTTON スタイルが設定されている必要があります。 外接する四角形はオーバーフローボタンを囲み、オーバーフローボタンが表示されている場合にのみ存在します。 詳細については、「 [ヘッダーコントロールのスタイル](/windows/win32/Controls/header-control-styles)」を参照してください。

このメソッドは、Windows SDK で説明されている [HDM_GETOVERFLOWRECT](/windows/win32/Controls/hdm-getoverflowrect) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、 `m_headerCtrl` 現在のヘッダーコントロールにアクセスするために使用される変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例は、メソッドを示して `GetOverflowRect` います。 コードの前のセクションでは、5つの列を持つヘッダーコントロールを作成しました。 ただし、列が表示されないようにするには、列の区切り線をドラッグします。 一部の列が表示されていない場合、ヘッダーコントロールはオーバーフローボタンを描画します。 次のコード例では、オーバーフローボタンの位置を囲む3D 四角形を描画します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

## <a name="cheaderctrlhittest"></a><a name="hittest"></a> CHeaderCtrl:: System.windows.media.visualtreehelper.hittest

指定したポイントに存在するヘッダー項目を判断します。

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>パラメーター

*phdhti*\
[入力、出力]テストの結果をテストして受け取るポイントを指定する [Hdhittestinfo](/windows/win32/api/commctrl/ns-commctrl-hdhittestinfo) 構造体へのポインター。

### <a name="return-value"></a>戻り値

ヘッダー項目の0から始まるインデックス (存在する場合)。指定した位置にある場合は。それ以外の場合は-1。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [HDM_HITTEST](/windows/win32/Controls/hdm-hittest) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、 `m_headerCtrl` 現在のヘッダーコントロールにアクセスするために使用される変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例は、メソッドを示して `HitTest` います。 このコード例の前のセクションでは、5つの列を持つヘッダーコントロールを作成しました。 ただし、列が表示されないようにするには、列の区切り線をドラッグします。 この例では、列が表示されている場合はそのインデックスを報告し、列が表示されていない場合は-1 を報告します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

## <a name="cheaderctrlinsertitem"></a><a name="insertitem"></a> CHeaderCtrl:: InsertItem

ヘッダーコントロール内の指定したインデックス位置に新しい項目を挿入します。

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
挿入する項目の 0 から始まるインデックス。 値が0の場合は、ヘッダーコントロールの先頭に項目が挿入されます。 値が最大値より大きい場合は、ヘッダーコントロールの末尾に項目が挿入されます。

*phdi*<br/>
挿入する項目に関する情報を格納している [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 構造体へのポインター。

### <a name="return-value"></a>戻り値

成功した場合は、新しい項目のインデックス。それ以外の場合は-1。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

## <a name="cheaderctrllayout"></a><a name="layout"></a> CHeaderCtrl:: Layout

指定された四角形内のヘッダーコントロールのサイズと位置を取得します。

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>パラメーター

*pHeaderLayout*<br/>
ヘッダーコントロールのサイズと位置を設定するために使用される情報を格納する、 [Hdlayout](/windows/win32/api/commctrl/ns-commctrl-hdlayout) 構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、指定された四角形を占有する新しいヘッダーコントロールの適切な次元を決定するために使用されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

## <a name="cheaderctrlordertoindex"></a><a name="ordertoindex"></a> CHeaderCtrl:: OrderToIndex

ヘッダーコントロールの順序に基づいて、項目のインデックス値を取得します。

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>パラメーター

*nOrder*<br/>
ヘッダーコントロールの項目が左から右へと表示される、0から始まる順序。

### <a name="return-value"></a>戻り値

ヘッダーコントロールの順序に基づいた項目のインデックス。 インデックスは、0から順に左から右にカウントされます。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 マクロ [HDM_ORDERTOINDEX](/windows/win32/controls/hdm-ordertoindex)の動作を実装します。 ヘッダー項目の順序付けをサポートするために用意されています。

## <a name="cheaderctrlsetbitmapmargin"></a><a name="setbitmapmargin"></a> CHeaderCtrl:: SetBitmapMargin

ヘッダーコントロールのビットマップの余白の幅を設定します。

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
既存のヘッダーコントロール内のビットマップを囲む余白の幅 (ピクセル単位)。

### <a name="return-value"></a>戻り値

ビットマップ余白の幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_SETBITMAPMARGIN](/windows/win32/Controls/hdm-setbitmapmargin)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

## <a name="cheaderctrlsetfilterchangetimeout"></a><a name="setfilterchangetimeout"></a> CHeaderCtrl:: SetFilterChangeTimeout

フィルター属性で変更が行われるまでのタイムアウト間隔と [HDN_FILTERCHANGE](/windows/win32/Controls/hdn-filterchange) 通知の投稿を設定します。

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>パラメーター

*dwTimeOut*<br/>
タイムアウト値 (ミリ秒単位)。

### <a name="return-value"></a>戻り値

変更されるフィルターコントロールのインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_SETFILTERCHANGETIMEOUT](/windows/win32/Controls/hdm-setfilterchangetimeout)の動作を実装します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

## <a name="cheaderctrlsetfocuseditem"></a><a name="setfocuseditem"></a> CHeaderCtrl:: SetFocusedItem

現在のヘッダーコントロール内の指定されたヘッダー項目にフォーカスを設定します。

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>パラメーター

*iItem*\
からヘッダー項目の0から始まるインデックス。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [HDM_SETFOCUSEDITEM](/windows/win32/Controls/hdm-setfocuseditem) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、 `m_headerCtrl` 現在のヘッダーコントロールにアクセスするために使用される変数を定義します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例は、 `SetFocusedItem` メソッドとメソッドを示して `GetFocusedItem` います。 コードの前のセクションでは、5つの列を持つヘッダーコントロールを作成しました。 ただし、列が表示されないようにするには、列の区切り線をドラッグします。 次の例では、を設定し、最後の列ヘッダーをフォーカス項目として確認します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

## <a name="cheaderctrlsethotdivider"></a><a name="sethotdivider"></a> CHeaderCtrl:: SetHotDivider

ヘッダー項目を手動でドラッグアンドドロップしたことを示すために、ヘッダー項目間の区分線を変更します。

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ポインターの位置。 ヘッダーコントロールは、ポインターの位置に基づいて適切な区分線を強調表示します。

*nIndex*<br/>
強調表示された区分線のインデックス。

### <a name="return-value"></a>戻り値

強調表示された区分線のインデックス。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_SETHOTDIVIDER](/windows/win32/Controls/hdm-sethotdivider)の動作を実装します。 ヘッダー項目のドラッグアンドドロップをサポートするために用意されています。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

## <a name="cheaderctrlsetimagelist"></a><a name="setimagelist"></a> CHeaderCtrl:: SetImageList

イメージリストをヘッダーコントロールに割り当てます。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
`CImageList`ヘッダーコントロールに割り当てられるイメージリストを格納しているオブジェクトへのポインター。

### <a name="return-value"></a>戻り値

以前にヘッダーコントロールに割り当てられた [CImageList](../../mfc/reference/cimagelist-class.md) オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [HDM_SETIMAGELIST](/windows/win32/Controls/hdm-setimagelist)の動作を実装します。 返された `CImageList` ポインターが指すオブジェクトは一時オブジェクトであり、次のアイドル時の処理で削除されます。

### <a name="example"></a>例

  [CHeaderCtrl:: GetImageList](#getimagelist)の例を参照してください。

## <a name="cheaderctrlsetitem"></a><a name="setitem"></a> CHeaderCtrl:: SetItem

ヘッダーコントロール内の指定された項目の属性を設定します。

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
操作する項目の0から始まるインデックス。

*pHeaderItem*<br/>
新しい項目に関する情報を格納している [HDITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) 構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [CHeaderCtrl:: GetItem](#getitem)の例を参照してください。

## <a name="cheaderctrlsetorderarray"></a><a name="setorderarray"></a> CHeaderCtrl:: SetOrderArray

ヘッダーコントロールの項目の左から右への順序を設定します。

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>パラメーター

*iCount*<br/>
ヘッダーコントロール項目の数。

*piArray*<br/>
ヘッダーコントロール内の項目のインデックス値を、左から右へと表示される順序で受け取るバッファーのアドレスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 マクロ [HDM_SETORDERARRAY](/windows/win32/Controls/hdm-setorderarray)の動作を実装します。 ヘッダー項目の順序付けをサポートするために用意されています。

### <a name="example"></a>例

  [CHeaderCtrl:: GetOrderArray](#getorderarray)の例を参照してください。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList クラス](../../mfc/reference/cimagelist-class.md)
