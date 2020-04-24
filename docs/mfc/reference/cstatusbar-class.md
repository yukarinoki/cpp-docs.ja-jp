---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CStatusBar
- AFXEXT/CStatusBar
- AFXEXT/CStatusBar::CStatusBar
- AFXEXT/CStatusBar::CommandToIndex
- AFXEXT/CStatusBar::Create
- AFXEXT/CStatusBar::CreateEx
- AFXEXT/CStatusBar::DrawItem
- AFXEXT/CStatusBar::GetItemID
- AFXEXT/CStatusBar::GetItemRect
- AFXEXT/CStatusBar::GetPaneInfo
- AFXEXT/CStatusBar::GetPaneStyle
- AFXEXT/CStatusBar::GetPaneText
- AFXEXT/CStatusBar::GetStatusBarCtrl
- AFXEXT/CStatusBar::SetIndicators
- AFXEXT/CStatusBar::SetPaneInfo
- AFXEXT/CStatusBar::SetPaneStyle
- AFXEXT/CStatusBar::SetPaneText
helpviewer_keywords:
- CStatusBar [MFC], CStatusBar
- CStatusBar [MFC], CommandToIndex
- CStatusBar [MFC], Create
- CStatusBar [MFC], CreateEx
- CStatusBar [MFC], DrawItem
- CStatusBar [MFC], GetItemID
- CStatusBar [MFC], GetItemRect
- CStatusBar [MFC], GetPaneInfo
- CStatusBar [MFC], GetPaneStyle
- CStatusBar [MFC], GetPaneText
- CStatusBar [MFC], GetStatusBarCtrl
- CStatusBar [MFC], SetIndicators
- CStatusBar [MFC], SetPaneInfo
- CStatusBar [MFC], SetPaneStyle
- CStatusBar [MFC], SetPaneText
ms.assetid: a3bde3db-e71c-4881-a3ca-1d5481c345ba
ms.openlocfilehash: 969edb3b1c87da851d83d390ab9d4e707bd2eb1e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753048"
---
# <a name="cstatusbar-class"></a>クラス

テキスト出力用のペインまたは "インジケーター" の行を持つコントロール バーです。

## <a name="syntax"></a>構文

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ステータスバー::ステータスバー](#cstatusbar)|`CStatusBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#commandtoindex)|指定されたインジケーター ID のインデックスを取得します。|
|[Cステータスバー::作成](#create)|ステータス バーを作成し、`CStatusBar`オブジェクトにアタッチし、初期フォントとバーの高さを設定します。|
|[Cステータスバー::作成します。](#createex)|埋め`CStatusBar`込み`CStatusBarCtrl`オブジェクトの追加スタイルを持つオブジェクトを作成します。|
|[:Dローアイテム](#drawitem)|オーナー描画ステータス バー コントロールの視覚的な側面が変更されたときに呼び出されます。|
|[をクリックします。](#getitemid)|指定したインデックスのインジケーター ID を取得します。|
|[をクリックします。](#getitemrect)|指定したインデックスの表示四角形を取得します。|
|[を設定します。](#getpaneinfo)|指定したインデックスのインジケーター ID、スタイル、および幅を取得します。|
|[をクリックします。](#getpanestyle)|指定したインデックスのインジケーター スタイルを取得します。|
|[テキストを取得します。](#getpanetext)|指定したインデックスのインジケーター テキストを取得します。|
|[を取得します。](#getstatusbarctrl)|基になるコモン コントロールに直接アクセスできるようにします。|
|[ステータスバー::セットインディケータ](#setindicators)|インジケータ ID を設定します。|
|[を設定します。](#setpaneinfo)|指定したインデックスのインジケーター ID、スタイル、および幅を設定します。|
|[コントロール::セットペインスタイル](#setpanestyle)|指定したインデックスのインジケーター スタイルを設定します。|
|[テキストを設定します。](#setpanetext)|指定したインデックスのインジケーター テキストを設定します。|

## <a name="remarks"></a>解説

出力ペインは、通常、メッセージ行として、およびステータス インジケータとして使用されます。 例としては、選択したメニュー コマンドを簡単に説明するメニュー ヘルプ メッセージ行や、SCROLL LOCK、NumLock、およびその他のキーの状態を示すインジケータがあります。

MFC 4.0 の新しいメンバー関数である[CStatusBarCtrl](#getstatusbarctrl)を使用すると、Windows コモン コントロールのステータス バーのカスタマイズと追加機能のサポートを利用できます。 `CStatusBar`メンバー関数は、Windows コモン コントロールのほとんどの機能を提供します。ただし、 に電話`GetStatusBarCtrl`をかけると、Windows 95/98 ステータス バーの特性をさらに多く表示できます。 を呼び`GetStatusBarCtrl`出すと、オブジェクトへの参照が`CStatusBarCtrl`返されます。 Windows コモン コントロールを使用したツール バーのデザインの詳細については[、「CStatusBarCtrl」](../../mfc/reference/cstatusbarctrl-class.md)を参照してください。 コモン コントロールの一般的な情報については、Windows SDK の[「コモン コントロール](/windows/win32/Controls/common-controls-intro)」を参照してください。

フレームワークは、位置 0 に左端のインジケーターを持つ配列にインジケーター情報を格納します。 ステータス バーを作成するときは、フレームワークが対応するインジケーターに関連付ける文字列 ID の配列を使用します。 その後、文字列 ID またはインデックスを使用してインジケーターにアクセスできます。

デフォルトでは、最初のインジケーターは「弾性」で、他のインジケーター・ペインで使用されていないステータス・バーの長さが取り込まれるため、他のペインは右揃えになります。

ステータス バーを作成するには、次の手順を実行します。

1. オブジェクトを`CStatusBar`構築します。

1. [[作成](#create)] (または[CreateEx)](#createex)関数を呼び出して、ステータス バー`CStatusBar`ウィンドウを作成し、オブジェクトにアタッチします。

1. 各指標に文字列IDを関連付ける[SetIndicators](#setindicators)を呼び出します。

ステータス バー ペインのテキストを更新するには、次の 3 つの方法があります。

1. ウィンドウ 0 のテキストのみを更新するには[、CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext)を呼び出します。

1. ステータス バーのON_UPDATE_COMMAND_UI ハンドラーで[CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext)を呼び出します。

1. 任意のペインのテキストを更新する[SetPaneText](#setpanetext)を呼び出します。

ステータス バー ペインのスタイルを更新するには[、SetPaneStyle](#setpanestyle)を呼び出します。

の使用方法`CStatusBar`の詳細については、「MFC の[ステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)」および「テクニカル ノート[31 : コントロール バー](../../mfc/tn031-control-bars.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[コントロールバー](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

## <a name="cstatusbarcommandtoindex"></a><a name="commandtoindex"></a>をクリックします。

指定した ID のインジケーター インデックスを取得します。

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>パラメーター

*nID検索*<br/>
インデックスを取得するインジケーターの文字列 ID。

### <a name="return-value"></a>戻り値

成功した場合はインジケーターのインデックス。成功しなかった場合は -1。

### <a name="remarks"></a>解説

最初の指標のインデックスは 0 です。

## <a name="cstatusbarcreate"></a><a name="create"></a>Cステータスバー::作成

ステータス バー (子ウィンドウ) を作成し、`CStatusBar`オブジェクトに関連付けます。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ウィンドウがステータス バーの親である[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

*Dwstyle*<br/>
ステータス バーのスタイル。 標準の Windows[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)に加えて、これらのスタイルもサポートされています。

- CBRS_TOPコントロール バーはフレーム ウィンドウの上部にあります。

- CBRS_BOTTOMコントロール バーはフレーム ウィンドウの下部にあります。

- CBRS_NOALIGNコントロールバーは、親のサイズを変更しても再配置されません。

*nID*<br/>
ツール バーの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

また、初期フォントを設定し、ステータス バーの高さを既定値に設定します。

## <a name="cstatusbarcreateex"></a><a name="createex"></a>Cステータスバー::作成します。

ステータス バー (子ウィンドウ) を作成し、`CStatusBar`オブジェクトに関連付けます。

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ウィンドウがステータス バーの親である[CWnd](../../mfc/reference/cwnd-class.md)オブジェクトへのポインター。

*スタイル*<br/>
埋め込まれた[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)オブジェクトの作成のための追加のスタイル。 既定では、サイズ変更グリップまたはツールヒントサポートのないステータス バーが指定されます。 サポートされるステータス バーのスタイルは次のとおりです。

- SBARS_SIZEGRIP ステータス バー コントロールには、ステータス バーの右端にサイズ変更グリップが含まれます。 サイズ変更グリップは、サイズ変更の境界線に似ています。これは、ユーザーがクリックしてドラッグして親ウィンドウのサイズを変更できる四角形の領域です。

- SBT_TOOLTIPS ステータス バーはツールヒントをサポートしています。

これらのスタイルの詳細については[、「CStatusBarCtrl の設定](../../mfc/settings-for-the-cstatusbarctrl.md)」を参照してください。

*Dwstyle*<br/>
ステータス バーのスタイル。 既定では、フレーム ウィンドウの下部に表示されるステータス バーが作成されます。 [ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[CDialogBar::作成](../../mfc/reference/cdialogbar-class.md#create)に表示されているステータス バー コントロール スタイルの任意の組み合わせを適用します。 ただし、このパラメーターには、常にWS_CHILDとWS_VISIBLEスタイルを含める必要があります。

*nID*<br/>
ステータス バーの子ウィンドウ ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

この関数は、初期フォントを設定し、ステータス バーの高さを既定値に設定します。

埋`CreateEx`め込まれたステータス バー[コントロールの作成時](#create)に特定のスタイルを必要とする場合は、 の代わりに Create を使用します。 たとえば、ステータス バー オブジェクトにツールチップを表示するには *、dwCtrlStyle*を SBT_TOOLTIPSに設定します。

## <a name="cstatusbarcstatusbar"></a><a name="cstatusbar"></a>ステータスバー::ステータスバー

オブジェクトを`CStatusBar`構築し、必要に応じてデフォルトのステータスバーフォントを作成し、フォント特性をデフォルト値に設定します。

```
CStatusBar();
```

## <a name="cstatusbardrawitem"></a><a name="drawitem"></a>:Dローアイテム

このメンバー関数は、オーナー描画ステータス バーの視覚的な側面が変更されたときに、フレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*構造体*<br/>
必要な描画の種類に関する情報を含む[DRAWITEMSTRUCT 構造体](/windows/win32/api/winuser/ns-winuser-drawitemstruct)へのポインター。

### <a name="remarks"></a>解説

構造`itemAction`のメンバーは`DRAWITEMSTRUCT`、実行される描画アクションを定義します。 オーナー描画`CStatusBar`オブジェクトの描画を実装するには、このメンバー関数をオーバーライドします。 アプリケーションは、このメンバー関数の終了前に *、lpDrawItemStruct*で提供される表示コンテキストに選択されているすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります。

## <a name="cstatusbargetitemid"></a><a name="getitemid"></a>をクリックします。

*nIndex*で指定されたインジケーターの ID を返します。

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得する ID を持つインジケーターのインデックス。

### <a name="return-value"></a>戻り値

*nIndex*で指定されたインジケーターの ID。

## <a name="cstatusbargetitemrect"></a><a name="getitemrect"></a>をクリックします。

*nIndex*で指定されたインジケーターの座標を *、lpRect*が指す構造体にコピーします。

```cpp
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
四角形の座標を取得するインジケーターのインデックス。

*Lprect*<br/>
*nIndex*で指定されたインジケーターの座標を受け取る[RECT](/windows/win32/api/windef/ns-windef-rect)構造体または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトへのポインター。

### <a name="remarks"></a>解説

座標は、ステータス バーの左上隅を基準にしたピクセル単位です。

## <a name="cstatusbargetpaneinfo"></a><a name="getpaneinfo"></a>を設定します。

*nID*、 *nStyle*、および*cxWidth*を*nIndex*で指定された位置にあるインジケータ ペインの ID、スタイル、および幅に設定します。

```cpp
void GetPaneInfo(
    int nIndex,
    UINT& nID,
    UINT& nStyle,
    int& cxWidth) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
情報を取得するペインのインデックス。

*nID*<br/>
ペインの ID に設定されている UINT への参照。

*nStyle*<br/>
ペインのスタイルに設定されている UINT への参照。

*幅*<br/>
ペインの幅に設定された整数への参照。

## <a name="cstatusbargetpanestyle"></a><a name="getpanestyle"></a>をクリックします。

ステータス バーのペインのスタイルを取得します。

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
取得するスタイルを持つペインのインデックス。

### <a name="return-value"></a>戻り値

*nIndex*で指定されたステータス バー ペインのスタイル。

### <a name="remarks"></a>解説

ペインのスタイルによって、ペインの表示方法が決まります。

ステータス バーで使用できるスタイルの一覧については、「[作成](#create)」を参照してください。

## <a name="cstatusbargetpanetext"></a><a name="getpanetext"></a>テキストを取得します。

ステータス バー ペインに表示されるテキストを取得します。

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
テキストを取得するペインのインデックス。

*文字列*<br/>
取得するテキストを含む[CString](../../atl-mfc-shared/reference/cstringt-class.md)オブジェクトへの参照。

### <a name="return-value"></a>戻り値

ペイン`CString`のテキストを含むオブジェクト。

### <a name="remarks"></a>解説

このメンバー関数の 2 番目の形式`CString`では、文字列テキストをオブジェクトに入力します。

## <a name="cstatusbargetstatusbarctrl"></a><a name="getstatusbarctrl"></a>を取得します。

このメンバー関数は、基になるコモン コントロールに直接アクセスできます。

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>戻り値

[オブジェクトへの](../../mfc/reference/cstatusbarctrl-class.md)参照を格納します。

### <a name="remarks"></a>解説

Windows`GetStatusBarCtrl`ステータス バー コモン コントロールの機能を利用し、ステータス バーのカスタマイズに関する[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)のサポートを利用するために使用します。 たとえば、コモン コントロールを使用して、ステータス バーにサイズ変更グリップを含むスタイルを指定したり、親ウィンドウのクライアント領域の上部にステータス バーを表示するスタイルを指定したりできます。

コモン コントロールの一般的な情報については、「Windows SDK の[コモン コントロール](/windows/win32/Controls/common-controls-intro)」を参照してください。

## <a name="cstatusbarsetindicators"></a><a name="setindicators"></a>ステータスバー::セットインディケータ

各指標の ID を配列*lpIDArray*の対応する要素で指定された値に設定し、各 ID で指定された文字列リソースを読み込み、インジケータのテキストを文字列に設定します。

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
ID の配列へのポインター。

*NIDカウント*<br/>
によって指される配列内の要素の数*です*。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

## <a name="cstatusbarsetpaneinfo"></a><a name="setpaneinfo"></a>を設定します。

指定したインジケーター ペインを新しい ID、スタイル、および幅に設定します。

```cpp
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
スタイルを設定するインジケーター ペインのインデックスです。

*nID*<br/>
インジケーター ペインの新しい ID。

*nStyle*<br/>
インジケーター ペインの新しいスタイル。

*幅*<br/>
インジケーター ペインの新しい幅。

### <a name="remarks"></a>解説

次のインジケータスタイルがサポートされています。

- SBPS_NOBORDERS ペインの周囲に 3-D 境界線はありません。

- SBPS_POPOUT逆罫線を使用して、テキストが "ポップ アウト" されるようにします。

- SBPS_DISABLED テキストを描画しません。

- SBPS_STRETCH[ペインをストレッチ]を使用して未使用の領域を埋めます。 このスタイルを持つことができるのは、ステータス バーごとに 1 つのペインのみです。

- SBPS_NORMAL 伸縮、境界線、またはポップアウトなし。

## <a name="cstatusbarsetpanestyle"></a><a name="setpanestyle"></a>コントロール::セットペインスタイル

ステータス バーのペインのスタイルを設定します。

```cpp
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
スタイルを設定するペインのインデックス。

*nStyle*<br/>
スタイルを設定するペインのスタイル。

### <a name="remarks"></a>解説

ペインのスタイルによって、ペインの表示方法が決まります。

ステータス バーで使用できるスタイルの一覧については、「 [SetPaneInfo](#setpaneinfo)」を参照してください。

## <a name="cstatusbarsetpanetext"></a><a name="setpanetext"></a>テキストを設定します。

このメンバー関数を呼び出して、ペイン テキストを*lpszNewText*が指す文字列に設定します。

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
テキストを設定するペインのインデックス。

*テキスト*<br/>
新しいペイン テキストへのポインター。

*b更新*<br/>
TRUE の場合、テキストが設定された後にペインが無効になります。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

を呼び`SetPaneText`出した後、ステータス バーに新しいテキストを表示する UI 更新ハンドラーを追加する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRL バー](../../overview/visual-cpp-samples.md)<br/>
[サンプル DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl クラス](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
