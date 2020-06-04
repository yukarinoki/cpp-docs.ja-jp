---
title: クラス
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
ms.openlocfilehash: 901a44c8f5fdecd1b277ebdecc995722a3afe9a3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752496"
---
# <a name="cmfccolorpopupmenu-class"></a>クラス

ユーザーがドキュメントまたはアプリケーションの色を選択するために使用するポップアップ メニューを表します。

## <a name="syntax"></a>構文

```
class CMFCColorPopupMenu : public CMFCPopupMenu
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[メニュー::CMFCカラーポップアップメニュー](#cmfccolorpopupmenu)|`CMFCColorPopupMenu` オブジェクトを構築します。|
|`CMFCColorPopupMenu::~CMFCColorPopupMenu`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[メニュー::作成ティアオフバー](#createtearoffbar)|ドッキング可能なティアオフ カラー バーを作成します。 (CMFC ポップアップ メニューをオーバーライド[します。](../../mfc/reference/cmfcpopupmenu-class.md#createtearoffbar)|
|[メニューを表示します。](#getmenubar)|ポップアップ メニュー内に埋め込まれている[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)を返します。 [(CMFC ポップアップ メニューをオーバーライドします。)](../../mfc/reference/cmfcpopupmenu-class.md#getmenubar)|
|`CMFCColorPopupMenu::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[メニュー::セットプロップリスト](#setproplist)|埋め込み`CMFCColorBar`オブジェクトのプロパティ グリッド コントロール オブジェクトを設定します。|

### <a name="data-members"></a>データ メンバー

|||
|-|-|
|名前|説明|
|`m_bEnabledInCustomizeMode`|カラー バーを表示するかどうかを決定するブール値。|
|`m_wndColorBar`|色`CMFCColorBar`の選択を提供するオブジェクト。|

### <a name="remarks"></a>解説

このクラスは、クラスのポップアップ メニュー機能を`CMFCPopupMenu`継承し、色の選択`CMFCColorBar`を提供するオブジェクトを管理します。 ツール バー フレームワークがカスタマイズ モードで`m_bEnabledInCustomizeMode`、メンバーが FALSE に設定されている場合、カラー バー オブジェクトは表示されません。 カスタマイズ モードの詳細については[、「CMFC ツール バー::IsCustomizeMode」を参照してください。](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)

の詳細`CMFCColorBar`については、「 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CFrameWnd](../../mfc/reference/cframewnd-class.md)

[CMiniFrameWnd](../../mfc/reference/cminiframewnd-class.md)

[CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md)

[メニュー](../../mfc/reference/cmfccolorpopupmenu-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcolorポップアップメニュー.h

## <a name="cmfccolorpopupmenucmfccolorpopupmenu"></a><a name="cmfccolorpopupmenu"></a>メニュー::CMFCカラーポップアップメニュー

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

*色*<br/>
[in]フレームワークがポップアップ メニューに表示する色の配列。

*色*<br/>
[in]既定の選択色。

*lpsz 自動カラー*<br/>
[in]*自動*(既定) の色のボタンのテキスト ラベル、または NULL。

自動ボタンの標準ラベルは **[自動]** です。

*その他の色*<br/>
[in]*他*のボタンのテキスト ラベルで、色の選択肢が増えるか、NULL を表示します。

もう一方のボタンの標準ラベルは **[その他の色..]** です。

*カラー*<br/>
[in]ドキュメントの色ボタンのテキスト ラベル。 ドキュメントのカラー パレットには、ドキュメントで現在使用されているすべての色が表示されます。

*カラー*<br/>
[in]ドキュメントが現在使用している色のリスト。

*nColumns*<br/>
[in]色の配列が持つ列の数。

*オーズドックロウズ*<br/>
[in]カラー バーが水平方向にドッキングされている場合の行数。

*列数*<br/>
[in]カラー バーが垂直にドッキングされている場合に表示される列の数。

*カラー自動*<br/>
[in]自動ボタンをクリックしたときにフレームワークが適用する既定の色。

*コマンド ID*<br/>
[in]カラー バー コントロールのコマンド ID。

*bStdカラードグルグ*<br/>
[in]標準のシステム カラー ダイアログ ボックスまたは[CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)ダイアログ ボックスを表示するかどうかを示すブール値。

*親の親*<br/>
[in]親ボタンへのポインター。

*nID*<br/>
[in]コマンド ID。

### <a name="remarks"></a>解説

オーバーロードされた各コンストラクターは、`m_bEnabledInCustomizeMode`メンバーを FALSE に設定します。

### <a name="example"></a>例

オブジェクトを構築する方法を次の例`CMFCColorPopupMenu`に示します。

[!code-cpp[NVC_MFC_RibbonApp#34](../../mfc/reference/codesnippet/cpp/cmfccolorpopupmenu-class_1.cpp)]

## <a name="cmfccolorpopupmenucreatetearoffbar"></a><a name="createtearoffbar"></a>メニュー::作成ティアオフバー

ドッキング可能なティアオフ カラー バーを作成します。

```
virtual CPane* CreateTearOffBar(
    CFrameWnd* pWndMain,
    UINT uiID,
    LPCTSTR lpszName);
```

### <a name="parameters"></a>パラメーター

|||
|-|-|
|パラメーター|説明|
|*ド・マイン*|[in]ティアオフ バーの親ウィンドウへのポインター。|
|*Uiid*|[in]ティアオフ バーのコマンド ID。|
|*名前を指定します。*|[in]ティアオフ バーのウィンドウ テキスト。|

### <a name="return-value"></a>戻り値

新しいティアオフ コントロール バー オブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは[、CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)オブジェクトを作成し[、CPane クラス](../../mfc/reference/cpane-class.md)のポインターにキャストします。 この値を[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)ポインターにキャストするには、「MFC クラス[オブジェクトの型キャスト](../../mfc/reference/type-casting-of-mfc-class-objects.md)」で説明されているキャスト マクロのいずれかを使用します。

## <a name="cmfccolorpopupmenugetmenubar"></a><a name="getmenubar"></a>メニューを表示します。

ポップアップ メニュー内に埋め込まれている[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)を返します。

```
virtual CMFCPopupMenuBar* GetMenuBar();
```

### <a name="return-value"></a>戻り値

埋め込み`CMFCPopupMenuBar`型の .

### <a name="remarks"></a>解説

カラーポップアップ メニューには[、CMFCPopupMenuBar クラス オブジェクトが](../../mfc/reference/cmfcpopupmenubar-class.md)埋め込まれています。 アプリケーションで別の埋め込み型を使用する場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccolorpopupmenusetproplist"></a><a name="setproplist"></a>メニュー::セットプロップリスト

埋め込み`CMFCColorBar`オブジェクトのプロパティ グリッド コントロール オブジェクトを設定します。

```cpp
void SetPropList(CMFCPropertyGridCtrl* pWndList);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
[in]プロパティ グリッド コントロール オブジェクトへのポインター。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
