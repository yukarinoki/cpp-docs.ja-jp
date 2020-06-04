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
ms.openlocfilehash: cbb2d1bb797737a14e9728d339305bf9c371b543
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752207"
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
|[Cツールバー::Cツールバー](#ctoolbar)|`CToolBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cツールバー::コマンドインデックス](#commandtoindex)|指定されたコマンド ID を持つボタンのインデックスを返します。|
|[Cツールバー::作成](#create)|Windows ツール バーを作成し、オブジェクト`CToolBar`にアタッチします。|
|[Cツールバー::作成します。](#createex)|埋め`CToolBar`込み`CToolBarCtrl`オブジェクトの追加スタイルを持つオブジェクトを作成します。|
|[コントロールバー::ゲットボタン情報](#getbuttoninfo)|ボタンの ID、スタイル、およびイメージ番号を取得します。|
|[Cツールバー::ゲットボタンスタイル](#getbuttonstyle)|ボタンのスタイルを取得します。|
|[コントロール バー::ボタンテキストを取得します。](#getbuttontext)|ボタンに表示されるテキストを取得します。|
|[をクリックします。](#getitemid)|指定されたインデックス位置にあるボタンまたは区切り記号のコマンド ID を返します。|
|[Cツールバー::ゲットアイテムレクト](#getitemrect)|指定したインデックス位置にある項目の表示四角形を取得します。|
|[Cツールバー::ツールバーCtrlを取得します。](#gettoolbarctrl)|基になるコモン コントロールに直接アクセスできるようにします。|
|[を使用します。](#loadbitmap)|ビットマップ ボタン イメージを含むビットマップを読み込みます。|
|[Cツールバー::ロードツールバー](#loadtoolbar)|リソース エディターで作成されたツール バー リソースを読み込みます。|
|[をクリックします。](#setbitmap)|ビットマップ イメージを設定します。|
|[コントロールバー::ボタンの設定](#setbuttoninfo)|ボタンの ID、スタイル、およびイメージ番号を設定します。|
|[コントロールバー::ボタンの設定](#setbuttons)|ボタンスタイルとビットマップ内のボタンイメージのインデックスを設定します。|
|[Cツールバー::セットボタンスタイル](#setbuttonstyle)|ボタンのスタイルを設定します。|
|[コントロールバー::ボタンテキストの設定](#setbuttontext)|ボタンに表示するテキストを設定します。|
|[Cツールバー::セットハイト](#setheight)|ツール バーの高さを設定します。|
|[Cツールバー::セットサイズ](#setsizes)|ボタンとそのビットマップのサイズを設定します。|

## <a name="remarks"></a>解説

ボタンは、押ボタン、チェックボックスボタン、ラジオボタンのように動作します。 `CToolBar`オブジェクトは、通常[、CFrameWnd](../../mfc/reference/cframewnd-class.md)または[CMDIFrameWnd](../../mfc/reference/cmdiframewnd-class.md)クラスから派生したフレーム ウィンドウ オブジェクトの埋め込みメンバーです。

MFC 4.0 の新しいメンバー関数である[CToolBar:GetToolBarCtrl](#gettoolbarctrl)を使用すると、ツール バーのカスタマイズと追加機能に対する Windows コモン コントロールのサポートを利用できます。 `CToolBar`メンバー関数は、Windows コモン コントロールのほとんどの機能を提供します。ただし、 を呼`GetToolBarCtrl`び出すと、Windows 95/98 のツール バーの特性をさらに多くツール バーに提供できます。 を呼び`GetToolBarCtrl`出すと、オブジェクトへの参照が`CToolBarCtrl`返されます。 Windows コモン コントロールを使用したツール バーのデザインの詳細については[、「CToolBarCtrl」](../../mfc/reference/ctoolbarctrl-class.md)を参照してください。 コモン コントロールの一般的な情報については、Windows SDK の[「コモン コントロール](/windows/win32/Controls/common-controls-intro)」を参照してください。

Visual C++ には、ツール バーを作成するための 2 つのメソッドが用意されています。 リソース エディターを使用してツール バー リソースを作成するには、次の手順を実行します。

1. ツール バー リソースを作成します。

1. オブジェクトを`CToolBar`構築します。

1. [作成](#create)(または[CreateEx)](#createex)関数を呼び出して、Windows ツール`CToolBar`バーを作成し、オブジェクトにアタッチします。

1. ツール バー リソースを読み込むには[、LoadToolBar](#loadtoolbar)を呼び出します。

それ以外の場合は、次の手順に従います。

1. オブジェクトを`CToolBar`構築します。

1. [作成](#create)(または[CreateEx)](#createex)関数を呼び出して、Windows ツール`CToolBar`バーを作成し、オブジェクトにアタッチします。

1. [LoadBitmap](#loadbitmap)を呼び出して、ツール バー ボタン イメージを含むビットマップを読み込みます。

1. [SetButtons](#setbuttons)を呼び出してボタンのスタイルを設定し、各ボタンをビットマップ内のイメージに関連付けます。

ツールバーのすべてのボタン イメージは、1 つのビットマップから取得され、ボタンごとに 1 つのイメージが含まれている必要があります。 すべてのイメージは同じサイズでなければなりません。デフォルトは、幅 16 ピクセル、高さ 15 ピクセルです。 ビットマップ内でイメージを並べて表示する必要があります。

この`SetButtons`関数は、コントロール ID の配列へのポインターと、配列内の要素数を指定する整数を受け取ります。 この関数は、各ボタンの ID を配列の対応する要素の値に設定し、各ボタンにイメージ インデックスを割り当てます。 配列要素に値ID_SEPARATORがある場合、イメージインデックスは割り当てられません。

ビットマップ内のイメージの順序は、通常、画面上に描画される順序ですが[、SetButtonInfo](#setbuttoninfo)関数を使用して、イメージの順序と描画順序の関係を変更できます。

ツールバーのすべてのボタンは同じサイズです。 デフォルトは、*ソフトウェア設計に関*する Windows インターフェイス ガイドラインに従って、24 x 22 ピクセルです。 画像とボタンの寸法の間にスペースを追加すると、画像の周囲に境界線が形成されます。

各ボタンには 1 つのイメージがあります。 ボタンの状態とスタイル(押された、上へ、下へ、無効、無効、不確定)は、その 1 つのイメージから生成されます。 ビットマップは任意の色にできますが、黒のイメージとグレーの陰影で最適な結果を得ることができます。

> [!WARNING]
> `CToolBar`は、最大 16 色のビットマップをサポートします。 イメージをツール バー エディターに読み込むと、Visual Studio は必要に応じてイメージを 16 色のビットマップに自動的に変換し、イメージが変換された場合は警告メッセージを表示します。 16 色を超えるイメージを使用する場合 (外部エディタを使用してイメージを編集する)、アプリケーションが予期しない動作をすることがあります。

ツールバーボタンは、デフォルトで押ボタンを模倣します。 ただし、ツールバーのボタンは、チェック ボックス ボタンやラジオ ボタンを模倣することもできます。 チェック ボックス ボタンには、チェック マーク、クリア、および不確定の 3 つの状態があります。 ラジオボタンには、オンとオフの2つの状態しかありません。

配列を指さずに個々のボタンまたは区切りスタイルを設定するには[、GetButtonStyle](#getbuttonstyle)を呼び出してスタイルを取得し、代`SetButtons`わりに[SetButtonStyle](#setbuttonstyle)を呼び出します。 `SetButtonStyle`は、実行時にボタンのスタイルを変更する場合に最も便利です。

ボタンに表示するテキストを割り当てるには[、GetButtonText](#getbuttontext)を呼び出してボタンに表示するテキストを取得し[、SetButtonText](#setbuttontext)を呼び出してテキストを設定します。

チェック ボックス ボタンを作成するには、スタイル TBBS_CHECKBOXを割り当`CCmdUI`てるか、ON_UPDATE_COMMAND_UI ハンドラーでオブジェクトの`SetCheck`メンバー関数を使用します。 呼`SetCheck`び出しは、押ボタンをチェックボックスボタンに変えます。 チェック`SetCheck`されていない場合は 0、チェックされている場合は 1、不確定の場合は 2 の引数を渡します。

ラジオ ボタンを作成するには、ON_UPDATE_COMMAND_UI ハンドラーから[CCmdUI](../../mfc/reference/ccmdui-class.md)オブジェクトの[SetRadio](../../mfc/reference/ccmdui-class.md#setradio)メンバー関数を呼び出します。 チェック`SetRadio`されていない場合は 0、チェックされていない場合は 0 以外の引数を渡します。 ラジオ グループの相互排他的な動作を提供するには、グループ内のすべてのボタンに対してON_UPDATE_COMMAND_UIハンドラーが必要です。

の使用方法`CToolBar`の詳細については[、「MFC ツール バーの実装](../../mfc/mfc-toolbar-implementation.md)」および「[テクニカル ノート 31: コントロール バー](../../mfc/tn031-control-bars.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[コントロールバー](../../mfc/reference/ccontrolbar-class.md)

`CToolBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="ctoolbarcommandtoindex"></a><a name="commandtoindex"></a>Cツールバー::コマンドインデックス

このメンバー関数は、コマンド ID が一致`nIDFind`する位置 0 から始まる、最初のツール バー ボタンのインデックスを返します。

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>パラメーター

*nID検索*<br/>
ツール バー ボタンのコマンド ID。

### <a name="return-value"></a>戻り値

ボタンのインデックス、またはボタンが指定されたコマンド ID を持たない場合は -1。

## <a name="ctoolbarcreate"></a><a name="create"></a>Cツールバー::作成

このメンバー関数は、Windows ツール バー (子ウィンドウ) を作成`CToolBar`し、それをオブジェクトに関連付けます。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_TOP,
    UINT nID = AFX_IDW_TOOLBAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ツール バーの親であるウィンドウへのポインター。

*Dwstyle*<br/>
ツール バーのスタイル。 サポートされる追加のツールバー スタイルは次のとおりです。

- CBRS_TOP コントロール バーは、フレーム ウィンドウの上部にあります。

- CBRS_BOTTOMコントロール バーは、フレーム ウィンドウの下部にあります。

- CBRS_NOALIGNコントロールバーは、親のサイズを変更しても再配置されません。

- CBRS_TOOLTIPSコントロールバーにツールヒントが表示されます。

- CBRS_SIZE_DYNAMICコントロールバーは動的です。

- CBRS_SIZE_FIXEDコントロールバーが固定されています。

- CBRS_FLOATINGコントロールバーが浮いている。

- CBRS_FLYBYステータス バーには、ボタンに関する情報が表示されます。

- CBRS_HIDE_INPLACEコントロールバーはユーザーに表示されません。

*nID*<br/>
ツール バーの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

また、ツールバーの高さを既定値に設定します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#179](../../mfc/codesnippet/cpp/ctoolbar-class_1.cpp)]

## <a name="ctoolbarcreateex"></a><a name="createex"></a>Cツールバー::作成します。

Windows のツール バー (子ウィンドウ) を作成し、`CToolBar`それをオブジェクトに関連付けます。

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
ツール バーの親であるウィンドウへのポインター。

*スタイル*<br/>
埋め込まれた[CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)オブジェクトを作成するための追加のスタイル。 既定では、この値はTBSTYLE_FLATに設定されています。 ツール バー スタイルの詳細な一覧については、「 *dwStyle*」を参照してください。

*Dwstyle*<br/>
ツール バーのスタイル。 適切なスタイルの一覧については、Windows SDK の[ツールバー コントロールとボタン スタイル](/windows/win32/Controls/toolbar-control-and-button-styles)を参照してください。

*rcボーダー*<br/>
ツール バー ウィンドウの境界線の幅を定義する[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクト。 これらの境界線は既定で 0,0,0,0 に設定されるため、ツールバー ウィンドウに枠線は表示されません。

*nID*<br/>
ツール バーの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

また、ツールバーの高さを既定値に設定します。

埋`CreateEx`め込まれたツール バー[コントロールの作成時](#create)に特定のスタイルを必要とする場合は、 の代わりに Create を使用します。 たとえば、&#124; TBSTYLE_TRANSPARENTに*dwCtrlStyle*を TBSTYLE_FLAT設定して、Internet Explorer 4 のツールバーのようなツールバーを作成します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#180](../../mfc/codesnippet/cpp/ctoolbar-class_2.cpp)]

## <a name="ctoolbarctoolbar"></a><a name="ctoolbar"></a>Cツールバー::Cツールバー

このメンバー関数は、オブジェクト`CToolBar`を構築し、既定のサイズを設定します。

```
CToolBar();
```

### <a name="remarks"></a>解説

Create[メンバー関数](#create)を呼び出して、ツール バー ウィンドウを作成します。

## <a name="ctoolbargetbuttoninfo"></a><a name="getbuttoninfo"></a>コントロールバー::ゲットボタン情報

このメンバー関数は *、nIndex*で指定された位置にあるツール バー ボタンまたは区切り記号のコントロール ID、スタイル、およびイメージ インデックスを取得します。

```cpp
void GetButtonInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& iImage) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
情報を取得するツール バー ボタンまたは区切り記号のインデックス。

*nID*<br/>
ボタンのコマンド ID に設定されている UINT への参照。

*nStyle*<br/>
ボタンのスタイルに設定されている UINT への参照。

*iイメージ*<br/>
ビットマップ内のボタンのイメージのインデックスに設定される整数への参照。

### <a name="remarks"></a>解説

これらの値は、 *nID*、 *nStyle*、および*iImage*によって参照される変数に割り当てられます。 イメージインデックスは、すべてのツール バー ボタンのイメージを含むビットマップ内のイメージの位置です。 最初のイメージは位置 0 です。

*nIndex で*区切り文字を指定した場合 *、iImage*は区切り文字の幅をピクセル単位で設定します。

## <a name="ctoolbargetbuttonstyle"></a><a name="getbuttonstyle"></a>Cツールバー::ゲットボタンスタイル

ツール バーのボタンまたは区切り記号のスタイルを取得します。

```
UINT GetButtonStyle(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得するツール バー ボタンまたは区切りスタイルのインデックス。

### <a name="return-value"></a>戻り値

*nIndex*で指定されたボタンまたは区切り記号のスタイル。

### <a name="remarks"></a>解説

ボタンのスタイルによって、ボタンの表示方法とユーザー入力への応答方法が決まります。 ボタン[スタイルの](#setbuttonstyle)例については、「ボタンスタイルの設定」を参照してください。

## <a name="ctoolbargetbuttontext"></a><a name="getbuttontext"></a>コントロール バー::ボタンテキストを取得します。

ボタンに表示されるテキストを取得します。

```
CString GetButtonText(int nIndex) const;

void GetButtonText(
    int nIndex,
    CString& rString) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得するテキストのインデックス。

*文字列*<br/>
取得するテキストを格納する[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

ボタン`CString`テキストを含むオブジェクト。

### <a name="remarks"></a>解説

このメンバー関数の 2 番目の形式`CString`では、文字列テキストをオブジェクトに入力します。

## <a name="ctoolbargetitemid"></a><a name="getitemid"></a>をクリックします。

このメンバー関数は *、nIndex*で指定されたボタンまたは区切り記号のコマンド ID を返します。

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する ID を持つアイテムのインデックス。

### <a name="return-value"></a>戻り値

*nIndex*で指定されたボタンまたは区切り記号のコマンド ID。

### <a name="remarks"></a>解説

区切り記号はID_SEPARATORを返します。

## <a name="ctoolbargetitemrect"></a><a name="getitemrect"></a>Cツールバー::ゲットアイテムレクト

このメンバー関数は、アドレス`RECT`が*lpRect*に含まれている構造体に *、nIndex*で指定されたボタンまたは区切り記号の座標を埋めます。

```
virtual void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
四角形の座標を取得する項目 (ボタンまたは区切り記号) のインデックス。

*Lprect*<br/>
項目の座標を格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体のアドレス。

### <a name="remarks"></a>解説

座標は、ツール バーの左上隅を基準にしたピクセル単位です。

コンボ`GetItemRect`ボックスまたはその他のコントロールで置き換える区切り記号の座標を取得するときに使用します。

### <a name="example"></a>例

  [CToolBar::SetSizes](#setsizes)の例を参照してください。

## <a name="ctoolbargettoolbarctrl"></a><a name="gettoolbarctrl"></a>Cツールバー::ツールバーCtrlを取得します。

このメンバー関数は、基になるコモン コントロールに直接アクセスできます。

```
CToolBarCtrl& GetToolBarCtrl() const;
```

### <a name="return-value"></a>戻り値

`CToolBarCtrl` オブジェクトへの参照です。

### <a name="remarks"></a>解説

Windows`GetToolBarCtrl`ツール バー コモン コントロールの機能を利用し[、CToolBarCtrl](../../mfc/reference/ctoolbarctrl-class.md)のサポートを利用してツール バーをカスタマイズするために使用します。

コモン コントロールの使用の詳細については、Windows SDK の[「コントロール](../../mfc/controls-mfc.md)と[コモン コントロール](/windows/win32/Controls/common-controls-intro)」を参照してください。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocViewSDI#15](../../mfc/codesnippet/cpp/ctoolbar-class_3.cpp)]

## <a name="ctoolbarloadbitmap"></a><a name="loadbitmap"></a>を使用します。

またはで`lpszResourceName`指定されたビットマップを読み込みます`nIDResource`。

```
BOOL LoadBitmap(LPCTSTR lpszResourceName);
BOOL LoadBitmap(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
読み込むビットマップのリソース名へのポインター。

*リソース*<br/>
読み込むビットマップのリソース ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ビットマップには、ツール バー ボタンごとに 1 つのイメージを含める必要があります。 画像が標準サイズ (幅 16 ピクセル、高さ 15 ピクセル) でない場合は[、SetSizes](#setsizes)を呼び出してボタンのサイズとそのイメージを設定します。

> [!WARNING]
> `CToolBar`は、最大 16 色のビットマップをサポートします。 イメージをツール バー エディターに読み込むと、Visual Studio は必要に応じてイメージを 16 色のビットマップに自動的に変換し、イメージが変換された場合は警告メッセージを表示します。 16 色を超えるイメージを使用する場合 (外部エディタを使用してイメージを編集する)、アプリケーションが予期しない動作をすることがあります。

## <a name="ctoolbarloadtoolbar"></a><a name="loadtoolbar"></a>Cツールバー::ロードツールバー

このメンバー関数を呼び出して *、lpszResourceName*または*nIDResource*で指定されたツール バーを読み込みます。

```
BOOL LoadToolBar(LPCTSTR lpszResourceName);
BOOL LoadToolBar(UINT nIDResource);
```

### <a name="parameters"></a>パラメーター

*リソース名*<br/>
読み込むツール バーのリソース名へのポインター。

*リソース*<br/>
読み込むツール バーのリソース ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

ツールバー リソースの作成の詳細については、 のツールバー[エディタ](../../windows/toolbar-editor.md)を参照してください。

### <a name="example"></a>例

  [CToolBar::CreateEx](#createex)の例を参照してください。

## <a name="ctoolbarsetbitmap"></a><a name="setbitmap"></a>をクリックします。

ツール バーのビットマップ イメージを設定します。

```
BOOL SetBitmap(HBITMAP hbmImageWell);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
ツール バーに関連付けられているビットマップ イメージのハンドル。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

たとえば、ユーザーが`SetBitmap`ドキュメントでボタンのアクションを変更した後に、ビットマップ イメージを変更する呼び出しです。

## <a name="ctoolbarsetbuttoninfo"></a><a name="setbuttoninfo"></a>コントロールバー::ボタンの設定

ボタンのコマンド ID、スタイル、およびイメージ番号を設定します。

```cpp
void SetButtonInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int iImage);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
情報を設定するボタンまたは区切り記号の 0 から始まるインデックス。

*nID*<br/>
ボタンのコマンド ID が設定される値。

*nStyle*<br/>
新しいボタンスタイル。 次のボタン スタイルがサポートされています。

- TBBS_BUTTON 標準押ボタン (デフォルト)

- TBBS_SEPARATOR区切り記号

- TBBS_CHECKBOX自動チェックボックスボタン

- TBBS_GROUP ボタンのグループの開始位置を示します。

- TBBS_CHECKGROUP チェック ボックス ボタンのグループの先頭をマークします。

- TBBS_DROPDOWN ドロップダウン リスト ボタンを作成します。

- TBBS_AUTOSIZE ボタンの幅は、イメージのサイズではなく、ボタンのテキストに基づいて計算されます。

- TBBS_NOPREFIX ボタンテキストにはアクセラレータのプレフィックスが関連付けされません。

*iイメージ*<br/>
ビットマップ内のボタンのイメージの新しいインデックス。

### <a name="remarks"></a>解説

スタイル TBBS_SEPARATORを持つ区切り文字の場合、この関数は、区切り文字の幅を*iImage*に格納されている値にピクセル単位で設定します。

> [!NOTE]
> *nStyle*パラメーターを使用してボタンの状態を設定することもできます。ただし、ボタンの状態は[ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)ハンドラーによって制御されるため、使用する状態`SetButtonInfo`は次のアイドル処理中に失われます。 詳細については、「[ユーザー インターフェイス オブジェクトを更新する方法](../../mfc/how-to-update-user-interface-objects.md)」および[「TN031: コントロール バー](../../mfc/tn031-control-bars.md) 」を参照してください。

ビットマップ イメージとボタンの詳細については[、「CToolBar](../../mfc/reference/ctoolbar-class.md)の概要」および[「CToolBar::LoadBitmap](#loadbitmap)」を参照してください。

## <a name="ctoolbarsetbuttons"></a><a name="setbuttons"></a>コントロールバー::ボタンの設定

このメンバー関数は、各ツール バー ボタンのコマンド ID を配列*lpIDArray*の対応する要素で指定された値に設定します。

```
BOOL SetButtons(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
コマンド ID の配列へのポインター。 空のボタンを割り当てるには NULL を指定できます。

*NIDカウント*<br/>
によって指される配列内の要素の数*です*。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

配列の要素がID_SEPARATOR値を持つ場合は、ツールバーの対応する位置に区切り記号が作成されます。 また、この関数は、各ボタンのスタイルをTBBS_BUTTONに設定し、各セパレータのスタイルをTBBS_SEPARATORに設定し、各ボタンにイメージインデックスを割り当てます。 イメージインデックスは、ビットマップ内のボタンのイメージの位置を指定します。

この関数は、区切り記号のイメージ インデックスを割り当てないので、ビットマップ内の区切り文字を考慮する必要はありません。 ツール バーの位置が 0、1、3 の位置に、位置 2 に区切り記号がある場合、ビットマップの位置 0、1、および 2 のイメージは、それぞれ位置 0、1、3 のボタンに割り当てられます。

*lpIDArray*が NULL の場合、この関数は*nIDCount*で指定された項目数の領域を割り当てます。 各項目の属性を設定するには[、SetButtonInfo](#setbuttoninfo)を使用します。

## <a name="ctoolbarsetbuttonstyle"></a><a name="setbuttonstyle"></a>Cツールバー::セットボタンスタイル

ボタンまたは区切り記号のスタイルを設定したり、ボタンをグループ化したりするために、このメンバー関数を呼び出します。

```cpp
void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
情報を設定するボタンまたは区切り記号のインデックス。

*nStyle*<br/>
ボタンのスタイル。 次のボタン スタイルがサポートされています。

- TBBS_BUTTON 標準押ボタン (デフォルト)

- TBBS_SEPARATOR区切り記号

- TBBS_CHECKBOX自動チェックボックスボタン

- TBBS_GROUP ボタンのグループの開始位置を示します。

- TBBS_CHECKGROUP チェック ボックス ボタンのグループの先頭をマークします。

- TBBS_DROPDOWN ドロップダウン リスト ボタンを作成します。

- TBBS_AUTOSIZE ボタンの幅は、画像のサイズではなく、ボタンのテキストに基づいて計算されます。

- TBBS_NOPREFIX ボタンテキストにはアクセラレータの接頭辞が関連付けされません。

### <a name="remarks"></a>解説

ボタンのスタイルによって、ボタンの表示方法とユーザー入力への応答方法が決まります。

を呼`SetButtonStyle`び出す前に[、GetButtonStyle](#getbuttonstyle)メンバー関数を呼び出して、ボタンまたは区切りスタイルを取得します。

> [!NOTE]
> *nStyle*パラメーターを使用してボタンの状態を設定することもできます。ただし、ボタンの状態は[ON_UPDATE_COMMAND_UI](message-map-macros-mfc.md#on_update_command_ui)ハンドラーによって制御されるため、使用する状態`SetButtonStyle`は次のアイドル処理中に失われます。 詳細については、「[ユーザー インターフェイス オブジェクトを更新する方法](../../mfc/how-to-update-user-interface-objects.md)」および[「TN031: コントロール バー](../../mfc/tn031-control-bars.md) 」を参照してください。

## <a name="ctoolbarsetbuttontext"></a><a name="setbuttontext"></a>コントロールバー::ボタンテキストの設定

ボタンのテキストを設定します。

```
BOOL SetButtonText(
    int nIndex,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
テキストを設定するボタンのインデックスです。

*lpszText*<br/>
ボタンに設定するテキストへのポイント。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="example"></a>例

  [の](#gettoolbarctrl)例を参照してください。

## <a name="ctoolbarsetheight"></a><a name="setheight"></a>Cツールバー::セットハイト

このメンバー関数は、ツール バーの高さを*cyHeight*で指定されたピクセル単位の値に設定します。

```cpp
void SetHeight(int cyHeight);
```

### <a name="parameters"></a>パラメーター

*サイハイト*<br/>
ツール バーの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

[SetSizes](#setsizes)を呼び出した後、このメンバー関数を使用して、標準のツール バーの高さをオーバーライドします。 高さが小さすぎる場合は、ボタンが下部に切り取られる。

この関数が呼び出されない場合、フレームワークはボタンのサイズを使用してツール バーの高さを決定します。

## <a name="ctoolbarsetsizes"></a><a name="setsizes"></a>Cツールバー::セットサイズ

ツール バーのボタンを*sizeButton*で指定されたサイズ (ピクセル単位) に設定します。

```cpp
void SetSizes(
    SIZE sizeButton,
    SIZE sizeImage);
```

### <a name="parameters"></a>パラメーター

*サイズボタン*<br/>
各ボタンのサイズ (ピクセル単位)。

*サイズイメージ*<br/>
各画像のサイズ (ピクセル単位)。

### <a name="remarks"></a>解説

*sizeImage*パラメーターには、ツール バーのビットマップ内のイメージのサイズ (ピクセル単位) を含める必要があります。 サイズのサイズ*ボタン*は、画像に幅7ピクセル、高さ6ピクセルを加えた値を保持するのに十分でなければなりません。 この関数は、ボタンに合わせてツールバーの高さを設定します。

このメンバー関数は、Windows*インターフェイス の*ガイドラインに従わないツール バーのボタンとイメージのサイズに関する推奨値を呼び出します。

### <a name="example"></a>例

[!code-cpp[NVC_MFCListView#8](../../atl/reference/codesnippet/cpp/ctoolbar-class_4.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL バー](../../overview/visual-cpp-samples.md)<br/>
[サンプル DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル ドッキングツール](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CToolBarCtrl クラス](../../mfc/reference/ctoolbarctrl-class.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
