---
title: CMFCColorPopupMenu クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CMFCColorPopupMenu
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::CreateTearOffBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::GetMenuBar
- AFXCOLORPOPUPMENU/CMFCColorPopupMenu::SetPropList
helpviewer_keywords:
- CMFCColorPopupMenu [MFC], CMFCColorPopupMenu
- CMFCColorPopupMenu [MFC], CreateTearOffBar
- CMFCColorPopupMenu [MFC], GetMenuBar
- CMFCColorPopupMenu [MFC], SetPropList
ms.assetid: 0bf9efe8-aed5-4ab7-b23b-eb284b4668be
ms.openlocfilehash: 2964f250b25ad6c77c70e8f10cd92cca0c7d11da
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844562"
---
# <a name="cmfccolorpopupmenu-class"></a>CMFCColorPopupMenu クラス

ドキュメントまたはアプリケーションで色を選択するためにユーザーが使用するポップアップメニューを表します。

## <a name="syntax"></a>構文

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|[CMFCColorPopupMenu::CMFCColorPopupMenu](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` オブジェクトを構築します。|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCColorPopupMenu::CreateTearOffBar](#createtearoffbar)|ドッキング可能なティアオフカラーバーを作成します。 ( [CMFCPopupMenu:: CreateTearOffBar](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar)をオーバーライドします。)|
|[CMFCColorPopupMenu:: GetMenuBar](#getmenubar)|ポップアップメニュー内に埋め込まれている [Cmfcpopupmenubar](../../mfc/reference/cmfcpopupmenubar-class.md) を返します。 ( [CMFCPopupMenu:: GetMenuBar](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar)をオーバーライドします)。|
|`CMFCColorPopupMenu::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCColorPopupMenu:: SetPropList](#setproplist)|埋め込みオブジェクトのプロパティグリッドコントロールオブジェクトを設定し `CMFCColorBar` ます。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|-|-|
|`m_bEnabledInCustomizeMode`|カラーバーを表示するかどうかを決定するブール値。|
|`m_wndColorBar`|`CMFCColorBar`色の選択を提供するオブジェクト。|

### <a name="remarks"></a>解説

このクラスは、クラスのポップアップメニュー機能を継承 `CMFCPopupMenu` し、色の `CMFCColorBar` 選択を提供するオブジェクトを管理します。 ツールバーフレームワークがカスタマイズモードで、 `m_bEnabledInCustomizeMode` メンバーが FALSE に設定されている場合、カラーバーオブジェクトは表示されません。 カスタマイズモードの詳細については、「 [Cmfctoolbar:: Iscustomization emode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) 」を参照してください。

の詳細について `CMFCColorBar` は、「 [Cmfccolorbar クラス](../../mfc/reference/cmfccolorbar-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[CMFCColorPopupMenu](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolorpopupmenu

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a> CMFCColorPopupMenu::CMFCColorPopupMenu

`CMFCColorPopupMenu` オブジェクトを構築します。

```
CMFCColorPopupMenu(
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    int nHorzDockRows,
    int nVertDockColumns,
    COLORREF colorAutomatic,
    UINT uiCommandID,
    BOOL bStdColorDlg = FALSE);

CMFCColorPopupMenu(
    CMFCColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic);

CMFCColorPopupMenu(
    CMFCRibbonColorButton* pParentBtn,
    const CArray<COLORREF, COLORREF>& colors,
    COLORREF color,
    LPCTSTR lpszAutoColor,
    LPCTSTR lpszOtherColor,
    LPCTSTR lpszDocColors, CList<COLORREF, COLORREF>& lstDocColors,
    int nColumns,
    COLORREF colorAutomatic,
    UINT nID);
```

### <a name="parameters"></a>パラメーター

*色数*<br/>
からフレームワークによってポップアップメニューに表示される色の配列。

*color*<br/>
から既定で選択されている色。

*lpszAutoColor*<br/>
から *自動* (既定) カラーボタンのテキストラベル、または NULL。

[自動] ボタンの標準ラベルは [ **自動**] です。

*lpszOtherColor*<br/>
から *他* のボタンのテキストラベル。より多くの色の選択肢を表示するか、NULL を表示します。

[その他] ボタンの標準ラベルは **より多くの色**です....

*lpszDocColors*<br/>
から[ドキュメントの色] ボタンのテキストラベル。 ドキュメントの色パレットには、ドキュメントが現在使用しているすべての色が表示されます。

*lstDocColors*<br/>
からドキュメントが現在使用している色の一覧。

*nColumns*<br/>
から色の配列に含まれる列の数。

*nHorzDockRows*<br/>
から水平方向にドッキングしたときにカラーバーが持つ行の数。

*nVertDockColumns*<br/>
からカラーバーが垂直方向にドッキングされるときの列の数。

*colorAutomatic*<br/>
から[自動] ボタンをクリックしたときにフレームワークによって適用される既定の色です。

*uiCommandID*<br/>
からカラーバーコントロールのコマンド ID。

*bStdColorDlg*<br/>
から標準システムカラーダイアログボックスと [ [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md) ] ダイアログボックスのどちらを表示するかを示すブール値です。

*pParentBtn*<br/>
から親ボタンへのポインター。

*nID*<br/>
からコマンド ID。

### <a name="remarks"></a>解説

オーバーロードされた各コンストラクターは、 `m_bEnabledInCustomizeMode` メンバーを FALSE に設定します。

### <a name="example"></a>例

次の例は、オブジェクトを構築する方法を示して `CMFCColorPopupMenu` います。

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a> CMFCColorPopupMenu::CreateTearOffBar

ドッキング可能なティアオフカラーバーを作成します。

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

*pWndMain*\
からティアオフバーの親ウィンドウへのポインター。

*uiID*\
からティアオフバーのコマンド ID。

*lpszName*\
からティアオフバーのウィンドウテキスト。

### <a name="return-value"></a>戻り値

新しいティアオフコントロールバーオブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは、 [Cmfccolorbar クラス](../../mfc/reference/cmfccolorbar-class.md) オブジェクトを作成し、 [CPane クラス](../../mfc/reference/cpane-class.md) ポインターにキャストします。 この値は、 [「MFC クラスオブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)」で説明されているキャストマクロのいずれかを使用して、 [Cmfccolorbar クラス](../../mfc/reference/cmfccolorbar-class.md)ポインターにキャストできます。

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a> CMFCColorPopupMenu:: GetMenuBar

ポップアップメニュー内に埋め込まれている [Cmfcpopupmenubar](../../mfc/reference/cmfcpopupmenubar-class.md) を返します。

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>戻り値

埋め込まれたへのポインター `CMFCPopupMenuBar` 。

### <a name="remarks"></a>解説

カラーポップアップメニューには、 [Cmfcpopupmenubar クラス](../../mfc/reference/cmfcpopupmenubar-class.md) オブジェクトが埋め込まれています。 アプリケーションが別の埋め込み型を使用する場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a> CMFCColorPopupMenu:: SetPropList

埋め込みオブジェクトのプロパティグリッドコントロールオブジェクトを設定し `CMFCColorBar` ます。

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>パラメーター

*pWndList*<br/>
からプロパティグリッドコントロールオブジェクトへのポインター。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
