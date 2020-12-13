---
description: '詳細情報: CMFCPopupMenuBar クラス'
title: CMFCPopupMenuBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::AdjustSizeImmediate
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::BuildOrigItems
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::CloseDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ExportToMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::FindDestintationToolBar
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetCurrentMenuImageSize
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetDefaultMenuId
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetLastCommandIndex
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::GetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::ImportFromMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsDropDownListMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsPaletteMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanel
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::IsRibbonPanelInRegularMode
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::LoadFromHash
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::RestoreDelayedSubMenu
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetButtonStyle
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::SetOffset
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::StartPopupMenuTimer
- AFXPOPUPMENUBAR/CMFCPopupMenuBar::m_bDisableSideBarInXPMode
helpviewer_keywords:
- CMFCPopupMenuBar [MFC], AdjustSizeImmediate
- CMFCPopupMenuBar [MFC], BuildOrigItems
- CMFCPopupMenuBar [MFC], CloseDelayedSubMenu
- CMFCPopupMenuBar [MFC], ExportToMenu
- CMFCPopupMenuBar [MFC], FindDestintationToolBar
- CMFCPopupMenuBar [MFC], GetCurrentMenuImageSize
- CMFCPopupMenuBar [MFC], GetDefaultMenuId
- CMFCPopupMenuBar [MFC], GetLastCommandIndex
- CMFCPopupMenuBar [MFC], GetOffset
- CMFCPopupMenuBar [MFC], ImportFromMenu
- CMFCPopupMenuBar [MFC], IsDropDownListMode
- CMFCPopupMenuBar [MFC], IsPaletteMode
- CMFCPopupMenuBar [MFC], IsRibbonPanel
- CMFCPopupMenuBar [MFC], IsRibbonPanelInRegularMode
- CMFCPopupMenuBar [MFC], LoadFromHash
- CMFCPopupMenuBar [MFC], RestoreDelayedSubMenu
- CMFCPopupMenuBar [MFC], SetButtonStyle
- CMFCPopupMenuBar [MFC], SetOffset
- CMFCPopupMenuBar [MFC], StartPopupMenuTimer
- CMFCPopupMenuBar [MFC], m_bDisableSideBarInXPMode
ms.assetid: 4c93c459-7f70-4240-8c63-280bb811e374
ms.openlocfilehash: 4db8c02ed92aec5243f9a2c7800c6fd1f9747751
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334749"
---
# <a name="cmfcpopupmenubar-class"></a>CMFCPopupMenuBar クラス

ポップアップ メニューに埋め込まれたメニュー バーです。

## <a name="syntax"></a>構文

```
class CMFCPopupMenuBar : public CMFCToolBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|ペインのレイアウトを直ちに再計算します。 ( [CPane:: AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)をオーバーライドします。)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|指定されたメニューリソースからポップアップメニュー項目を読み込みます。|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|遅延ポップアップメニューボタンを閉じます。|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|ポップアップメニューのボタンからメニューを作成します。|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|指定したポイントがあるツールバーを検索します。|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|メニューボタンのイメージのサイズを示します。|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|既定のメニュー項目の識別子を返します。|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|直前に呼び出されたメニューコマンドのインデックスを取得します。|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|ポップアップメニューバーの行オフセットを取得します。|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|指定したメニューからポップアップメニューボタンをインポートします。|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|ポップアップメニューバーがドロップダウンリストモードであるかどうかを示します。|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|ポップアップメニューバーがパレットモードであるかどうかを示します。|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|これがリボンパネルである (既定では FALSE) かどうかを示します。|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|これが通常モードのリボンパネルであるかどうかを示します (既定では FALSE)。|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|アーカイブされたメニューを読み込みます。|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|ポップアップメニューバーを閉じるための遅延メニューボタンを復元します。|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|指定したインデックス位置にあるツールバーボタンのスタイルを設定します。 ( [Cmfctoolbar:: SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)をオーバーライドします)。|
|[CMFCPopupMenuBar::SetOffset](#setoffset)|ポップアップメニューバーの行オフセットを設定します。|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|指定した遅延ポップアップメニューボタンのタイマーを開始します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCPopupMenuBar:: m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|アプリケーションの外観が Windows XP の場合に、灰色のサイドバーを表示するかどうかを指定します。|

## <a name="remarks"></a>解説

は、 `CMFCPopupMenuBar` [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md) と同時に作成され、その中に埋め込まれます。 は、 `CMFCPopupMenuBar` オブジェクトのクライアント領域全体をカバーし `CMFCPopupMenu` ます。 キーボードとマウスの入力をサポートしています。 また、この入力をと、 `CMFCPopupMenu` トップレベルのフレームウィンドウにも通信します。

## <a name="example"></a>例

オブジェクトからオブジェクトを初期化する方法を次の例に示し `CMFCPopupMenuBar` `CMFCPopupMenu` ます。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCBaseToolBar](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxpopupmenubar

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a> CMFCPopupMenuBar:: AdjustSizeImmediate

ポップアップメニューバーウィンドウのレイアウトを直ちに再計算します。 ( [CPane:: AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)をオーバーライドします。

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>パラメーター

*bRecalcLayout*<br/>
からポップアップメニューバーウィンドウのレイアウトを自動的に再計算する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a> CMFCPopupMenuBar:: BuildOrigItems

指定されたメニューリソースからポップアップメニュー項目を読み込みます。

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>パラメーター

*uiMenuResID*<br/>
から読み込むメニューリソースのメニュー ID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、そうでない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a> CMFCPopupMenuBar:: CloseDelayedSubMenu メニュー

遅延されたポップアップメニューボタンを閉じます。

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a> CMFCPopupMenuBar:: ExportToMenu

ポップアップメニューボタンからメニューを作成します。

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>戻り値

新しいメニューへのハンドルを返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a> CMFCPopupMenuBar:: FindDestintationToolBar

指定したポイントがあるツールバーを検索します。

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>パラメーター

*視点*<br/>
から画面上のポイント。

### <a name="return-value"></a>戻り値

ポイントが存在する場合は、そのツールバーへのハンドルを返します。存在しない場合は NULL を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a> CMFCPopupMenuBar:: GetCurrentMenuImageSize

メニューボタンのイメージのサイズを示します。

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>戻り値

ツールバーのメニューボタンイメージのサイズを返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a> CMFCPopupMenuBar:: GetDefaultMenuId

既定のメニュー項目の識別子を返します。

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>戻り値

ポップアップメニューバーの既定のメニュー項目の識別子を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a> CMFCPopupMenuBar:: GetLastCommandIndex

直前に呼び出されたメニューコマンドのインデックスを取得します。

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>戻り値

呼び出された最後のメニューコマンドのインデックスを返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a> CMFCPopupMenuBar:: GetOffset

ポップアップメニューバーの行オフセットを取得します。

```
int GetOffset() const;
```

### <a name="return-value"></a>戻り値

ポップアップメニューバーの行オフセットを返します。

### <a name="remarks"></a>解説

この値は、 [Cmfcpopupmenubar:: SetOffset](#setoffset)を使用して設定します。

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a> CMFCPopupMenuBar:: ImportFromMenu

指定したメニューからポップアップメニューボタンをインポートします。

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>パラメーター

*hMenu*<br/>
からポップアップメニューのボタンをインポートするメニュー。

*bShowAllCommands*<br/>
からメニューのすべてのコマンドをインポートする場合は TRUE、使用頻度が低い場合は FALSE を指定します。

### <a name="return-value"></a>戻り値

メニューボタンがメニューから正常にインポートされた場合は TRUE を返し、そうでない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a> CMFCPopupMenuBar:: IsDropDownListMode

ポップアップメニューバーがドロップダウンリストモードであるかどうかを示します。

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>戻り値

ポップアップメニューバーがドロップダウンリストモードの場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a> CMFCPopupMenuBar:: IsPaletteMode

ポップアップメニューバーがパレットモードであるかどうかを示します。

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>戻り値

パレットモードが有効な場合は TRUE を返し、そうでない場合は FALSE を返します。

### <a name="remarks"></a>解説

メニューバーがパレットモードに設定されている場合、メニュー項目は複数の列と行の数に制限されます。

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a> CMFCPopupMenuBar:: IsRibbonPanel

これがリボンパネルである (既定では FALSE) かどうかを示します。

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>戻り値

既定では FALSE を返します。これは、これがリボンパネルではないことを示します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a> CMFCPopupMenuBar:: IsRibbonPanelInRegularMode

これが通常モードのリボンパネルであるかどうかを示します (既定では FALSE)。

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>戻り値

既定では FALSE を返します。これは、これが通常モードのリボンパネルではないことを示します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a> CMFCPopupMenuBar:: LoadFromHash

アーカイブされたメニューを読み込みます。

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*hMenu*<br/>
から読み込むアーカイブ済みメニューへのハンドル。

### <a name="return-value"></a>戻り値

メニューが正常に読み込まれた場合は TRUE、それ以外の場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a> CMFCPopupMenuBar:: m_bDisableSideBarInXPMode

アプリケーションに Windows XP の外観がある場合に、灰色のサイドバーがあるかどうかを示すブール値パラメーターです。

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>解説

このメンバー変数が FALSE に設定されていて、アプリケーションの外観が Windows XP の場合、フレームワークはアプリケーションにグレーのサイドバーを描画します。

既定値は FALSE です。

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a> CMFCPopupMenuBar:: RestoreDelayedSubMenu メニュー

ポップアップメニューバーを閉じるための遅延メニューボタンを復元します。

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a> CMFCPopupMenuBar:: SetButtonStyle

指定したインデックス位置にあるツールバーボタンのスタイルを設定します。 ( [Cmfctoolbar:: SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)をオーバーライドします)。

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からスタイルが設定されるツールバーボタンの0から始まるインデックス。

*nStyle*<br/>
からボタンのスタイル。 使用可能なツールバーボタンスタイルの一覧については、「 [ツールバーコントロールスタイル](../../mfc/reference/toolbar-control-styles.md) 」を参照してください。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a> CMFCPopupMenuBar:: SetOffset

ポップアップメニューバーの行オフセットを設定します。

```cpp
void SetOffset(int iOffset);
```

### <a name="parameters"></a>パラメーター

*iOffset*<br/>
からポップアップメニューバーがオフセットされる行の数。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a> CMFCPopupMenuBar:: StartPopupMenuTimer

指定した遅延ポップアップメニューボタンのタイマーを開始します。

```cpp
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>パラメーター

*pMenuButton*<br/>
から遅延タイマーを設定するメニューボタンへのポインター。

*nDelayFactor*<br/>
から標準のメニュー遅延時間 (通常は0.5 秒 ~ 5 秒) で乗算するための、少なくとも1つの遅延係数。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)
