---
title: CStatusBar クラス
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
ms.openlocfilehash: d714159aa9fd52df682b1e5f3dbf3957bbef1b91
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777338"
---
# <a name="cstatusbar-class"></a>CStatusBar クラス

テキスト出力用のペインまたは "インジケーター" の行を持つコントロール バーです。

## <a name="syntax"></a>構文

```
class CStatusBar : public CControlBar
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CStatusBar::CStatusBar](#cstatusbar)|`CStatusBar` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CStatusBar::CommandToIndex](#commandtoindex)|指定したインジケーターの ID のインデックスを取得します。|
|[CStatusBar::Create](#create)|ステータス バーを作成し、それにアタッチします、`CStatusBar`オブジェクト、および初期のフォントとバーの高さを設定します。|
|[CStatusBar::CreateEx](#createex)|作成、 `CStatusBar` 、埋め込みの追加のスタイルを使用してオブジェクト`CStatusBarCtrl`オブジェクト。|
|[CStatusBar::DrawItem](#drawitem)|オーナー描画ステータス バー コントロールの変更のビジュアルな部分と呼び出されます。|
|[CStatusBar::GetItemID](#getitemid)|指定されたインデックスのインジケーターの ID を取得します。|
|[CStatusBar::GetItemRect](#getitemrect)|取得は、指定されたインデックスの四角形を表示します。|
|[CStatusBar::GetPaneInfo](#getpaneinfo)|指定されたインデックスのインジケーターの ID、スタイル、および幅を取得します。|
|[CStatusBar::GetPaneStyle](#getpanestyle)|指定されたインデックスのインジケーターのスタイルを取得します。|
|[CStatusBar::GetPaneText](#getpanetext)|指定されたインデックスのインジケーターのテキストを取得します。|
|[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)|基になる一般的なコントロールに直接アクセスをできます。|
|[CStatusBar::SetIndicators](#setindicators)|インジケーターの Id を設定します。|
|[CStatusBar::SetPaneInfo](#setpaneinfo)|インジケーターの ID、スタイル、および指定されたインデックスの幅を設定します。|
|[CStatusBar::SetPaneStyle](#setpanestyle)|指定されたインデックスのインジケーターのスタイルを設定します。|
|[CStatusBar::SetPaneText](#setpanetext)|指定されたインデックスのインジケーターのテキストを設定します。|

## <a name="remarks"></a>Remarks

出力ペイン一般的使用メッセージ行およびステータス インジケーターとして使用されます。 例には、選択されたメニュー コマンドを簡単に説明するメニュー ヘルプ メッセージ行と SCROLL LOCK、NUM LOCK、およびその他のキーの状態を示すインジケーターが含まれます。

[CStatusBar::GetStatusBarCtrl](#getstatusbarctrl)、メンバー関数は、新しい MFC 4.0 では、することができますステータス バーのカスタマイズなどの追加機能の Windows コモン コントロールのサポートを活用します。 `CStatusBar` メンバー関数は、ほとんどの Windows コモン コントロール以外の機能を提供します。ただし、呼び出す`GetStatusBarCtrl`、Windows 95/98 のステータス バーの特性の詳細も、ステータス バーを付けることができます。 呼び出すと`GetStatusBarCtrl`への参照が返されます、`CStatusBarCtrl`オブジェクト。 参照してください[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)詳細については、Windows のコモン コントロールを使用してツールバーを設計します。 コモン コントロールの概要については、次を参照してください。[コモン コントロール](/windows/desktop/Controls/common-controls-intro)Windows SDK に含まれています。

フレームワークでは、0 の位置の一番左のインジケーターを含む配列のインジケーターの情報を格納します。 ステータス バーを作成するときは、フレームワークが、対応するインジケーターを関連付けられる Id の文字列の配列を使用します。 インジケーターにアクセスし、文字列 ID またはインデックスのいずれかを使用できます。

既定では、最初のインジケーターは"elastic": 他のウィンドウが右揃えになるように、他のインジケーター ペインでは使用されませんステータス バーの長さをかかります。

ステータス バーを作成するには、次の手順を実行します。

1. 構築、`CStatusBar`オブジェクト。

1. 呼び出す、[作成](#create)(または[CreateEx](#createex))、ステータス バーのウィンドウを作成し、アタッチ先の関数、`CStatusBar`オブジェクト。

1. 呼び出す[SetIndicators](#setindicators)に関連付ける各インジケーターの文字列 ID。

ステータス バー ペインのテキストを更新する次の 3 つの方法はあります。

1. 呼び出す[とき](../../mfc/reference/cwnd-class.md#setwindowtext)ウィンドウ 0 のみのテキストを更新します。

1. 呼び出す[CCmdUI::SetText](../../mfc/reference/ccmdui-class.md#settext)ステータス バーの します。

1. 呼び出す[SetPaneText](#setpanetext)ペインのテキストを更新します。

呼び出す[SetPaneStyle](#setpanestyle)ステータス バー ペインのスタイルを更新します。

使用しての詳細については`CStatusBar`、記事をご覧ください[MFC でのステータス バーの実装](../../mfc/status-bar-implementation-in-mfc.md)と[テクニカル ノート 31。コントロール バー](../../mfc/tn031-control-bars.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CControlBar](../../mfc/reference/ccontrolbar-class.md)

`CStatusBar`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxext.h

##  <a name="commandtoindex"></a>  CStatusBar::CommandToIndex

指定された ID のインジケーターのインデックスを取得します。

```
int CommandToIndex(UINT nIDFind) const;
```

### <a name="parameters"></a>パラメーター

*nIDFind*<br/>
文字列を取得するインデックスは、インジケーターの ID です。

### <a name="return-value"></a>戻り値

成功した場合は、インジケーターのインデックス成功しなかった場合は-1。

### <a name="remarks"></a>Remarks

最初のインジケーターのインデックスは 0 です。

##  <a name="create"></a>  CStatusBar::Create

ステータス バー (子ウィンドウ) を作成しに関連付けます、`CStatusBar`オブジェクト。

```
virtual BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)ステータス バーの親である Windows ウィンドウを持つオブジェクト。

*dwStyle*<br/>
ステータス バーのスタイル。 標準の Windows だけでなく[スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)、これらのスタイルがサポートされています。

- CBRS_TOP コントロール バーは、フレーム ウィンドウの上部にあること。

- CBRS_BOTTOM コントロール バーでは、フレーム ウィンドウの下部にあります。

- 親のサイズが変更されたときに CBRS_NOALIGN コントロール バーの位置を変更できません。

*nID*<br/>
ツールバーの子ウィンドウの id。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

初期のフォントを設定し、ステータス バーの高さを既定値。

##  <a name="createex"></a>  CStatusBar::CreateEx

ステータス バー (子ウィンドウ) を作成し、それをこの関数を呼び出して、`CStatusBar`オブジェクト。

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle = 0,
    DWORD dwStyle = WS_CHILD | WS_VISIBLE | CBRS_BOTTOM,
    UINT nID = AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ポインター、 [CWnd](../../mfc/reference/cwnd-class.md)ステータス バーの親である Windows ウィンドウを持つオブジェクト。

*dwCtrlStyle*<br/>
埋め込まれたを作成するための追加スタイル[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)オブジェクト。 既定値の指定、サイズ変更グリップとツールヒントなしのステータス バーをサポートします。 ステータス バーのスタイルがサポートされている次のとおりです。

- SBARS_SIZEGRIP、ステータス バー コントロールには、ステータス バーの右端にあるサイズ変更グリップが含まれています。 サイズ変更グリップはサイズ変更境界線; に似ていますユーザーがクリックして親ウィンドウのサイズをドラッグ四角形の領域になります。

- ステータス バーには、ツール ヒントがサポートされています。

これらのスタイルについて詳しくは、[CStatusBarCtrl の設定](../../mfc/settings-for-the-cstatusbarctrl.md)を参照してください。

*dwStyle*<br/>
ステータス バーのスタイル。 既定では、フレーム ウィンドウの下部に表示されるステータス バーを作成することを指定します。 ステータス バーに表示されているコントロールのスタイルの任意の組み合わせを適用[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)と[CDialogBar::Create](../../mfc/reference/cdialogbar-class.md#create)します。 ただし、このパラメーターは、WS_CHILD と WS_VISIBLE スタイルを常に含める必要があります。

*nID*<br/>
ステータス バーの子ウィンドウ id。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

この関数も初期のフォントを設定し、設定、ステータス バーの高さを既定値。

使用`CreateEx`の代わりに[作成](#create)、特定のスタイルは、埋め込まれたステータス バー コントロールの作成中に存在する必要があります。 たとえば、設定*ツール バー*にステータス バーのオブジェクトにツールヒントを表示するには。

##  <a name="cstatusbar"></a>  CStatusBar::CStatusBar

構築、`CStatusBar`オブジェクトが必要に応じて、既定のステータス バーのフォントを作成し、フォントの特性を既定値に設定します。

```
CStatusBar();
```

##  <a name="drawitem"></a>  CStatusBar::DrawItem

このメンバー関数は、ビジュアルな部分のオーナー描画ステータス バーが変更されたときにフレームワークによって呼び出されます。

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>パラメーター

*lpDrawItemStruct*<br/>
ポインターを[DRAWITEMSTRUCT](/windows/desktop/api/winuser/ns-winuser-tagdrawitemstruct)のために必要な図面の種類に関する情報を含む構造体。

### <a name="remarks"></a>Remarks

`itemAction`のメンバー、`DRAWITEMSTRUCT`構造体を実行する描画の動作を定義します。 オーナー描画の描画を実装するには、このメンバー関数をオーバーライド`CStatusBar`オブジェクト。 アプリケーションで提供されるディスプレイ コンテキスト用に選択したすべてのグラフィックス デバイス インターフェイス (GDI) オブジェクトを復元する必要があります*lpDrawItemStruct*このメンバー関数の終了前にします。

##  <a name="getitemid"></a>  CStatusBar::GetItemID

指定したインジケーターの ID を返します*nIndex*します。

```
UINT GetItemID(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
ID を取得するが、インジケーターのインデックス。

### <a name="return-value"></a>戻り値

指定したインジケーターの ID *nIndex*します。

##  <a name="getitemrect"></a>  CStatusBar::GetItemRect

指定したインジケーターの座標をコピー *nIndex*が指す構造体に*lpRect*します。

```
void GetItemRect(
    int nIndex,
    LPRECT lpRect) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
四角形の座標インジケーターのインデックスでは、取得します。

*lpRect*<br/>
指す、 [RECT](/previous-versions/dd162897\(v=vs.85\))構造または[CRect](../../atl-mfc-shared/reference/crect-class.md)オブジェクトで指定したインジケーターの座標を受け取る*nIndex*します。

### <a name="remarks"></a>Remarks

座標は、ステータス バーの左上隅に対して相対的 (ピクセル単位)。

##  <a name="getpaneinfo"></a>  CStatusBar::GetPaneInfo

セット*nID*、 *nStyle*、および*cxWidth* ID、スタイル、およびによって指定された位置インジケーターのウィンドウの幅を*nIndex*します。

```
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
ウィンドウのスタイルに設定されている UINT への参照。

*cxWidth*<br/>
ウィンドウの幅に設定されている整数への参照。

##  <a name="getpanestyle"></a>  CStatusBar::GetPaneStyle

ステータス バーのウィンドウのスタイルを取得するには、このメンバー関数を呼び出します。

```
UINT GetPaneStyle(int nIndex) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
スタイルを取得するペインのインデックス。

### <a name="return-value"></a>戻り値

指定されたステータス バー ペインのスタイル*nIndex*します。

### <a name="remarks"></a>Remarks

ウィンドウのスタイルは、ペインの表示方法を決定します。

ステータス バーで使用可能なスタイルの一覧は、[作成](#create)を参照してください。

##  <a name="getpanetext"></a>  CStatusBar::GetPaneText

ステータス バー ペインに表示されるテキストを取得するには、このメンバー関数を呼び出します。

```
CString GetPaneText(int nIndex) const;  void GetPaneText(int nIndex, CString& rString) const;
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
テキストを取得するペインのインデックス。

*rString*<br/>
参照を[CString](../../atl-mfc-shared/reference/cstringt-class.md)を取得するテキストを含むオブジェクト。

### <a name="return-value"></a>戻り値

A`CString`ウィンドウのテキストを含むオブジェクト。

### <a name="remarks"></a>Remarks

このメンバーの 2 番目の形式の関数の塗りつぶしを`CString`文字列テキストを含むオブジェクト。

##  <a name="getstatusbarctrl"></a>  CStatusBar::GetStatusBarCtrl

このメンバー関数は、基になる一般的なコントロールに直接アクセスをできます。

```
CStatusBarCtrl& GetStatusBarCtrl() const;
```

### <a name="return-value"></a>戻り値

参照が含まれています、 [CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

使用`GetStatusBarCtrl`Windows ステータス バーの一般的なコントロールの機能を活用して、サポートを活用するために[CStatusBarCtrl](../../mfc/reference/cstatusbarctrl-class.md)ステータス バーのカスタマイズを提供します。 たとえば、一般的なコントロールを使用すると、ステータス バーの サイズ変更グリップを含むスタイルを指定することができます。 またはステータス バーを親ウィンドウのクライアント領域の上部に表示スタイルを指定することができます。

コモン コントロールの概要については、次を参照してください。[コモン コントロール](/windows/desktop/Controls/common-controls-intro)Windows SDK に含まれています。

##  <a name="setindicators"></a>  CStatusBar::SetIndicators

各インジケーターの ID は、配列の対応する要素で指定された値を設定*lpIDArray*、各 ID を使用して指定された文字列リソースを読み込み、およびインジケーターのテキストを文字列に設定します。

```
BOOL SetIndicators(
    const UINT* lpIDArray,
    int nIDCount);
```

### <a name="parameters"></a>パラメーター

*lpIDArray*<br/>
Id の配列へのポインター。

*nIDCount*<br/>
配列内の要素の数が指す*lpIDArray*します。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

##  <a name="setpaneinfo"></a>  CStatusBar::SetPaneInfo

新しい ID、スタイル、および幅を指定したインジケーターのウィンドウを設定します。

```
void SetPaneInfo(
    int nIndex,
    UINT nID,
    UINT nStyle,
    int cxWidth);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
スタイルを設定するインジケーター ペインのインデックス。

*nID*<br/>
インジケーター ペインの新しい ID。

*nStyle*<br/>
インジケーター ペインの新しいスタイル。

*cxWidth*<br/>
インジケーター ペインの新しい幅。

### <a name="remarks"></a>Remarks

次のインジケーターのスタイルがサポートされています。

- 3-D 枠が、ウィンドウの周囲を SBPS_NOBORDERS なし。

- テキスト「飛び出します」ように罫線 SBPS_POPOUT 反転

- SBPS_DISABLED テキストを描画しません。

- 未使用の領域を埋める SBPS_STRETCH Stretch ウィンドウです。 ステータス バー ペインは 1 つだけでは、このスタイルを持つことができます。

- SBPS_NORMAL いいえ stretch、罫線、またはポップアウトします。

##  <a name="setpanestyle"></a>  CStatusBar::SetPaneStyle

ステータス バーのウィンドウのスタイルを設定するには、このメンバー関数を呼び出します。

```
void SetPaneStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
スタイルを設定するペインのインデックス。

*nStyle*<br/>
スタイルを設定するペインのスタイル。

### <a name="remarks"></a>Remarks

ウィンドウのスタイルは、ペインの表示方法を決定します。

ステータス バーで使用可能なスタイルの一覧は、[SetPaneInfo](#setpaneinfo)を参照してください。

##  <a name="setpanetext"></a>  CStatusBar::SetPaneText

指す文字列にウィンドウのテキストを設定するには、このメンバー関数を呼び出す*されている*します。

```
BOOL SetPaneText(
    int nIndex,
    LPCTSTR lpszNewText,
    BOOL bUpdate = TRUE);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
テキストを設定するペインのインデックス。

*lpszNewText*<br/>
新しいウィンドウのテキストへのポインター。

*bUpdate*<br/>
TRUE の場合、テキストを設定した後、ウィンドウが無効にします。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>Remarks

呼び出した後`SetPaneText`、ステータス バーに新しいテキストを表示する UI の更新ハンドラーを追加する必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCDocView#176](../../mfc/codesnippet/cpp/cstatusbar-class_1.cpp)]

[!code-cpp[NVC_MFCDocView#177](../../mfc/codesnippet/cpp/cstatusbar-class_2.cpp)]

[!code-cpp[NVC_MFCDocView#178](../../mfc/codesnippet/cpp/cstatusbar-class_3.cpp)]

## <a name="see-also"></a>関連項目

[MFC サンプル CTRLBARS](../../overview/visual-cpp-samples.md)<br/>
[MFC サンプル DLGCBR32](../../overview/visual-cpp-samples.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CStatusBarCtrl クラス](../../mfc/reference/cstatusbarctrl-class.md)<br/>
[CControlBar クラス](../../mfc/reference/ccontrolbar-class.md)
