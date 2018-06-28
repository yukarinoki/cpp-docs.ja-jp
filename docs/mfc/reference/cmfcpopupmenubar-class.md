---
title: CMFCPopupMenuBar クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aede6e3224149bd237ca2bb830370718105e1f83
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037759"
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
|[CMFCPopupMenuBar::AdjustSizeImmediate](#adjustsizeimmediate)|すぐに、ウィンドウのレイアウトを再計算します。 (上書き[CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate))。|  
|[CMFCPopupMenuBar::BuildOrigItems](#buildorigitems)|指定されたメニュー リソースからのポップアップ メニュー項目を読み込みます。|  
|[CMFCPopupMenuBar::CloseDelayedSubMenu](#closedelayedsubmenu)|遅延のポップアップ メニュー ボタンを閉じます。|  
|[CMFCPopupMenuBar::ExportToMenu](#exporttomenu)|ポップアップ メニュー ボタンから表示するメニューを作成します。|  
|[CMFCPopupMenuBar::FindDestintationToolBar](#finddestintationtoolbar)|指定したポイントがあるツールバーを検索します。|  
|[CMFCPopupMenuBar::GetCurrentMenuImageSize](#getcurrentmenuimagesize)|メニュー ボタンのイメージのサイズを示します。|  
|[CMFCPopupMenuBar::GetDefaultMenuId](#getdefaultmenuid)|既定のメニュー項目の識別子を返します。|  
|[CMFCPopupMenuBar::GetLastCommandIndex](#getlastcommandindex)|最後に呼び出したのメニュー コマンドのインデックスを取得します。|  
|[CMFCPopupMenuBar::GetOffset](#getoffset)|ポップアップ メニュー バーの行オフセットを取得します。|  
|[CMFCPopupMenuBar::ImportFromMenu](#importfrommenu)|指定されたメニューからのポップアップ メニュー ボタンをインポートします。|  
|[CMFCPopupMenuBar::IsDropDownListMode](#isdropdownlistmode)|ポップアップ メニュー バーが、ドロップ ダウン リスト モードにするかどうかを示します。|  
|[CMFCPopupMenuBar::IsPaletteMode](#ispalettemode)|ポップアップ メニュー バーがパレット モードであるかどうかを示します。|  
|[CMFCPopupMenuBar::IsRibbonPanel](#isribbonpanel)|リボン パネルであるかどうかを示します (`FALSE`既定)。|  
|[CMFCPopupMenuBar::IsRibbonPanelInRegularMode](#isribbonpanelinregularmode)|リボン パネル通常モードであるかどうかを示します (`FALSE`既定)。|  
|[CMFCPopupMenuBar::LoadFromHash](#loadfromhash)|アーカイブ済みのメニューを読み込みます。|  
|[CMFCPopupMenuBar::RestoreDelayedSubMenu](#restoredelayedsubmenu)|ポップアップ メニュー バーを閉じるときの遅延のメニュー ボタンを復元します。|  
|[CMFCPopupMenuBar::SetButtonStyle](#setbuttonstyle)|指定したインデックス位置には、ツールバーのボタンのスタイルを設定します。 (上書き[CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle))。|  
|[CMFCPopupMenuBar::SetOffset](#setoffset)|ポップアップ メニュー バーの行オフセットを設定します。|  
|[CMFCPopupMenuBar::StartPopupMenuTimer](#startpopupmenutimer)|指定された遅延のポップアップ メニュー ボタン用タイマーを開始します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCPopupMenuBar::m_bDisableSideBarInXPMode](#m_bdisablesidebarinxpmode)|アプリケーションがある Windows XP の外観とグレーのサイドバーが表示されるかどうかを指定します。|  
  
## <a name="remarks"></a>Remarks  
 `CMFCPopupMenuBar`と同時に作成された、 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)内に埋め込まれたとします。 `CMFCPopupMenuBar`の全体のクライアント領域を覆う、`CMFCPopupMenu`オブジェクト。 キーボードとマウス入力をサポートします。 入力とも通信、`CMFCPopupMenu`と最上位のフレーム ウィンドウにします。  
  
## <a name="example"></a>例  
 次の例では、初期化、`CMFCPopupMenuBar`オブジェクトから、`CMFCPopupMenu`オブジェクト。 このコード スニペットは、「 [クライアント サンプルの描画](../../visual-cpp-samples.md)」の一部です。  
  
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
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxpopupmenubar.h  
  
##  <a name="adjustsizeimmediate"></a>  CMFCPopupMenuBar::AdjustSizeImmediate  
 ポップアップ メニュー バー ペインのレイアウトをすぐに再計算します。 (上書き[CPane::AdjustSizeImmediate](../../mfc/reference/cpane-class.md#adjustsizeimmediate)です。  
  
```  
virtual void AdjustSizeImmediate(BOOL bRecalcLayout);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*bRecalcLayout*  
 `TRUE` ポップアップ メニュー バー ペインのレイアウトを自動的に再計算するにはそれ以外の場合、`FALSE`です。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="buildorigitems"></a>  CMFCPopupMenuBar::BuildOrigItems  
 指定されたメニュー リソースからのポップアップ メニュー項目を読み込みます。  
  
```  
BOOL BuildOrigItems(UINT uiMenuResID);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*uiMenuResID*  
 読み込むメニュー リソースのメニュー ID を指定します。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`正常終了した場合または`FALSE`しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="closedelayedsubmenu"></a>  CMFCPopupMenuBar::CloseDelayedSubMenu  
 実行が遅れているポップアップ メニュー ボタンを閉じます。  
  
```  
virtual void CloseDelayedSubMenu();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="exporttomenu"></a>  CMFCPopupMenuBar::ExportToMenu  
 ポップアップ メニュー ボタンから表示するメニューを作成します。  
  
```  
virtual HMENU ExportToMenu() const;  
```  
  
### <a name="return-value"></a>戻り値  
 新しいメニューにハンドルを返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="finddestintationtoolbar"></a>  CMFCPopupMenuBar::FindDestintationToolBar  
 指定したポイントがあるツールバーを検索します。  
  
```  
CMFCToolBar* FindDestintationToolBar(CPoint point);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*ポイント*  
 画面上のポイント。  
  
### <a name="return-value"></a>戻り値  
 ハンドルを返します、ツールバー、点がある場所 therei が、いずれかである場合または`NULL`しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getcurrentmenuimagesize"></a>  CMFCPopupMenuBar::GetCurrentMenuImageSize  
 メニュー ボタンのイメージのサイズを示します。  
  
```  
virtual CSize GetCurrentMenuImageSize() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ツールバーのメニュー ボタンのイメージのサイズを返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getdefaultmenuid"></a>  CMFCPopupMenuBar::GetDefaultMenuId  
 既定のメニュー項目の識別子を返します。  
  
```  
UINT GetDefaultMenuId() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニュー バーで、既定のメニュー項目の識別子を返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getlastcommandindex"></a>  CMFCPopupMenuBar::GetLastCommandIndex  
 最後に呼び出したのメニュー コマンドのインデックスを取得します。  
  
```  
static int __stdcall GetLastCommandIndex();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出された最後のメニュー コマンドのインデックスを返します。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="getoffset"></a>  CMFCPopupMenuBar::GetOffset  
 ポップアップ メニュー バーの行オフセットを取得します。  
  
```  
int GetOffset() const;  
```  
  
### <a name="return-value"></a>戻り値  
 ポップアップ メニュー バーの行オフセットを返します。  
  
### <a name="remarks"></a>Remarks  
 使用してこの値を設定[CMFCPopupMenuBar::SetOffset](#setoffset)です。  
  
##  <a name="importfrommenu"></a>  CMFCPopupMenuBar::ImportFromMenu  
 指定されたメニューからのポップアップ メニュー ボタンをインポートします。  
  
```  
virtual BOOL ImportFromMenu(
    HMENU hMenu,  
    BOOL bShowAllCommands = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hMenu*  
 ポップアップ メニュー ボタンのインポート元のメニュー。  
  
 [in]*bShowAllCommands*  
 `TRUE` メニューのすべてのコマンドをインポートする場合または`FALSE`場合はあまり使用されないものを非表示にすることがあります。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`メニュー ボタンは、メニューから正常にインポートされていない場合または`FALSE`しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isdropdownlistmode"></a>  CMFCPopupMenuBar::IsDropDownListMode  
 ポップアップ メニュー バーが、ドロップ ダウン リスト モードにするかどうかを示します。  
  
```  
BOOL IsDropDownListMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`ポップアップ メニュー バーは、ドロップ ダウン リスト モードの場合、または`FALSE`しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="ispalettemode"></a>  CMFCPopupMenuBar::IsPaletteMode  
 ポップアップ メニュー バーがパレット モードであるかどうかを示します。  
  
```  
BOOL IsPaletteMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`パレット モードが有効になっている場合または`FALSE`しない場合。  
  
### <a name="remarks"></a>Remarks  
 メニュー バーがパレット モードに設定されている場合は、複数の列と行の制限数にメニュー項目が表示されます。  
  
##  <a name="isribbonpanel"></a>  CMFCPopupMenuBar::IsRibbonPanel  
 リボン パネルであるかどうかを示します (`FALSE`既定)。  
  
```  
virtual BOOL IsRibbonPanel() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`FALSE`既定では、リボン パネルではないことを示すです。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="isribbonpanelinregularmode"></a>  CMFCPopupMenuBar::IsRibbonPanelInRegularMode  
 リボン パネル通常モードであるかどうかを示します (`FALSE`既定)。  
  
```  
virtual BOOL IsRibbonPanelInRegularMode() const;  
```  
  
### <a name="return-value"></a>戻り値  
 返します`FALSE`既定ではないことを示すこのリボン パネル通常モードにします。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="loadfromhash"></a>  CMFCPopupMenuBar::LoadFromHash  
 アーカイブ済みのメニューを読み込みます。  
  
```  
BOOL LoadFromHash(HMENU hMenu);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*hMenu*  
 読み込むには、アーカイブされたメニューへのハンドル。  
  
### <a name="return-value"></a>戻り値  
 返します`TRUE`、メニューが正常に読み込まれている場合または`FALSE`しない場合。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="m_bdisablesidebarinxpmode"></a>  CMFCPopupMenuBar::m_bDisableSideBarInXPMode  
 Windows XP の外観にある場合に、アプリケーションがグレーのサイドバーがかどうかを示すブール値パラメーターです。  
  
```  
BOOL m_bDisableSideBarInXPMode;  
```  
  
### <a name="remarks"></a>Remarks  
 このメンバー変数に設定されている場合`FALSE`アプリケーションが Windows XP の外観をしていると、フレームワークは、アプリケーションでグレーのサイドバーを描画します。  
  
 既定値は `FALSE` です。  
  
##  <a name="restoredelayedsubmenu"></a>  CMFCPopupMenuBar::RestoreDelayedSubMenu  
 ポップアップ メニュー バーを閉じるときの遅延のメニュー ボタンを復元します。  
  
```  
virtual void RestoreDelayedSubMenu();
```  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setbuttonstyle"></a>  CMFCPopupMenuBar::SetButtonStyle  
 指定したインデックス位置には、ツールバーのボタンのスタイルを設定します。 (上書き[CMFCToolBar::SetButtonStyle](../../mfc/reference/cmfctoolbar-class.md#setbuttonstyle))。  
  
```  
virtual void SetButtonStyle(
    int nIndex,  
    UINT nStyle);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*nIndex*  
 スタイルを設定する、ツール バー ボタンの 0 から始まるインデックス。  
  
 [in]*nStyle*  
 ボタンのスタイルです。 参照してください[ツール バー コントロールのスタイル](../../mfc/reference/toolbar-control-styles.md)利用できるツール バー ボタンのスタイルの一覧についてはします。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="setoffset"></a>  CMFCPopupMenuBar::SetOffset  
 ポップアップ メニュー バーの行オフセットを設定します。  
  
```  
void SetOffset(int iOffset);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*iOffset*  
 ポップアップ メニュー バーをオフセットするか行の数。  
  
### <a name="remarks"></a>Remarks  
  
##  <a name="startpopupmenutimer"></a>  CMFCPopupMenuBar::StartPopupMenuTimer  
 指定された遅延のポップアップ メニュー ボタン用タイマーを開始します。  
  
```  
void StartPopupMenuTimer(
    CMFCToolBarMenuButton* pMenuButton,  
    int nDelayFactor = 1);
```  
  
### <a name="parameters"></a>パラメーター  
 [in]*pMenuButton*  
 遅延タイマーを設定する対象のメニュー ボタンへのポインター。  
  
 [in]*nDelayFactor*  
 遅延係数、少なくとも 1 つに、標準のメニューの遅延時間 (0.5 秒間一般に、5 秒) での乗算に等しい。  
  
### <a name="remarks"></a>Remarks  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCColorBar クラス](../../mfc/reference/cmfccolorbar-class.md)   
 [CMFCPopupMenu クラス](../../mfc/reference/cmfcpopupmenu-class.md)
