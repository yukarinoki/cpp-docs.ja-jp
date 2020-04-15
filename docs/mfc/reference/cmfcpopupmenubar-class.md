---
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
ms.openlocfilehash: b4693e316fd78948cfae262433fee8ca8b6ab23c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375358"
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
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|ペインのレイアウトを直ちに再計算します。 (CPane をオーバーライド[します::調整サイズイミディエイト](../../mfc/reference/cpane-class.md#adjustsizeimmediate).)|
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|指定したメニュー リソースからポップアップ メニュー項目を読み込みます。|
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|遅延ポップアップ メニュー ボタンを閉じます。|
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|ポップアップ メニュー ボタンからメニューを作成します。|
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|指定したポイントがあるツール バーを検索します。|
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|メニュー ボタン イメージのサイズを示します。|
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|既定のメニュー項目の識別子を返します。|
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|最後に呼び出されたメニュー コマンドのインデックスを取得します。|
|[CMFCPopupMenuBar::GetOffset](#getoffset)|ポップアップ メニュー バーの行オフセットを取得します。|
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|指定したメニューからポップアップ メニュー ボタンを読み込みます。|
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|ポップアップ メニュー バーがドロップダウン リスト モードかどうかを示します。|
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|ポップアップ メニュー バーがパレット モードかどうかを示します。|
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|これがリボン パネルであるかどうかを示します (既定では FALSE)。|
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|これが通常モードのリボン パネルであるかどうかを示します (既定では FALSE)。|
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|アーカイブされたメニューを読み込みます。|
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|ポップアップ メニュー バーを閉じる際に遅延したメニュー ボタンを復元します。|
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|指定したインデックス位置にあるツール バー ボタンのスタイルを設定します。 ([オーバーライドします。](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)|
|[CMFCPopupMenuBar::SetOffset](#setoffset)|ポップアップ メニュー バーの行オフセットを設定します。|
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|指定した遅延ポップアップ メニュー ボタンのタイマーを開始します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[メニューバー::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|アプリケーションが Windows XP の外観を持つときに、灰色のサイドバーを表示するかどうかを指定します。|

## <a name="remarks"></a>解説

`CMFCPopupMenuBar`は[、CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)と同時に作成され、その中に埋め込まれます。 オブジェクト`CMFCPopupMenuBar`のクライアント領域全体を`CMFCPopupMenu`カバーします。 キーボードとマウスの入力をサポートしています。 また、その入力を最上位のフレーム`CMFCPopupMenu`ウィンドウに通知します。

## <a name="example"></a>例

オブジェクトからオブジェクトを初期化する方法を次`CMFCPopupMenuBar`の例に`CMFCPopupMenu`示します。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#7](../../mfc/reference/codesnippet/cpp/cmfcpopupmenubar-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[ツールバー](../../mfc/reference/cmfcbasetoolbar-class.md)

[CMFCToolBar](../../mfc/reference/cmfctoolbar-class.md)

[CMFCPopupMenuBar](../../mfc/reference/cmfcpopupmenubar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxpopupmenubar.h

## <a name="cmfcpopupmenubaradjustsizeimmediate"></a><a name="adjustsizeimmediate"></a>メニューバー::サイズを調整イミディエイト

ポップアップ メニューバーペインのレイアウトを直ちに再計算します。 (CPane をオーバーライド[します::調整サイズイミディエイト](../../mfc/reference/cpane-class.md#adjustsizeimmediate)。

```
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```

### <a name="parameters"></a>パラメーター

*ブレカルクレイアウト*<br/>
[in]ポップアップ メニューバーペインのレイアウトを自動的に再計算する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarbuildorigitems"></a><a name="buildorigitems"></a>メニューバー::ビルドオリッグアイテム

指定したメニュー リソースからポップアップ メニュー項目を読み込みます。

```
BOOL BuildOrigItems(UINT uiMenuResID);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]読み込むメニュー リソースのメニュー ID を指定します。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、成功しなかった場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarclosedelayedsubmenu"></a><a name="closedelayedsubmenu"></a>メニューバー::終了サブメニュー

遅延したポップアップ メニュー ボタンを閉じます。

```
virtual void CloseDelayedSubMenu();
```

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarexporttomenu"></a><a name="exporttomenu"></a>メニューバー::メニューにエクスポート

ポップアップメニューボタンからメニューを作成します。

```
virtual HMENU ExportToMenu() const;
```

### <a name="return-value"></a>戻り値

新しいメニューへのハンドルを返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarfinddestintationtoolbar"></a><a name="finddestintationtoolbar"></a>メニューバー::デスティンテーションツールバーを見つける

指定したポイントがあるツール バーを検索します。

```
CMFCToolBar* FindDestintationToolBar(CPoint point);
```

### <a name="parameters"></a>パラメーター

*ポイント*<br/>
[in]画面上のポイント。

### <a name="return-value"></a>戻り値

ポイントがある場合は、そのポイントがある場合は NULL を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetcurrentmenuimagesize"></a><a name="getcurrentmenuimagesize"></a>メニューバー::次のメニューのイメージサイズ

メニュー ボタン イメージのサイズを示します。

```
virtual CSize GetCurrentMenuImageSize() const;
```

### <a name="return-value"></a>戻り値

ツール バーのメニュー ボタン イメージのサイズを返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetdefaultmenuid"></a><a name="getdefaultmenuid"></a>メニューバー::既定のメニューId

既定のメニュー項目の識別子を返します。

```
UINT GetDefaultMenuId() const;
```

### <a name="return-value"></a>戻り値

ポップアップ メニュー バーの既定のメニュー項目の識別子を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetlastcommandindex"></a><a name="getlastcommandindex"></a>メニューバー::ラストコマンドインデックス

最後に呼び出されたメニュー コマンドのインデックスを取得します。

```
static int __stdcall GetLastCommandIndex();
```

### <a name="return-value"></a>戻り値

最後に起動されたメニュー コマンドのインデックスを返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubargetoffset"></a><a name="getoffset"></a>メニューバー::ゲットオフセット

ポップアップ メニュー バーの行オフセットを取得します。

```
int GetOffset() const;
```

### <a name="return-value"></a>戻り値

ポップアップ メニュー バーの行オフセットを返します。

### <a name="remarks"></a>解説

この値は[、CMFCPopupMenuBar を](#setoffset)使用して設定されます。

## <a name="cmfcpopupmenubarimportfrommenu"></a><a name="importfrommenu"></a>メニューバー::メニューからインポート

指定したメニューからポップアップ メニュー ボタンを読み込みます。

```
virtual BOOL ImportFromMenu(
    HMENU hMenu,
    BOOL bShowAllCommands = FALSE);
```

### <a name="parameters"></a>パラメーター

*Hmenu*<br/>
[in]ポップアップ メニュー ボタンの読み込み元のメニュー。

*コマンドを表示します。*<br/>
[in]メニューのすべてのコマンドをインポートする場合は TRUE、使用されないコマンドが非表示になっている場合は FALSE。

### <a name="return-value"></a>戻り値

メニュー ボタンがメニューから正常にインポートされた場合は TRUE を返し、インポートされていない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarisdropdownlistmode"></a><a name="isdropdownlistmode"></a>メニューバー::リストダウンリストモード

ポップアップ メニュー バーがドロップダウン リスト モードかどうかを示します。

```
BOOL IsDropDownListMode() const;
```

### <a name="return-value"></a>戻り値

ポップアップ メニュー バーがドロップダウン リスト モードの場合は TRUE を返し、ドロップダウン リスト モードでない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarispalettemode"></a><a name="ispalettemode"></a>メニューバー::アイコンモード

ポップアップ メニュー バーがパレット モードかどうかを示します。

```
BOOL IsPaletteMode() const;
```

### <a name="return-value"></a>戻り値

パレット モードが有効な場合は TRUE を返し、有効でない場合は FALSE を返します。

### <a name="remarks"></a>解説

メニュー バーがパレット モードに設定されている場合、メニュー項目は複数の列に表示され、行数は制限されます。

## <a name="cmfcpopupmenubarisribbonpanel"></a><a name="isribbonpanel"></a>メニューバー::イズリボン

これがリボン パネルであるかどうかを示します (既定では FALSE)。

```
virtual BOOL IsRibbonPanel() const;
```

### <a name="return-value"></a>戻り値

既定では FALSE を返し、これがリボン パネルではないことを示します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarisribbonpanelinregularmode"></a><a name="isribbonpanelinregularmode"></a>コントロール バー::アイコン

これが通常モードのリボン パネルであるかどうかを示します (既定では FALSE)。

```
virtual BOOL IsRibbonPanelInRegularMode() const;
```

### <a name="return-value"></a>戻り値

既定では FALSE を返し、通常モードではリボン パネルではないことを示します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarloadfromhash"></a><a name="loadfromhash"></a>メニューバー::ハッシュから読み込む

アーカイブされたメニューを読み込みます。

```
BOOL LoadFromHash(HMENU hMenu);
```

### <a name="parameters"></a>パラメーター

*Hmenu*<br/>
[in]読み込むアーカイブされたメニューへのハンドル。

### <a name="return-value"></a>戻り値

メニューが正常に読み込まれた場合は TRUE を返し、読み込みできない場合は FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarm_bdisablesidebarinxpmode"></a><a name="m_bdisablesidebarinxpmode"></a>メニューバー::m_bDisableSideBarInXPMode

Windows XP の外観を持つアプリケーションに灰色のサイドバーがあるかどうかを示すブール値パラメーター。

```
BOOL m_bDisableSideBarInXPMode;
```

### <a name="remarks"></a>解説

このメンバー変数が FALSE に設定され、アプリケーションの Windows XP の外観がある場合、フレームワークはアプリケーションに灰色のサイドバーを描画します。

既定値は FALSE です。

## <a name="cmfcpopupmenubarrestoredelayedsubmenu"></a><a name="restoredelayedsubmenu"></a>メニューバー::遅延サブメニューを復元します。

ポップアップ メニュー バーを閉じる際に遅延したメニュー ボタンを復元します。

```
virtual void RestoreDelayedSubMenu();
```

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarsetbuttonstyle"></a><a name="setbuttonstyle"></a>メニューバー::ボタンスタイルを設定します。

指定したインデックス位置にあるツール バー ボタンのスタイルを設定します。 ([オーバーライドします。](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle)

```
virtual void SetButtonStyle(
    int nIndex,
    UINT nStyle);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]スタイルを設定するツール バー ボタンの 0 から始まるインデックス。

*nStyle*<br/>
[in]ボタンのスタイル。 使用可能なツールバー ボタン スタイルの一覧については、「[ツール バー コントロール](../../mfc/reference/toolbar-control-styles.md)のスタイル」を参照してください。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarsetoffset"></a><a name="setoffset"></a>メニューバー::オフセット

ポップアップ メニュー バーの行オフセットを設定します。

```
void SetOffset(int iOffset);
```

### <a name="parameters"></a>パラメーター

*iオフセット*<br/>
[in]ポップアップ メニュー バーをオフセットする行数。

### <a name="remarks"></a>解説

## <a name="cmfcpopupmenubarstartpopupmenutimer"></a><a name="startpopupmenutimer"></a>メニューバー::スタートアップポップアップメニュータイマー

指定した遅延ポップアップ メニュー ボタンのタイマーを開始します。

```
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,
    int nDelayFactor = 1);
```

### <a name="parameters"></a>パラメーター

*ボタン*<br/>
[in]遅延タイマーを設定するメニュー ボタンへのポインター。

*ディレイファクター*<br/>
[in]標準メニュー遅延時間 (通常は、半秒から 5 秒の間) を掛ける遅延係数です。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)
