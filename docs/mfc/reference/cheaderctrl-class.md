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
ms.openlocfilehash: 56c694283c5143174b0ce7370d98a244c056bc1e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496019"
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
|[CHeaderCtrl::CHeaderCtrl](#cheaderctrl)|`CHeaderCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHeaderCtrl::ClearAllFilters](#clearallfilters)|ヘッダー コントロールのすべてのフィルターをクリアします。|
|[CHeaderCtrl::ClearFilter](#clearfilter)|ヘッダー コントロールのフィルターをクリアします。|
|[CHeaderCtrl::Create](#create)|ヘッダー コントロールを作成し、それにアタッチ、`CHeaderCtrl`オブジェクト。|
|[CHeaderCtrl::CreateDragImage](#createdragimage)|ヘッダー コントロール内の項目の画像の透明なバージョンを作成します。|
|[CHeaderCtrl::CreateEx](#createex)|指定した Windows の拡張スタイルを使用して、ヘッダー コントロールを作成しにアタッチします、`CListCtrl`オブジェクト。|
|[CHeaderCtrl::DeleteItem](#deleteitem)|ヘッダー コントロールから項目を削除します。|
|[CHeaderCtrl::DrawItem](#drawitem)|ヘッダー コントロールの指定した項目を描画します。|
|[CHeaderCtrl::EditFilter](#editfilter)|ヘッダー コントロールの指定したフィルターの編集を開始します。|
|[CHeaderCtrl::GetBitmapMargin](#getbitmapmargin)|ヘッダー コントロールのビットマップの余白の幅を取得します。|
|[CHeaderCtrl::GetFocusedItem](#getfocuseditem)|フォーカスがある現在のヘッダー コントロールで項目の識別子を取得します。|
|[CHeaderCtrl::GetImageList](#getimagelist)|ヘッダー コントロールの項目を描画に使用するイメージ リストのハンドルを取得します。|
|[CHeaderCtrl::GetItem](#getitem)|ヘッダー コントロールの項目に関する情報を取得します。|
|[CHeaderCtrl::GetItemCount](#getitemcount)|ヘッダー コントロールの項目の数を取得します。|
|[CHeaderCtrl::GetItemDropDownRect](#getitemdropdownrect)|ヘッダー コントロールの指定のドロップダウン ボタンの外接する四角形の情報を取得します。|
|[CHeaderCtrl::GetItemRect](#getitemrect)|ヘッダー コントロールの特定の項目の外接する四角形を取得します。|
|[CHeaderCtrl::GetOrderArray](#getorderarray)|ヘッダー コントロールの項目の左から右の順序を取得します。|
|[CHeaderCtrl::GetOverflowRect](#getoverflowrect)|現在のヘッダー コントロールのオーバーフロー ボタンの外接する四角形を取得します。|
|[CHeaderCtrl::HitTest](#hittest)|どのヘッダー項目がある場合、指定したポイントにあるかを決定します。|
|[として](#insertitem)|ヘッダー コントロールには、新しい項目を挿入します。|
|[配置](#layout)|指定した四角形内のヘッダー コントロールの位置とサイズを取得します。|
|[CHeaderCtrl::OrderToIndex](#ordertoindex)|ヘッダー コントロール内での順序に基づいて、item のインデックス値を取得します。|
|[CHeaderCtrl::SetBitmapMargin](#setbitmapmargin)|ヘッダー コントロールのビットマップの余白の幅を設定します。|
|[CHeaderCtrl::SetFilterChangeTimeout](#setfilterchangetimeout)|フィルター属性が、変更時の転記までのタイムアウト間隔を設定、`HDN_FILTERCHANGE`通知します。|
|[CHeaderCtrl::SetFocusedItem](#setfocuseditem)|現在のヘッダー コントロールの指定したヘッダー項目にフォーカスを設定します。|
|[CHeaderCtrl::SetHotDivider](#sethotdivider)|変更を手動で示すためにヘッダー項目間の境界線をドラッグし、ヘッダー項目のドロップします。|
|[CHeaderCtrl::SetImageList](#setimagelist)|イメージ リストをヘッダー コントロールに割り当てます。|
|[CHeaderCtrl::SetItem](#setitem)|ヘッダー コントロールの指定した項目の属性を設定します。|
|[CHeaderCtrl::SetOrderArray](#setorderarray)|ヘッダー コントロールの項目の左から右の順序を設定します。|

## <a name="remarks"></a>Remarks

ヘッダー コントロールは、テキストまたは数値の列のセットの上に配置された通常ウィンドウです。 各列のタイトルが含まれているし、部分に分割できる場合します。 ユーザーは、各列の幅を設定する部分を分割する区切り線をドラッグできます。 ヘッダー コントロールの図解は、次を参照してください。[ヘッダー コントロール](/windows/desktop/Controls/header-controls)します。

このコントロール (つまり、`CHeaderCtrl`クラス) は以降 Windows 95/98 および Windows NT 3.51 の下で実行するプログラムにのみ使用できます。

Windows 95/Internet Explorer 4.0 のコモン コントロールの追加機能には、次の項目が含まれます。

- ヘッダー項目の並べ替え。

- ヘッダー項目は、ドラッグ アンド ドロップ、ヘッダー項目の順序を並べ替えるため。 HDS_DRAGDROP 形式を使用して、作成するときに、`CHeaderCtrl`オブジェクト。

- ヘッダー列のテキストが列のサイズ変更時に常に表示できます。 HDS_FULLDRAG スタイルを使用して、作成するときに、`CHeaderCtrl`オブジェクト。

- ヘッダーのホット トラッキングが、ポインターが上に配置されているときにヘッダー項目を強調表示されます。 作成するときにするときを使用して、`CHeaderCtrl`オブジェクト。

- イメージ リストのサポート。 ヘッダー項目が格納されているイメージを含めることができます、`CImageList`オブジェクトまたはテキスト。

使用しての詳細については`CHeaderCtrl`を参照してください[コントロール](../../mfc/controls-mfc.md)と[を使用して CHeaderCtrl](../../mfc/using-cheaderctrl.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHeaderCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

##  <a name="cheaderctrl"></a>  CHeaderCtrl::CHeaderCtrl

`CHeaderCtrl` オブジェクトを構築します。

```
CHeaderCtrl();
```

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_1.cpp)]

##  <a name="clearallfilters"></a>  CHeaderCtrl::ClearAllFilters

ヘッダー コントロールのすべてのフィルターをクリアします。

```
BOOL ClearAllFilters();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、Win32 メッセージの動作を実装[HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter)列値は-1 で、Windows SDK で説明されているようです。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_2.cpp)]

##  <a name="clearfilter"></a>  CHeaderCtrl::ClearFilter

ヘッダー コントロールのフィルターをクリアします。

```
BOOL ClearFilter(int nColumn);
```

### <a name="parameters"></a>パラメーター

*nColumn*<br/>
列の値をクリアするフィルターを示します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、Win32 メッセージの動作を実装[HDM_CLEARFILTER](/windows/desktop/Controls/hdm-clearfilter)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_3.cpp)]

##  <a name="create"></a>  CHeaderCtrl::Create

ヘッダー コントロールを作成し、それにアタッチ、`CHeaderCtrl`オブジェクト。

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
ヘッダー コントロールのスタイルを指定します。 ヘッダー コントロールのスタイルの説明は、次を参照してください。[ヘッダー コントロールのスタイル](/windows/desktop/Controls/header-control-styles)Windows SDK に含まれています。

*rect*<br/>
ヘッダー コントロールのサイズと位置を指定します。 いずれかのことができます、 [CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトまたは[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)構造体。

*pParentWnd*<br/>
通常、ヘッダー コントロールの親ウィンドウを指定します、`CDialog`します。 NULL は指定できません。

*nID*<br/>
ヘッダー コントロールの ID を指定します

### <a name="return-value"></a>戻り値

初期化が成功した場合、0 以外の場合それ以外の場合 0 を返します。

### <a name="remarks"></a>Remarks

構築する、 `CHeaderCtrl` 2 つのステップ内のオブジェクト。 最初に、コンス トラクターを呼び出すし、呼び出して`Create`、ヘッダー コントロールを作成しにアタッチする`CHeaderCtrl`オブジェクト。

ヘッダー コントロールの位置し、サイズ変更を確認する次の一般的なコントロールのスタイルを使用するだけでなく、ヘッダー コントロールのスタイル (を参照してください[コモン コントロール スタイル](/windows/desktop/Controls/common-control-styles)詳細)。

- CCS_BOTTOM 自体を親ウィンドウのクライアント領域の下部にある位置にコントロールし、ウィンドウの幅を親と同じ幅に設定します。

- コントロールの上部に描画される CCS_NODIVIDER により 2 ピクセルは強調表示します。

- CCS_NOMOVEY では、コントロールにサイズを変更して、WM_SIZE メッセージへの応答で垂直方向にではありませんが、水平方向に移動させます。 CCS_NORESIZE スタイルを使用する場合は、このスタイルは適用されません。 ヘッダー コントロールでは、既定ではこのスタイルが適用されます。

- CCS_NOPARENTALIGN では、コントロールが上部または親ウィンドウの下部に自動的に移動できなくなります。 代わりに、コントロールは、親ウィンドウのサイズへの変更に関係なく、親ウィンドウ内の位置を保持します。 CCS_TOP または CCS_BOTTOM スタイルも使用する場合を既定の高さが調整されますが、位置と幅は変更されません。

- CCS_NORESIZE では、コントロールがその初期サイズまたは新しいサイズを設定するときに、既定の幅と高さを使用することを防ぎます。 代わりに、幅と高さの作成やサイズ変更要求で指定されたコントロールを使用します。

- CCS_TOP 自体を親ウィンドウのクライアント領域の上部にある位置をコントロールし、ウィンドウの幅を親と同じ幅に設定します。

ヘッダー コントロールに、次のウィンドウ スタイルを適用することもできます (を参照してください[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)詳細)。

- WS_CHILD は、子ウィンドウを作成します。 WS_POPUP スタイルでは使用できません。

- WS_VISIBLE は、最初に表示されているウィンドウを作成します。

- WS_DISABLED は、最初に無効になっているウィンドウを作成します。

- WS_GROUP では、最初のコントロールをユーザーに移動できます 1 つのコントロールから、[次へ] 矢印キーでコントロールのグループを指定します。 最初のコントロールが同じグループに属している後に WS_GROUP スタイルで定義されたすべてのコントロール。 WS_GROUP スタイルでは、次のコントロールは、スタイルのグループを終了し、[次へ] のグループ (は、1 つのグループの末尾が次の開始位置) を開始します。

- WS_TABSTOP を指定します任意の数のいずれかのコントロールにより、ユーザーが TAB キーを使用して移動できます。 TAB キーでは、WS_TABSTOP スタイルで指定された次のコントロールにユーザーを移動します。

コントロールで拡張ウィンドウ スタイルを使用する場合は、呼び出す[CreateEx](#createex)の代わりに`Create`します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_4.cpp)]

##  <a name="createex"></a>  CHeaderCtrl::CreateEx

コントロール (子ウィンドウ) を作成し、関連付けること、`CHeaderCtrl`オブジェクト。

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
作成されるコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧は、次を参照してください。、 *dwExStyle*パラメーターを[CreateWindowEx](/windows/desktop/api/winuser/nf-winuser-createwindowexa) Windows SDK に含まれています。

*dwStyle*<br/>
ヘッダー コントロールのスタイル。 ヘッダー コントロールのスタイルの説明は、次を参照してください。[ヘッダー コントロールのスタイル](/windows/desktop/Controls/header-control-styles)Windows SDK に含まれています。 参照してください[作成](#create)追加スタイルの一覧についてはします。

*rect*<br/>
参照を[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)のクライアント座標で、作成するには、ウィンドウの位置とサイズを記述する構造体*pParentWnd*します。

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*nID*<br/>
コントロールの子ウィンドウ ID

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

使用`CreateEx`の代わりに`Create`、Windows の拡張スタイルの先頭で指定された、Windows の拡張スタイルを適用する**WS_EX**します。

##  <a name="createdragimage"></a>  CHeaderCtrl::CreateDragImage

ヘッダー コントロール内の項目の画像の透明なバージョンを作成します。

```
CImageList* CreateDragImage(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ヘッダー コントロール内の項目の 0 から始まるインデックス。 この項目に割り当てられているイメージは、透過的なイメージの基盤です。

### <a name="return-value"></a>戻り値

ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)成功。 それ以外の場合に NULL の場合は、オブジェクト。 返された一覧には、1 つのイメージが含まれています。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_CREATEDRAGIMAGE](/windows/desktop/Controls/hdm-createdragimage)」の説明に従って、Windows SDK。 ヘッダー項目のドラッグ アンド ドロップをサポートするために提供されます。

`CImageList`返されたポインターを一時オブジェクトし、では、次のアイドル処理が削除されたオブジェクト。

##  <a name="deleteitem"></a>  CHeaderCtrl::DeleteItem

ヘッダー コントロールから項目を削除します。

```
BOOL DeleteItem(int nPos);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
削除する項目の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#5](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_5.cpp)]

##  <a name="drawitem"></a>  CHeaderCtrl::DrawItem

オーナー描画ヘッダー コントロールの変更の視覚的要素のときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
ポインターを[DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)構造体を描画する項目を記述します。

### <a name="remarks"></a>Remarks

`itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行する描画の動作を定義します。

既定では、このメンバー関数は何もしません。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CHeaderCtrl`オブジェクト。

アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバーの前に、関数が終了します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_6.cpp)]

##  <a name="editfilter"></a>  CHeaderCtrl::EditFilter

ヘッダー コントロールの指定したフィルターの編集を開始します。

```
BOOL EditFilter(
    int nColumn,
    BOOL bDiscardChanges);
```

### <a name="parameters"></a>パラメーター

*nColumn*<br/>
編集する列。

*bDiscardChanges*<br/>
ユーザーを処理する方法を指定する値は、ユーザーがフィルターの編集中の場合、変更内容の編集時に、 [HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter)メッセージを送信します。

指定する場合は TRUE をユーザーが行った変更を受け入れるように、ユーザー、または FALSE を行った変更を破棄します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、Win32 メッセージの動作を実装[HDM_EDITFILTER](/windows/desktop/Controls/hdm-editfilter)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#7](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_7.cpp)]

##  <a name="getbitmapmargin"></a>  CHeaderCtrl::GetBitmapMargin

ヘッダー コントロールのビットマップの余白の幅を取得します。

```
int GetBitmapMargin() const;
```

### <a name="return-value"></a>戻り値

ビットマップのピクセルの余白の幅。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_GETBITMAPMARGIN](/windows/desktop/Controls/hdm-getbitmapmargin)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#8](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_8.cpp)]

##  <a name="getfocuseditem"></a>  CHeaderCtrl::GetFocusedItem

現在のヘッダー コントロールでフォーカスのある項目のインデックスを取得します。

```
int GetFocusedItem() const;
```

### <a name="return-value"></a>戻り値

フォーカスがあるヘッダー項目の 0 から始まるインデックス。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [HDM_GETFOCUSEDITEM](/windows/desktop/Controls/hdm-getfocuseditem)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 `m_headerCtrl`、つまり現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例に示します、`SetFocusedItem`と`GetFocusedItem`メソッド。 コードの前のセクションでは、5 つの列のヘッダー コントロールを作成しました。 ただし、列が表示されないように、列区切り記号をドラッグできます。 次の例では、設定し、しフォーカス アイテムと最後の列ヘッダーを確認します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="getimagelist"></a>  CHeaderCtrl::GetImageList

ヘッダー コントロールの項目を描画に使用するイメージ リストのハンドルを取得します。

```
CImageList* GetImageList() const;
```

### <a name="return-value"></a>戻り値

ポインターを[CImageList](../../mfc/reference/cimagelist-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_GETIMAGELIST](/windows/desktop/Controls/hdm-getimagelist)」の説明に従って、Windows SDK。 `CImageList`返されたポインターを一時オブジェクトし、では、次のアイドル処理が削除されたオブジェクト。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#9](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_11.cpp)]

##  <a name="getitem"></a>  CHeaderCtrl::GetItem

ヘッダー コントロールの項目に関する情報を取得します。

```
BOOL GetItem(
    int nPos,
    HDITEM* pHeaderItem) const;
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
取得する項目の 0 から始まるインデックスを指定します。

*pHeaderItem*<br/>
ポインター、 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema)を新しい項目を受け取る構造体。 この構造体を併用、`InsertItem`と`SetItem`メンバー関数。 任意のフラグ設定、`mask`要素は、対応する要素の値が戻り時に正しく入力あることを確認します。 場合、`mask`要素が 0 に設定されている、他の構造体の要素の値は意味がありません。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#10](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_12.cpp)]

##  <a name="getitemcount"></a>  CHeaderCtrl::GetItemCount

ヘッダー コントロールの項目の数を取得します。

```
int GetItemCount() const;
```

### <a name="return-value"></a>戻り値

成功した場合、ヘッダー コントロール項目の数それ以外の場合 - 1。

### <a name="example"></a>例

  例をご覧ください[CHeaderCtrl::DeleteItem](#deleteitem)します。

##  <a name="getitemdropdownrect"></a>  CHeaderCtrl::GetItemDropDownRect

現在のヘッダー コントロールのヘッダー項目のドロップダウン ボタンの外接する四角形を取得します。

```
BOOL GetItemDropDownRect(
    int iItem,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iItem*|[in]スタイルがヘッダー項目の 0 から始まるインデックス。 詳細については、次を参照してください。、`fmt`のメンバー、 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema)構造体。|
|*lpRect*|[out]ポインターを[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る構造体。|

### <a name="return-value"></a>戻り値

この関数が成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [HDM_GETITEMDROPDOWNRECT](/windows/desktop/Controls/hdm-getitemdropdownrect)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 `m_headerCtrl`、つまり現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例に示します、`GetItemDropDownRect`メソッド。 コードの前のセクションでは、5 つの列のヘッダー コントロールを作成しました。 次のコード例は、ヘッダーのドロップダウン ボタン用に予約されている最初の列の場所の周囲の 3D の四角形を描画します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#2](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_13.cpp)]

##  <a name="getitemrect"></a>  CHeaderCtrl::GetItemRect

ヘッダー コントロールの特定の項目の外接する四角形を取得します。

```
BOOL GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ヘッダー コントロールの項目の 0 から始まるインデックス。

*lpRect*<br/>
アドレスへのポインターを[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメソッドは、Win32 メッセージの動作を実装[HDM_GETITEMRECT](/windows/desktop/Controls/hdm-getitemrect)」の説明に従って、Windows SDK。

##  <a name="getorderarray"></a>  CHeaderCtrl::GetOrderArray

ヘッダー コントロールの項目の左から右の順序を取得します。

```
BOOL GetOrderArray(
    LPINT piArray,
    int iCount);
```

### <a name="parameters"></a>パラメーター

*piArray*<br/>
表示される左から右へ順に、ヘッダー コントロールの項目のインデックス値を受け取るバッファーのアドレスへのポインター。

*iCount*<br/>
ヘッダー コントロールの項目の数。 負でない必要があります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_GETORDERARRAY](/windows/desktop/Controls/hdm-getorderarray)」の説明に従って、Windows SDK。 ヘッダー項目の並べ替えをサポートするために提供されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#11](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_14.cpp)]

##  <a name="getoverflowrect"></a>  CHeaderCtrl::GetOverflowRect

現在のヘッダー コントロールのオーバーフロー ボタンの外接する四角形を取得します。

```
BOOL GetOverflowRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*lpRect*|[out]ポインターを[RECT](https://msdn.microsoft.com/library/windows/desktop/dd162897)外接する四角形の情報を受け取る構造体。|

### <a name="return-value"></a>戻り値

この関数が成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

ヘッダー コントロールに同時に表示できるほど多くの項目が含まれている場合、コントロールは表示されない項目をスクロールするオーバーフロー ボタンを表示できます。 ヘッダー コントロールには、HDS_OVERFLOW と HDF_SPLITBUTTON スタイル オーバーフロー ボタンを表示する必要があります。 外接する四角形は、オーバーフロー ボタンを囲むし、オーバーフロー ボタンが表示される場合にのみ存在します。 詳細については、次を参照してください。[ヘッダー コントロールのスタイル](/windows/desktop/Controls/header-control-styles)します。

このメソッドは、送信、 [HDM_GETOVERFLOWRECT](/windows/desktop/Controls/hdm-getoverflowrect)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 `m_headerCtrl`、つまり現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例に示します、`GetOverflowRect`メソッド。 コードの前のセクションでは、5 つの列のヘッダー コントロールを作成しました。 ただし、列が表示されないように、列区切り記号をドラッグできます。 一部の列が表示されない場合、ヘッダー コントロールは、オーバーフロー ボタンを描画します。 次のコード例は、オーバーフロー ボタンの場所の周囲の 3D の四角形を描画します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#3](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_15.cpp)]

##  <a name="hittest"></a>  CHeaderCtrl::HitTest

どのヘッダー項目がある場合、指定したポイントにあるかを決定します。

```
int HitTest(LPHDHITTESTINFO* phdhti);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*phdhti*|[入力、出力]ポインターを[HDHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-_hd_hittestinfo)をテストする点を指定し、テストの結果を受け取る構造体。|

### <a name="return-value"></a>戻り値

指定した位置に存在する場合、ヘッダー項目の 0 から始まるインデックスそれ以外の場合、-1 を返します。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [HDM_HITTEST](/windows/desktop/Controls/hdm-hittest)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 `m_headerCtrl`、つまり現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例に示します、`HitTest`メソッド。 このコード例の前のセクションでは、5 つの列のヘッダー コントロールを作成しました。 ただし、列が表示されないように、列区切り記号をドラッグできます。 この例は、表示されている場合に、列のインデックスをレポートし、列が表示されていない場合は-1。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#1](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_16.cpp)]

##  <a name="insertitem"></a>  として

指定したインデックス位置にあるヘッダー コントロールには、新しい項目を挿入します。

```
int InsertItem(
    int nPos,
    HDITEM* phdi);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
挿入する項目の 0 から始まるインデックス。 値が 0 の場合は、ヘッダー コントロールの先頭に、項目が挿入されます。 値が最大値より大きい場合は、ヘッダー コントロールの最後に、項目が挿入されます。

*phdi*<br/>
ポインター、 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema)を挿入する項目に関する情報を含む構造体。

### <a name="return-value"></a>戻り値

成功した場合は、新しい項目のインデックスそれ以外の場合 - 1。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#12](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_17.cpp)]

##  <a name="layout"></a>  配置

指定した四角形内のヘッダー コントロールの位置とサイズを取得します。

```
BOOL Layout(HDLAYOUT* pHeaderLayout);
```

### <a name="parameters"></a>パラメーター

*pHeaderLayout*<br/>
ポインター、 [HDLAYOUT](/windows/desktop/api/commctrl/ns-commctrl-_hd_layout)構造体は、ヘッダー コントロールの位置とサイズを設定するための情報が含まれています。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

この関数を使用して、指定した四角形を占有するようにある新しいヘッダー コントロールの適切な大きさを決定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#13](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_18.cpp)]

##  <a name="ordertoindex"></a>  CHeaderCtrl::OrderToIndex

ヘッダー コントロール内での順序に基づいて、item のインデックス値を取得します。

```
int OrderToIndex(int nOrder) const;
```

### <a name="parameters"></a>パラメーター

*nOrder*<br/>
アイテムをヘッダー コントロールで、左から右へ表示する 0 から始まる順序。

### <a name="return-value"></a>戻り値

ヘッダー コントロール内での順序に基づいて、項目のインデックス。 インデックスの数は、左から右、0 から始まるをします。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 のマクロの動作を実装[HDM_ORDERTOINDEX](https://msdn.microsoft.com/library/windows/desktop/bb775355)」の説明に従って、Windows SDK。 ヘッダー項目の並べ替えをサポートするために提供されます。

##  <a name="setbitmapmargin"></a>  CHeaderCtrl::SetBitmapMargin

ヘッダー コントロールのビットマップの余白の幅を設定します。

```
int SetBitmapMargin(int nWidth);
```

### <a name="parameters"></a>パラメーター

*nWidth*<br/>
既存のヘッダー コントロール内にあるビットマップの周囲の余白 (ピクセル) で指定された幅。

### <a name="return-value"></a>戻り値

ビットマップのピクセルの余白の幅。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_SETBITMAPMARGIN](/windows/desktop/Controls/hdm-setbitmapmargin)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#14](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_19.cpp)]

##  <a name="setfilterchangetimeout"></a>  CHeaderCtrl::SetFilterChangeTimeout

フィルター属性が、変更時の転記までのタイムアウト間隔を設定、[から](/windows/desktop/Controls/hdn-filterchange)通知します。

```
int SetFilterChangeTimeout(DWORD dwTimeOut);
```

### <a name="parameters"></a>パラメーター

*dwTimeOut*<br/>
タイムアウト値 (ミリ秒)。

### <a name="return-value"></a>戻り値

変更されるフィルター コントロールのインデックス。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_SETFILTERCHANGETIMEOUT](/windows/desktop/Controls/hdm-setfilterchangetimeout)」の説明に従って、Windows SDK。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#15](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_20.cpp)]

##  <a name="setfocuseditem"></a>  CHeaderCtrl::SetFocusedItem

現在のヘッダー コントロールの指定したヘッダー項目にフォーカスを設定します。

```
BOOL SetFocusedItem(int iItem);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*iItem*|[in]ヘッダー項目の 0 から始まるインデックス。|

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、送信、 [HDM_SETFOCUSEDITEM](/windows/desktop/Controls/hdm-setfocuseditem)メッセージは、Windows SDK で説明します。

### <a name="example"></a>例

次のコード例は、変数を定義します。 `m_headerCtrl`、つまり現在のヘッダー コントロールにアクセスするために使用します。 この変数は次の例で使用されています。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#6](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_9.h)]

### <a name="example"></a>例

次のコード例に示します、`SetFocusedItem`と`GetFocusedItem`メソッド。 コードの前のセクションでは、5 つの列のヘッダー コントロールを作成しました。 ただし、列が表示されないように、列区切り記号をドラッグできます。 次の例では、設定し、しフォーカス アイテムと最後の列ヘッダーを確認します。

[!code-cpp[NVC_MFC_CHeaderCtrl_s4#4](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_10.cpp)]

##  <a name="sethotdivider"></a>  CHeaderCtrl::SetHotDivider

変更を手動で示すためにヘッダー項目間の境界線をドラッグし、ヘッダー項目のドロップします。

```
int SetHotDivider(CPoint pt);
int SetHotDivider(int nIndex);
```

### <a name="parameters"></a>パラメーター

*pt*<br/>
ポインターの位置。 ヘッダー コントロールには、ポインターの位置に基づいて適切な区分線が強調表示されます。

*nIndex*<br/>
強調表示されている区分線のインデックス。

### <a name="return-value"></a>戻り値

強調表示されている区分線のインデックス。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_SETHOTDIVIDER](/windows/desktop/Controls/hdm-sethotdivider)」の説明に従って、Windows SDK。 ヘッダー項目のドラッグ アンド ドロップをサポートするために提供されます。

### <a name="example"></a>例

[!code-cpp[NVC_MFC_CHeaderCtrl#16](../../mfc/reference/codesnippet/cpp/cheaderctrl-class_21.cpp)]

##  <a name="setimagelist"></a>  CHeaderCtrl::SetImageList

イメージ リストをヘッダー コントロールに割り当てます。

```
CImageList* SetImageList(CImageList* pImageList);
```

### <a name="parameters"></a>パラメーター

*pImageList*<br/>
ポインターを`CImageList`ヘッダー コントロールに割り当てられるイメージ リストを含むオブジェクト。

### <a name="return-value"></a>戻り値

ポインター、 [CImageList](../../mfc/reference/cimagelist-class.md)ヘッダー コントロールに割り当てられているオブジェクト。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 メッセージの動作を実装[HDM_SETIMAGELIST](/windows/desktop/Controls/hdm-setimagelist)」の説明に従って、Windows SDK。 `CImageList`返されたポインターを一時オブジェクトし、では、次のアイドル処理が削除されたオブジェクト。

### <a name="example"></a>例

  例をご覧ください[CHeaderCtrl::GetImageList](#getimagelist)します。

##  <a name="setitem"></a>  CHeaderCtrl::SetItem

ヘッダー コントロールの指定した項目の属性を設定します。

```
BOOL SetItem(
    int nPos,
    HDITEM* pHeaderItem);
```

### <a name="parameters"></a>パラメーター

*nPos*<br/>
操作する項目の 0 から始まるインデックス。

*pHeaderItem*<br/>
ポインター、 [HDITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema)新しい項目の情報を含む構造体。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CHeaderCtrl::GetItem](#getitem)します。

##  <a name="setorderarray"></a>  CHeaderCtrl::SetOrderArray

ヘッダー コントロールの項目の左から右の順序を設定します。

```
BOOL SetOrderArray(
    int iCount,
    LPINT piArray);
```

### <a name="parameters"></a>パラメーター

*iCount*<br/>
ヘッダー コントロールの項目の数。

*piArray*<br/>
表示される左から右へ順に、ヘッダー コントロールの項目のインデックス値を受け取るバッファーのアドレスへのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

このメンバー関数は、Win32 のマクロの動作を実装[HDM_SETORDERARRAY](/windows/desktop/Controls/hdm-setorderarray)」の説明に従って、Windows SDK。 ヘッダー項目の並べ替えをサポートするために提供されます。

### <a name="example"></a>例

  例をご覧ください[CHeaderCtrl::GetOrderArray](#getorderarray)します。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CTabCtrl クラス](../../mfc/reference/ctabctrl-class.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)<br/>
[CImageList クラス](../../mfc/reference/cimagelist-class.md)
