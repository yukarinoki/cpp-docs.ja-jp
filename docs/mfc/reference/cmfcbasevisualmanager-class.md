---
title: CMFCBaseVisualManager クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::CMFCBaseVisualManager
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawCheckBox
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboBorder
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawComboDropButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawPushButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawRadioButton
- AFXVISUALMANAGER/CMFCBaseVisualManager::DrawStatusBarProgress
- AFXVISUALMANAGER/CMFCBaseVisualManager::FillReBarPane
- AFXVISUALMANAGER/CMFCBaseVisualManager::GetStandardWindowsTheme
- AFXVISUALMANAGER/CMFCBaseVisualManager::CleanUpThemes
- AFXVISUALMANAGER/CMFCBaseVisualManager::UpdateSystemColors
dev_langs:
- C++
helpviewer_keywords:
- CMFCBaseVisualManager [MFC], CMFCBaseVisualManager
- CMFCBaseVisualManager [MFC], DrawCheckBox
- CMFCBaseVisualManager [MFC], DrawComboBorder
- CMFCBaseVisualManager [MFC], DrawComboDropButton
- CMFCBaseVisualManager [MFC], DrawPushButton
- CMFCBaseVisualManager [MFC], DrawRadioButton
- CMFCBaseVisualManager [MFC], DrawStatusBarProgress
- CMFCBaseVisualManager [MFC], FillReBarPane
- CMFCBaseVisualManager [MFC], GetStandardWindowsTheme
- CMFCBaseVisualManager [MFC], CleanUpThemes
- CMFCBaseVisualManager [MFC], UpdateSystemColors
ms.assetid: d56f3afc-cdea-4de1-825a-a08999c571e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 496c6905276e789a72c55db1835187b0d4ab342a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager クラス
派生のビジュアル マネージャーと Windows テーマ API 間のレイヤー。  
  
 `CMFCBaseVisualManager` UxTheme.dll、利用できる場合を読み込んで Windows テーマ API のメソッドへのアクセスを管理します。  
  
 このクラスは内部でのみ使用されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCBaseVisualManager: public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CMFCBaseVisualManager](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` オブジェクトを構築して初期化します。|  
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::DrawCheckBox](#drawcheckbox)|現在の Windows テーマを使用して、チェック ボックス コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawComboBorder](#drawcomboborder)|現在の Windows テーマを使用して、コンボ ボックスの境界線を描画します。|  
|[CMFCBaseVisualManager::DrawComboDropButton](#drawcombodropbutton)|現在の Windows テーマを使用して、コンボ ボックスのドロップダウン ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawPushButton](#drawpushbutton)|現在の Windows テーマを使用してプッシュ ボタンを描画します。|  
|[CMFCBaseVisualManager::DrawRadioButton](#drawradiobutton)|現在の Windows テーマを使用して、ラジオ ボタン コントロールを描画します。|  
|[CMFCBaseVisualManager::DrawStatusBarProgress](#drawstatusbarprogress)|ステータス バー コントロールでの進行状況バーの描画 ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) 現在の Windows テーマを使用します。|  
|[CMFCBaseVisualManager::FillReBarPane](#fillrebarpane)|現在の Windows テーマを使用して、rebar コントロールの背景を塗りつぶします。|  
|[CMFCBaseVisualManager::GetStandardWindowsTheme](#getstandardwindowstheme)|現在の Windows テーマを取得します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|||  
|-|-|  
|名前|説明|  
|[CMFCBaseVisualManager::CleanUpThemes](#cleanupthemes)|呼び出し`CloseThemeData`で取得したすべてのハンドルの`UpdateSystemColors`します。|  
|[CMFCBaseVisualManager::UpdateSystemColors](#updatesystemcolors)|呼び出し`OpenThemeData`をさまざまなコントロールを描画するためのハンドルを取得する: ウィンドウ、ツールバー、ボタン、およびなどです。|  
  
## <a name="remarks"></a>コメント  
 このクラスのオブジェクトを直接インスタンス化する必要はありません。  
  
 だけに呼び出すことができます、すべてのビジュアル マネージャーの基本クラスになっているため[CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)現在 Visual マネージャーへのポインターを取得、およびアクセスの方法で、`CMFCBaseVisualManager`そのポインターを使用します。 ただし、現在の Windows テーマを使用して、コントロールを表示する場合は、お勧めを使用する、`CMFCVisualManagerWindows`インターフェイスです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxvisualmanager.h  
  
##  <a name="cleanupthemes"></a>  CMFCBaseVisualManager::CleanUpThemes  
 呼び出し`CloseThemeData`で取得したすべてのハンドルの`UpdateSystemColors`します。  
  
```  
void CleanUpThemes();
```  
  
### <a name="remarks"></a>コメント  
 内部使用のみ。  
  
##  <a name="cmfcbasevisualmanager"></a>  CMFCBaseVisualManager::CMFCBaseVisualManager  
 `CMFCBaseVisualManager` オブジェクトを構築して初期化します。  
  
```  
CMFCBaseVisualManager();
```  
  
##  <a name="drawcheckbox"></a>  CMFCBaseVisualManager::DrawCheckBox  
 現在の Windows テーマを使用して、チェック ボックス コントロールを描画します。  
  
```  
virtual BOOL DrawCheckBox(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    int nState,   
    BOOL bEnabled,   
    BOOL bPressed);

);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター  
  
 [入力] `rect`  
 チェック ボックスの外接する四角形。  
  
 [入力] `bHighlighted`  
 チェック ボックスが強調表示されているかどうかを指定します。  
  
 [入力] `nState`  
 0 の通常のチェックをオフの場合、1  
  
 混合で通常の 2。  
  
 [入力] `bEnabled`  
 チェック ボックスをオンになっているかどうかを指定します。  
  
 [入力] `bPressed`  
 チェック ボックスが押されたかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
### <a name="remarks"></a>コメント  
 値`nState`次のチェック ボックスのスタイルに対応します。  
  
|%n 状態|チェック ボックス スタイル|  
|------------|---------------------|  
|0|CBS_UNCHECKEDNORMAL|  
|1|CBS_CHECKEDNORMAL|  
|2|CBS_MIXEDNORMAL|  
  
##  <a name="drawcomboborder"></a>  CMFCBaseVisualManager::DrawComboBorder  
 現在の Windows テーマを使用してコンボ ボックスの枠線を描画します。  
  
```  
virtual BOOL DrawComboBorder(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 コンボ ボックスの枠線の外接する四角形。  
  
 [入力] `bDisabled`  
 コンボ ボックスの枠線が無効になっているかどうかを指定します。  
  
 [入力] `bIsDropped`  
 コンボ ボックスの枠線が削除されるかどうかを指定します。  
  
 [入力] `bIsHighlighted`  
 コンボ ボックスの枠線が強調表示されているかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
##  <a name="drawcombodropbutton"></a>  CMFCBaseVisualManager::DrawComboDropButton  
 現在の Windows テーマを使用して、コンボ ボックスのドロップダウン ボタンを描画します。  
  
```  
virtual BOOL DrawComboDropButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bDisabled,   
    BOOL bIsDropped,   
    BOOL bIsHighlighted);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|[入力] `pDC`|デバイス コンテキストへのポインター。|  
|[入力] `rect`|コンボ ボックスのドロップダウン ボタンの外接する四角形。|  
|[入力] `bDisabled`|コンボ ボックスのドロップダウン ボタンが無効になっているかどうかを指定します。|  
|[入力] `bIsDropped`|コンボ ボックスのドロップダウン ボタンのドロップダウンがされているかどうかを指定します。|  
|[入力] `bIsHighlighted`|コンボ ボックスのドロップダウン ボタンが強調表示されているかどうかを指定します。|  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
##  <a name="drawpushbutton"></a>  CMFCBaseVisualManager::DrawPushButton  
 現在の Windows テーマを使用してプッシュ ボタンを描画します。  
  
```  
virtual BOOL DrawPushButton(
    CDC* pDC,   
    CRect rect,   
    CMFCButton* pButton,   
    UINT uiState);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 プッシュ ボタンの外接する四角形。  
  
 [入力] `pButton`  
 ポインター、 [CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)を描画するオブジェクト。  
  
 [入力] `uiState`  
 無視されます。 状態がから取得した`pButton`です。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
##  <a name="drawradiobutton"></a>  CMFCBaseVisualManager::DrawRadioButton  
 現在の Windows テーマを使用して、ラジオ ボタン コントロールを描画します。  
  
```  
virtual BOOL DrawRadioButton(
    CDC* pDC,   
    CRect rect,   
    BOOL bHighlighted,   
    BOOL bChecked,   
    BOOL bEnabled,   
    BOOL bPressed);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `rect`  
 オプション ボタンの外接する四角形。  
  
 [入力] `bHighlighted`  
 ラジオ ボタンが強調表示されているかどうかを指定します。  
  
 [入力] `bChecked`  
 ラジオ ボタンが選択されているかどうかを指定します。  
  
 [入力] `bEnabled`  
 ラジオ ボタンが有効になっているかどうかを指定します。  
  
 [入力] `bPressed`  
 ラジオ ボタンが押されたかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
##  <a name="drawstatusbarprogress"></a>  CMFCBaseVisualManager::DrawStatusBarProgress  
 ステータス バー コントロールの進行状況バーを描画 ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) 現在の Windows テーマを使用します。  
  
```  
virtual BOOL DrawStatusBarProgress(
    CDC* pDC,   
    CMFCStatusBar* pStatusBar,   
    CRect rectProgress,   
    int nProgressTotal,   
    int nProgressCurr,  
    COLORREF clrBar,   
    COLORREF clrProgressBarDest,   
    COLORREF clrProgressText,   
    BOOL bProgressText);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pStatusBar`  
 ステータス バーへのポインター。 この値は無視されます。  
  
 [入力] `rectProgress`  
 進行状況バーの外接する四角形`pDC`座標。  
  
 [入力] `nProgressTotal`  
 全体の進行状況の値です。  
  
 [入力] `nProgressCurr`  
 現在の進行状況の値。  
  
 [入力] `clrBar`  
 開始色です。 `CMFCBaseVisualManager` これは無視されます。 派生クラスを色のグラデーションを使用できます。  
  
 [入力] `clrProgressBarDest`  
 最後の色。 `CMFCBaseVisualManager` これは無視されます。 派生クラスを色のグラデーションを使用できます。  
  
 [入力] `clrProgressText`  
 進行状況のテキストの色。 `CMFCBaseVisualManager` これは無視されます。 テキストの色がによって定義された`afxGlobalData.clrBtnText`です。  
  
 [入力] `bProgressText`  
 進行状況のテキストを表示するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
##  <a name="fillrebarpane"></a>  CMFCBaseVisualManager::FillReBarPane  
 現在の Windows テーマを使用して、rebar コントロールの背景を塗りつぶします。  
  
```  
virtual void FillReBarPane(
    CDC* pDC,   
    CBasePane* pBar,   
    CRect rectClient);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pDC`  
 デバイス コンテキストへのポインター。  
  
 [入力] `pBar`  
 背景を描画するウィンドウへのポインター。  
  
 [入力] `rectClient`  
 格納する領域に外接する四角形。  
  
### <a name="return-value"></a>戻り値  
 `TRUE` テーマの API が有効である場合それ以外の場合`FALSE`です。  
  
##  <a name="getstandardwindowstheme"></a>  CMFCBaseVisualManager::GetStandardWindowsTheme  
 現在の Windows テーマを取得します。  
  
```  
virtual WinXpTheme GetStandardWindowsTheme();
```  
  
### <a name="return-value"></a>戻り値  
 現在選択されている Windows テーマの色。 次の列挙値のいずれかを指定できます。  
  
- `WinXpTheme_None` -有効になっているテーマはありません。  
  
- `WinXpTheme_NonStandard` -(つまり、以下の一覧から [なし] が、テーマが選択されている) 非標準のテーマを選択します。  
  
- `WinXpTheme_Blue` -青のテーマ (Luna)。  
  
- `WinXpTheme_Olive` -オリーブ テーマ。  
  
- `WinXpTheme_Silver` -銀色のテーマ。  
  
##  <a name="updatesystemcolors"></a>  CMFCBaseVisualManager::UpdateSystemColors  
 呼び出し`OpenThemeData`をさまざまなコントロールを描画するためのハンドルを取得する: ウィンドウ、ツールバー、ボタン、およびなどです。  
  
```  
void UpdateSystemColors();
```  
  
### <a name="remarks"></a>コメント  
 内部使用のみ。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
