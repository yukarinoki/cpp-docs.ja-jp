---
title: CToolBar クラス
ms.date: 11/04/2016
f1_keywords:
- CToolBar
- AFXEXT/CToolBar
- AFXEXT/CToolBar::CToolBar
- AFXEXT/CToolBar::CommandToIndex
- AFXEXT/CToolBar::Create
- AFXEXT/CToolBar::CreateEx
- AFXEXT/CToolBar::GetButtonInfo
- AFXEXT/CToolBar::GetButtonStyle
- AFXEXT/CToolBar::GetButtonText
- AFXEXT/CToolBar::GetItemID
- AFXEXT/CToolBar::GetItemRect
- AFXEXT/CToolBar::GetToolBarCtrl
- AFXEXT/CToolBar::LoadBitmap
- AFXEXT/CToolBar::LoadToolBar
- AFXEXT/CToolBar::SetBitmap
- AFXEXT/CToolBar::SetButtonInfo
- AFXEXT/CToolBar::SetButtons
- AFXEXT/CToolBar::SetButtonStyle
- AFXEXT/CToolBar::SetButtonText
- AFXEXT/CToolBar::SetHeight
- AFXEXT/CToolBar::SetSizes
helpviewer_keywords:
- CToolBar [MFC], CToolBar
- CToolBar [MFC], CommandToIndex
- CToolBar [MFC], Create
- CToolBar [MFC], CreateEx
- CToolBar [MFC], GetButtonInfo
- CToolBar [MFC], GetButtonStyle
- CToolBar [MFC], GetButtonText
- CToolBar [MFC], GetItemID
- CToolBar [MFC], GetItemRect
- CToolBar [MFC], GetToolBarCtrl
- CToolBar [MFC], LoadBitmap
- CToolBar [MFC], LoadToolBar
- CToolBar [MFC], SetBitmap
- CToolBar [MFC], SetButtonInfo
- CToolBar [MFC], SetButtons
- CToolBar [MFC], SetButtonStyle
- CToolBar [MFC], SetButtonText
- CToolBar [MFC], SetHeight
- CToolBar [MFC], SetSizes
ms.assetid: e868da26-5e07-4607-9651-e2f863ad9059
ms.openlocfilehash: aa49ebed2d48d9818c2d39ae4894d8caf1fbbf81
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773139"
---
# <a name="ctoolbar-class"></a>CToolBar クラス

一連のビットマップ ボタンおよびオプションの区切り記号を含むコントロール バーです。

## <a name="syntax"></a>構文

```
class CToolBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CToolBar::CToolBar](#ctoolbar)|`CToolBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CToolBar::CommandToIndex](#commandtoindex)|指定されたコマンド ID を持つボタンのインデックスを返します|
|[CToolBar::Create](#create)|Windows ツールバーを作成しにアタッチします、`CToolBar`オブジェクト。|
|[CToolBar::CreateEx](#createex)|作成、 `CToolBar` 、埋め込みの追加のスタイルを使用してオブジェクト`CToolBarCtrl`オブジェクト。|
|[CToolBar::GetButtonInfo](#getbuttoninfo)|ID、スタイル、およびボタンのイメージ数を取得します。|
|[CToolBar::GetButtonStyle](#getbuttonstyle)|ボタンのスタイルを取得します。|
|[CToolBar::GetButtonText](#getbuttontext)|ボタンに表示されるテキストを取得します。|
|[CToolBar::GetItemID](#getitemid)|ボタンまたは指定したインデックス位置にある区切り記号のコマンド ID を返します。|
|[CToolBar::GetItemRect](#getitemrect)|指定したインデックス位置にある項目を表示する四角形を取得します。|
|[CToolBar::GetToolBarCtrl](#gettoolbarctrl)|基になる一般的なコントロールに直接アクセスをできます。|
|[CToolBar::LoadBitmap](#loadbitmap)|ビットマップ ボタンの画像を含むビットマップを読み込みます。|
|[CToolBar::LoadToolBar](#loadtoolbar)|リソース エディターで作成されたツール バー リソースを読み込みます。|
|[CToolBar::SetBitmap](#setbitmap)|ビットマップ イメージを設定します。|
|[CToolBar::SetButtonInfo](#setbuttoninfo)|ID、スタイル、およびボタンのイメージ数を設定します。|
|[CToolBar::SetButtons](#setbuttons)|ボタンのスタイルとボタンのイメージ、ビットマップ内のインデックスを設定します。|
|[CToolBar::SetButtonStyle](#setbuttonstyle)|ボタンのスタイルを設定します。|
|[CToolBar::SetButtonText](#setbuttontext)|ボタンの上に表示されるテキストを設定します。|
|[CToolBar::SetHeight](#setheight)|ツールバーの高さを設定します。|
|[CToolBar::SetSizes](#setsizes)|ボタンとビットマップのサイズを設定します。|

## <a name="remarks"></a>Remarks

ボタンは、プッシュ ボタン、チェック ボックス ボタン、またはラジオ ボタンのように動作します。 `CToolBar` オブジェクトはクラスから派生したフレーム ウィンドウ オブジェクトの通常の埋め込みメンバー [CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)します。

[CToolBar::GetToolBarCtrl](#gettoolbarctrl)、メンバー関数は、新しい MFC 4.0 では、することができます ツールバーのカスタマイズなどの追加機能の Windows コモン コントロールのサポートを活用します。 `CToolBar` メンバー関数は、ほとんどの Windows コモン コントロール以外の機能を提供します。ただし、呼び出す`GetToolBarCtrl`、Windows 95/98 ツールバーの特性のさらに多くのツールバーを付けることができます。 呼び出すと`GetToolBarCtrl`への参照が返されます、`CToolBarCtrl`オブジェクト。 参照してください[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)詳細については、Windows のコモン コントロールを使用してツールバーを設計します。 コモン コントロールの概要については、次を参照してください。[コモン コントロール](/windows/desktop/Controls/common-controls-intro)Windows SDK に含まれています。

Visual C は、ツールバーを作成する 2 つのメソッドを提供します。 リソース エディターを使用してツール バー リソースを作成するには、次の手順を実行します。

1. ツール バー リソースを作成します。

1. 構築、`CToolBar`オブジェクト。

1. 呼び出す、[作成](#create)(または[CreateEx](#createex)) を Windows ツールバーを作成し、アタッチ先、`CToolBar`オブジェクト。

1. 呼び出す[LoadToolBar](#loadtoolbar)ツール バー リソースを読み込めません。

それ以外の場合、これらの手順に従います。

1. 構築、`CToolBar`オブジェクト。

1. 呼び出す、[作成](#create)(または[CreateEx](#createex)) を Windows ツールバーを作成し、アタッチ先、`CToolBar`オブジェクト。

1. 呼び出す[LoadBitmap](#loadbitmap)ツール バー ボタンのイメージを含むビットマップを読み込みます。

1. 呼び出す[SetButtons](#setbuttons)ボタン スタイルを設定し、各ボタンをビットマップ内のイメージに関連付けます。

ツールバーのボタンのイメージをすべては、1 つのビットマップは、各ボタンの 1 つのイメージを含める必要がありますから取得されます。 すべてのイメージは同じサイズにする必要があります。既定では、幅 16 ピクセル、高さ 15 ピクセルです。 イメージは、ビットマップ内で並行してある必要があります。

`SetButtons`関数は、コントロール Id と、配列内の要素の数を指定する整数の配列へのポインターを受け取ります。 関数は、各ボタンの ID は、配列の対応する要素の値を設定し、各ボタンにビットマップのボタンの画像の位置を指定するイメージのインデックスを割り当てます。 配列の要素がある、値として、イメージのインデックスは割り当てられません。

ビットマップ内のイメージの順序は、通常、画面に描画されますが、使用することができます、[です](#setbuttoninfo)イメージ順序と描画順序との間のリレーションシップを変更する関数。

ツールバー内のすべてのボタンは、同じサイズです。 既定値に従って、24 x 22 ピクセルは*ソフトウェア設計の Windows のインターフェイス ガイドライン*します。 イメージとボタンのディメンション間でさらに空き領域を使用して、イメージの周りに罫線を形成します。

各ボタンは、1 つのイメージです。 ボタンのさまざまな状態と、スタイル (押された、up、down、無効になっている、ダウン、無効になっており中間) は、その 1 つのイメージから生成されます。 ビットマップできますが、任意の色は黒、灰色の網掛けでイメージの最良の結果を実現できます。

> [!WARNING]
> `CToolBar` 最大 16 色のビットマップをサポートしています。 ツール バー エディターからイメージを読み込むときに、Visual Studio は自動的に必要に応じて、16 色のビットマップにイメージを変換し、イメージが変換された場合に警告メッセージが表示されます。 (画像を編集するのには外部エディターを使用して) 複数の 16 色でイメージを使用する場合は、アプリケーションが予期しない動作可能性があります。

ツールバーのボタンは、既定でプッシュ ボタンを模倣します。 ただし、チェック ボックスまたはラジオ ボタン ツールバーのボタンを模倣こともできます。 チェック ボックス ボタンがある 3 つの状態: オン、オフで、不確定です。 ラジオ ボタンがある 2 つの状態: オンおよびオフにします。

配列を指すことがなく、個々 のボタンまたは区分線のスタイルを設定するには、呼び出す[に](#getbuttonstyle)、スタイルを取得し、呼び出す[SetButtonStyle](#setbuttonstyle)の代わりに`SetButtons`します。 `SetButtonStyle` 実行時にボタンのスタイルを変更するときに最も役立ちます。

ボタンに表示されるテキストに割り当てるには、呼び出す[GetButtonText](#getbuttontext) 、ボタンに表示し、呼び出すテキストを取得する[SetButtonText](#setbuttontext)テキストを設定します。

チェック ボックス ボタンを作成、TBBS_CHECKBOX スタイルを割り当てる、または使用を`CCmdUI`オブジェクトの`SetCheck`ON_UPDATE_COMMAND_UI ハンドラー内のメンバー関数。 呼び出す`SetCheck`チェック ボックス ボタンにプッシュ ボタンをオンにします。 渡す`SetCheck`引数が 0 のチェック、または 2 つのチェックを行わない、1 の不確定です。

ラジオ ボタンを作成するには、 [CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトの[SetRadio](../../mfc/reference/ccmdui-class.md#setradio) ON_UPDATE_COMMAND_UI ハンドラーからのメンバー関数。 渡す`SetRadio`オフまたは以外の引数が 0 の。 ラジオ グループの相互に排他的な動作を提供するために、グループ内のすべてのボタンに対してが必要です。

使用しての詳細については`CToolBar`、記事をご覧ください[MFC ツールバーの実装](../../mfc/mfc-toolbar-implementation.md)と[テクニカル ノート 31。コントロール バー](../../mfc/tn031-control-bars.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

##  <a name="commandtoindex"></a>  CToolBar::CommandToIndex

このメンバー関数は、ツールバー、最初のボタンの位置 0、コマンド id のインデックスを返します`nIDFind`します。

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>パラメーター

*nIDFind*<br/>
ツール バー ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

ボタン、またはボタンに指定されたコマンド ID があるない場合は-1 のインデックス

##  <a name="create"></a>  CToolBar::Create

このメンバー関数は、Windows ツールバー (子ウィンドウ) を作成しに関連付けます、`CToolBar`オブジェクト。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ツールバーの親ウィンドウへのポインター。

*dwStyle*<br/>
ツールバーのスタイル。 追加のスタイルは次のとおりです。

- CBRS_TOP コントロール バーは、フレーム ウィンドウの上部にあること。

- CBRS_BOTTOM コントロール バーでは、フレーム ウィンドウの下部にあります。

- 親のサイズが変更されたときに CBRS_NOALIGN コントロール バーの位置を変更できません。

- CBRS_TOOLTIPS コントロール バーには、ツール ヒントが表示されます。

- CBRS_SIZE_DYNAMIC コントロール バーは動的です。

- CBRS_SIZE_FIXED コントロール バーは固定されています。

- CBRS_FLOATING コントロール バーがフローティングします。

- CBRS_FLYBY ステータス バーには、ボタンに関する情報が表示されます。

- CBRS_HIDE_INPLACE コントロール バーがユーザーに表示されません。

*nID*<br/>
ツールバーの子ウィンドウの id。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

また、ツールバーの高さを既定値に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

##  <a name="createex"></a>  CToolBar::CreateEx

Windows ツールバー (子ウィンドウ) を作成し、それをするには、この関数を呼び出して、`CToolBar`オブジェクト。

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = TBSTYLE_FLAT,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_ALIGN_TOP,
    CRect rcBorders = CRect(
    0,
    0,
    0,
    0),
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ツールバーの親ウィンドウへのポインター。

*dwCtrlStyle*<br/>
埋め込まれたを作成するための追加スタイル[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)オブジェクト。 既定では、この値は TBSTYLE_FLAT に設定します。 ツール バー スタイルの完全な一覧を参照してください。 *dwStyle*します。

*dwStyle*<br/>
ツールバーのスタイル。 参照してください[ツール バー コントロールとボタンのスタイル](/windows/desktop/Controls/toolbar-control-and-button-styles)適切なスタイルの一覧については、Windows SDK に含まれています。

*rcBorders*<br/>
A [CRect](../../atl-mfc-shared/reference/crect-class.md)ウィンドウのツールバーの境界線の幅を定義するオブジェクト。 これらの罫線は、境界線なしで、ツールバーのウィンドウで、既定で 0,0,0,0 に設定されます。

*nID*<br/>
ツールバーの子ウィンドウの id。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

また、ツールバーの高さを既定値に設定します。

使用`CreateEx`の代わりに[作成](#create)、特定のスタイルを組み込みのツール バー コントロールの作成中に存在する必要があります。 たとえば、設定*ツール バー* TBSTYLE_FLAT に&#124;バーオブジェクト Internet Explorer 4 ツールバーのようなツールバーを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

##  <a name="ctoolbar"></a>  CToolBar::CToolBar

このメンバー関数を作成、`CToolBar`オブジェクトおよび既定のサイズを設定します。

```
CToolBar();
```

### <a name="remarks"></a>Remarks

呼び出す、[作成](#create)メンバー関数は、[ツールバー] ウィンドウを作成します。

##  <a name="getbuttoninfo"></a>  CToolBar::GetButtonInfo

このメンバー関数は、コントロールの ID、スタイル、およびツール バー ボタンまたはで指定された場所に区切り線のイメージのインデックスを取得します。 *nIndex します。*

```
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
区切り記号を取得する情報を持つは、ツール バー ボタンのインデックス。

*nID*<br/>
ボタンのコマンド ID に設定されている UINT への参照。

*nStyle*<br/>
ボタンのスタイルに設定されている UINT への参照。

*画像を*<br/>
ボタンのイメージ、ビットマップ内のインデックスに設定されている整数への参照。

### <a name="remarks"></a>Remarks

これらの値がによって参照される変数に割り当てられている*nID*、 *nStyle*、および*画像を*します。 イメージのインデックスは、すべてのツール バー ボタンのイメージを含む、ビットマップ内の画像の位置です。 最初のイメージが 0 の位置です。

場合*nIndex* 、区切り記号を指定します*画像を*区切り記号の幅 (ピクセル単位) に設定されます。

##  <a name="getbuttonstyle"></a>  CToolBar::GetButtonStyle

ボタンまたはツールバーの区切り記号のスタイルを取得するには、このメンバー関数を呼び出します。

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得するツールバーのボタンまたは区切り記号のスタイルのインデックス。

### <a name="return-value"></a>戻り値

ボタンまたはで指定された区切り記号のスタイル*nIndex*します。

### <a name="remarks"></a>Remarks

ボタンのスタイルは、ボタンの表示方法と、ユーザー入力への応答方法を決定します。 参照してください[SetButtonStyle](#setbuttonstyle)ボタンのスタイルの例についてはします。

##  <a name="getbuttontext"></a>  CToolBar::GetButtonText

ボタンに表示されるテキストを取得するには、このメンバー関数を呼び出します。

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得するテキストのインデックス。

*rString*<br/>
参照を[CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得するテキストを格納するオブジェクト。

### <a name="return-value"></a>戻り値

A`CString`ボタンのテキストを含むオブジェクト。

### <a name="remarks"></a>Remarks

このメンバーの 2 番目の形式の関数の塗りつぶしを`CString`文字列テキストを含むオブジェクト。

##  <a name="getitemid"></a>  CToolBar::GetItemID

このメンバー関数は、ボタンまたはで指定された区切り記号のコマンド ID を返します*nIndex*します。

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ID が取得される項目のインデックス。

### <a name="return-value"></a>戻り値

ボタンまたはで指定された区切り記号のコマンド ID *nIndex*します。

### <a name="remarks"></a>Remarks

区切り記号としてを返します。

##  <a name="getitemrect"></a>  CToolBar::GetItemRect

このメンバー関数、`RECT`構造内のアドレスを持つ*lpRect*ボタンまたはで指定された区切り記号の座標を持つ*nIndex*します。

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
四角形の座標の項目 (ボタンまたは区切り記号) のインデックスでは、取得します。

*lpRect*<br/>
アドレス、 [RECT](/windows/desktop/api/windef/ns-windef-tagrect)アイテムの座標を格納する構造体。

### <a name="remarks"></a>Remarks

座標は、ツールバーの左上隅に対して相対的 (ピクセル単位)。

使用`GetItemRect`コンボ ボックスまたは他のコントロールを置換する区切り記号の座標を取得します。

### <a name="example"></a>例

  例をご覧ください[CToolBar::SetSizes](#setsizes)します。

##  <a name="gettoolbarctrl"></a>  CToolBar::GetToolBarCtrl

このメンバー関数は、基になる一般的なコントロールに直接アクセスをできます。

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>戻り値

`CToolBarCtrl` オブジェクトへの参照。

### <a name="remarks"></a>Remarks

使用`GetToolBarCtrl`Windows ツール バー コモン コントロールの機能を活用して、サポートを活用するために[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)ツールバーのカスタマイズを提供します。

コモン コントロールの使い方の詳細については、この記事を参照してください。[コントロール](../../mfc/controls-mfc.md)と[コモン コントロール](/windows/desktop/Controls/common-controls-intro)Windows SDK に含まれています。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

##  <a name="loadbitmap"></a>  CToolBar::LoadBitmap

指定されたビットマップを読み込むには、このメンバー関数を呼び出す`lpszResourceName`または`nIDResource`します。

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
読み込むビットマップのリソース名へのポインター。

*可能*<br/>
リソースを読み込むには、ビットマップの ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

ビットマップは、各ツール バー ボタンの 1 つのイメージを含める必要があります。 イメージがない場合、標準のサイズ (幅 16 ピクセル、高さ 15 ピクセル) の呼び出し[SetSizes](#setsizes)ボタンのサイズとそのイメージを設定します。

> [!WARNING]
> `CToolBar` 最大 16 色のビットマップをサポートしています。 ツール バー エディターからイメージを読み込むときに、Visual Studio は自動的に必要に応じて、16 色のビットマップにイメージを変換し、イメージが変換された場合に警告メッセージが表示されます。 (画像を編集するのには外部エディターを使用して) 複数の 16 色でイメージを使用する場合は、アプリケーションが予期しない動作可能性があります。

##  <a name="loadtoolbar"></a>  CToolBar::LoadToolBar

指定されたツールバーを読み込むには、このメンバー関数を呼び出す*lpszResourceName*または*可能*します。

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*lpszResourceName*<br/>
読み込まれる、ツールバーのリソース名へのポインター。

*可能*<br/>
リソースを読み込むには、ツールバーの ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

参照してください[ツール バー エディター](../../windows/toolbar-editor.md)の詳細については、ツール バー リソースを作成します。

### <a name="example"></a>例

  例をご覧ください[CToolBar::CreateEx](#createex)します。

##  <a name="setbitmap"></a>  CToolBar::SetBitmap

ツールバーのビットマップ イメージを設定するには、このメンバー関数を呼び出します。

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>パラメーター

*hbmImageWell*<br/>
ツールバーに関連付けられているビットマップ イメージのハンドル。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

たとえば、呼び出す`SetBitmap`ユーザーが実行する、ボタンの動作を変更するドキュメントの後に、ビットマップ イメージを変更します。

##  <a name="setbuttoninfo"></a>  CToolBar::SetButtonInfo

ボタンのコマンド ID、スタイル、およびイメージの数を設定するには、このメンバー関数を呼び出します。

```
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ボタンまたは情報を設定する対象の区切り記号の 0 から始まるインデックス。

*nID*<br/>
ボタンのコマンド ID に設定する値。

*nStyle*<br/>
新しいボタン スタイル。 次のボタンのスタイルがサポートされています。

- TBBS_BUTTON 標準プッシュ ボタン (既定値)

- TBBS_SEPARATOR 区切り記号

- TBBS_CHECKBOX 自動チェック ボックス ボタン

- ボタンのグループの先頭に TBBS_GROUP

- チェック ボックス ボタンのグループの先頭に TBBS_CHECKGROUP

- TBBS_DROPDOWN は、ドロップダウン リスト ボタンを作成します。

- イメージのサイズではなく、ボタンのテキストに基づいています TBBS_AUTOSIZE ボタンの幅を計算します。

- TBBS_NOPREFIX ボタンのテキストでは、関連付けられているアクセラレータ プレフィックスを持ちません。

*画像を*<br/>
ボタンのイメージ、ビットマップ内の新しいインデックス。

### <a name="remarks"></a>Remarks

スタイル TBBS_SEPARATOR がある、区切り記号としてこの関数はピクセル単位で格納されている値の区切り記号の幅を設定*画像を*します。

> [!NOTE]
>  使用してボタンの状態を設定することも、 *nStyle*パラメーターですただし、ボタンの状態によって制御されるため、 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)ハンドラーでは、すべての状態を使用して設定する`SetButtonInfo`は失われます。次の中にアイドル プロセス。 参照してください[ユーザー インターフェイス オブジェクトを更新する方法](../../mfc/how-to-update-user-interface-objects.md)と[TN031:コントロール バー](../../mfc/tn031-control-bars.md)詳細についてはします。

ビットマップ イメージやボタンについては、次を参照してください。、 [CToolBar](../../mfc/reference/ctoolbar-class.md)の概要と[CToolBar::LoadBitmap](#loadbitmap)します。

##  <a name="setbuttons"></a>  CToolBar::SetButtons

このメンバー関数は、配列の対応する要素で指定された値を各ツール バー ボタンのコマンド ID を設定する*lpIDArray*します。

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>パラメーター

*lpIDArray*<br/>
コマンド Id の配列へのポインター。 NULL は空のボタンを割り当てることがあります。

*nIDCount*<br/>
配列内の要素の数が指す*lpIDArray*します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

値として、配列の要素の場合は、区切り記号は、ツールバーの対応する位置に作成されます。 この関数は、各ボタンのスタイル TBBS_BUTTON と TBBS_SEPARATOR に各区切り記号のスタイルを設定し、各ボタンにイメージ インデックスを割り当てます。 イメージのインデックスでは、ボタンのイメージ、ビットマップ内の位置を指定します。

ビットマップの区切り記号のため、この関数は区切り記号にイメージのインデックスを割り当てませんを考慮する必要はありません。 場合は、ツールバーは、0 の位置にあるボタンを持つ、1、3 と、位置 2、イメージ、ビットマップ内の位置 0、1、および 2 の区切り記号に割り当てられているボタンの位置の 0、1、および 3 では、それぞれします。

場合*lpIDArray*が null の場合、この関数で指定された項目の数の領域を割り当てます*nIDCount*します。 使用[です](#setbuttoninfo)各項目の属性を設定します。

##  <a name="setbuttonstyle"></a>  CToolBar::SetButtonStyle

ボタンまたは区切り記号、またはボタンをグループ化のスタイルを設定するには、このメンバー関数を呼び出します。

```
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ボタンの情報が設定される区切り記号のインデックス。

*nStyle*<br/>
ボタンのスタイル。 次のボタンのスタイルがサポートされています。

- TBBS_BUTTON 標準プッシュ ボタン (既定値)

- TBBS_SEPARATOR 区切り記号

- TBBS_CHECKBOX 自動チェック ボックス ボタン

- ボタンのグループの先頭に TBBS_GROUP

- チェック ボックス ボタンのグループの先頭に TBBS_CHECKGROUP

- TBBS_DROPDOWN は、ドロップダウン リスト ボタンを作成します。

- イメージのサイズではなく、ボタンのテキストに基づいて TBBS_AUTOSIZE ボタンの幅を計算します

- TBBS_NOPREFIX ボタンのテキストは、関連付けられているアクセラレータ プレフィックスをありません。

### <a name="remarks"></a>Remarks

ボタンのスタイルは、ボタンの表示方法と、ユーザー入力への応答方法を決定します。

呼び出しの前に`SetButtonStyle`を呼び出し、[に](#getbuttonstyle)ボタンまたは区切り記号のスタイルを取得します。

> [!NOTE]
>  使用してボタンの状態を設定することも、 *nStyle*パラメーターですただし、ボタンの状態によって制御されるため、 [ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)ハンドラーでは、すべての状態を使用して設定する`SetButtonStyle`は失われます。次の中にアイドル プロセス。 参照してください[ユーザー インターフェイス オブジェクトを更新する方法](../../mfc/how-to-update-user-interface-objects.md)と[TN031:コントロール バー](../../mfc/tn031-control-bars.md)詳細についてはします。

##  <a name="setbuttontext"></a>  CToolBar::SetButtonText

ボタンのテキストを設定するには、この関数を呼び出します。

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
テキストを設定するボタンのインデックス。

*lpszText*<br/>
ボタンに設定するテキストを指します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  例をご覧ください[CToolBar::GetToolBarCtrl](#gettoolbarctrl)します。

##  <a name="setheight"></a>  CToolBar::SetHeight

このメンバー関数は、ツールバーの高さをピクセル単位で指定された値に設定*cyHeight*します。

```
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>パラメーター

*cyHeight*<br/>
ツールバーのピクセル単位の高さ。

### <a name="remarks"></a>Remarks

呼び出した後[SetSizes](#setsizes)、標準ツールバーの高さをオーバーライドするこのメンバー関数を使用します。 高さが小さすぎる場合は、下部にあるボタンがクリップされます。

この関数が呼び出されない場合、フレームワーク、ボタンのサイズを使用して、ツールバーの高さを決定します。

##  <a name="setsizes"></a>  CToolBar::SetSizes

ツールバーのボタンをピクセル単位で指定されたサイズに設定するには、このメンバー関数を呼び出す*sizeButton*します。

```
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>パラメーター

*sizeButton*<br/>
各ボタンのピクセル単位のサイズ。

*sizeImage*<br/>
各イメージのピクセル単位のサイズ。

### <a name="remarks"></a>Remarks

*SizeImage*パラメーターは、ツールバーのビットマップ内のイメージのピクセル単位でサイズを含める必要があります。 内のディメンション*sizeButton*イメージに加え 7 ピクセル幅、および 6 ピクセルの高さを保持するのに十分である必要があります。 この関数はまた、ツールバーのボタンの高さの高さを設定します。

このメンバー関数に従っていないツールバーに対してのみ*ソフトウェア設計の Windows のインターフェイス ガイドライン*ボタンとイメージのサイズに関する推奨事項。

### <a name="example"></a>例

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル DOCKTOOL](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
