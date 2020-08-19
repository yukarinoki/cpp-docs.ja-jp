---
title: CMFCBaseVisualManager クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 28efe75c3c825c04c88f9f2263a3db2d83d4f3af
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561324"
---
# <a name="cmfcbasevisualmanager-class"></a>CMFCBaseVisualManager クラス

派生ビジュアルマネージャーと Windows テーマ API 間のレイヤー。

`CMFCBaseVisualManager` 使用可能な場合は UxTheme.dll を読み込み、Windows Theme API メソッドへのアクセスを管理します。

このクラスは、内部でのみ使用されます。

## <a name="syntax"></a>構文

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[CMFCBaseVisualManager:: CMFCBaseVisualManager](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` オブジェクトを構築して初期化します。|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[CMFCBaseVisualManager::D rawCheckBox](#drawcheckbox)|現在の Windows テーマを使用して、チェックボックスコントロールを描画します。|
|[CMFCBaseVisualManager::D rawComboBorder](#drawcomboborder)|現在の Windows テーマを使用して、コンボボックスの境界線を描画します。|
|[CMFCBaseVisualManager::D rawComboDropButton](#drawcombodropbutton)|現在の Windows テーマを使用して、コンボボックスのドロップダウンボタンを描画します。|
|[CMFCBaseVisualManager::D Rawpのボタン](#drawpushbutton)|現在の Windows テーマを使用してプッシュボタンを描画します。|
|[CMFCBaseVisualManager::D rawRadioButton](#drawradiobutton)|現在の Windows テーマを使用して、オプションボタンコントロールを描画します。|
|[CMFCBaseVisualManager::D rawStatusBarProgress](#drawstatusbarprogress)|現在の Windows テーマを使用して、ステータスバーコントロール ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) にプログレスバーを描画します。|
|[CMFCBaseVisualManager:: FillReBarPane](#fillrebarpane)|現在の Windows テーマを使用して rebar コントロールの背景を塗りつぶします。|
|[CMFCBaseVisualManager:: GetStandardWindowsTheme](#getstandardwindowstheme)|現在の Windows テーマを取得します。|

### <a name="protected-methods"></a>プロテクト メソッド

|||
|-|-|
|名前|説明|
|[CMFCBaseVisualManager:: CleanUpThemes](#cleanupthemes)|`CloseThemeData`で取得したすべてのハンドルのを呼び出し `UpdateSystemColors` ます。|
|[CMFCBaseVisualManager:: UpdateSystemColors](#updatesystemcolors)|を呼び出して、 `OpenThemeData` さまざまなコントロール (ウィンドウ、ツールバー、ボタンなど) を描画するハンドルを取得します。|

## <a name="remarks"></a>解説

このクラスのオブジェクトを直接インスタンス化する必要はありません。

すべてのビジュアルマネージャーの基本クラスであるため、 [Cmfcvisualmanager:: GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)を呼び出し、現在のビジュアルマネージャーへのポインターを取得し、 `CMFCBaseVisualManager` そのポインターを使用するためのメソッドにアクセスするだけです。 ただし、現在の Windows テーマを使用してコントロールを表示する必要がある場合は、インターフェイスを使用することをお勧めし `CMFCVisualManagerWindows` ます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCBaseVisualManager](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxvisualmanager

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a> CMFCBaseVisualManager:: CleanUpThemes

`CloseThemeData`で取得したすべてのハンドルのを呼び出し `UpdateSystemColors` ます。

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>解説

内部使用のみ。

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a> CMFCBaseVisualManager:: CMFCBaseVisualManager

`CMFCBaseVisualManager` オブジェクトを構築して初期化します。

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a> CMFCBaseVisualManager::D rawCheckBox

現在の Windows テーマを使用して、チェックボックスコントロールを描画します。

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

*pDC*<br/>
からデバイスコンテキストへのポインター

*rect*<br/>
からチェックボックスの外接する四角形。

*bHighlighted 表示*<br/>
からチェックボックスを強調表示するかどうかを指定します。

*nState*<br/>
[入力] オフの場合は0、チェックされた通常の場合は1

混合法線の場合は2。

*bEnabled*<br/>
からチェックボックスをオンにするかどうかを指定します。

*bPressed れた状態*<br/>
からチェックボックスをオンにするかどうかを指定します。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*NState*の値は、次のチェックボックスのスタイルに対応しています。

|nState|チェックボックスのスタイル|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a> CMFCBaseVisualManager::D rawComboBorder

現在の Windows テーマを使用して、コンボボックスの境界線を描画します。

```
virtual BOOL DrawComboBorder(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
からコンボボックスの境界線の外接する四角形。

*bDisabled*<br/>
からコンボボックスの境界線を無効にするかどうかを指定します。

*bIsDropped*<br/>
からコンボボックスの境界線をドロップダウンするかどうかを指定します。

*bIsHighlighted*<br/>
からコンボボックスの境界線を強調表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a> CMFCBaseVisualManager::D rawComboDropButton

現在の Windows テーマを使用して、コンボボックスのドロップダウンボタンを描画します。

```
virtual BOOL DrawComboDropButton(
    CDC* pDC,
    CRect rect,
    BOOL bDisabled,
    BOOL bIsDropped,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>パラメーター

*pDC*\
からデバイスコンテキストへのポインター。

*rect*\
からコンボボックスのドロップダウンボタンの外接する四角形。

*bDisabled*\
からコンボボックスのドロップダウンボタンを無効にするかどうかを指定します。

*bIsDropped*\
からコンボボックスのドロップダウンボタンをドロップダウンにするかどうかを指定します。

*bIsHighlighted*\
からコンボボックスのドロップダウンボタンを強調表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a> CMFCBaseVisualManager::D Rawpのボタン

現在の Windows テーマを使用してプッシュボタンを描画します。

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
からプッシュボタンの外接する四角形。

*pButton*<br/>
から描画する [Cmfcbutton クラス](../../mfc/reference/cmfcbutton-class.md) オブジェクトへのポインター。

*uiState*<br/>
から無効. 状態は *Pbutton*から取得されます。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a> CMFCBaseVisualManager::D rawRadioButton

現在の Windows テーマを使用して、オプションボタンコントロールを描画します。

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

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rect*<br/>
からオプションボタンの外接する四角形。

*bHighlighted 表示*<br/>
からオプションボタンを強調表示するかどうかを指定します。

*bChecked*<br/>
からオプションボタンをオンにするかどうかを指定します。

*bEnabled*<br/>
からオプションボタンを有効にするかどうかを指定します。

*bPressed れた状態*<br/>
からオプションボタンを押すかどうかを指定します。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a> CMFCBaseVisualManager::D rawStatusBarProgress

現在の Windows テーマを使用して、ステータスバーコントロール ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) の進行状況バーを描画します。

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

*pDC*<br/>
からデバイスコンテキストへのポインター。

*pStatusBar*<br/>
からステータスバーへのポインター。 この値は無視されます。

*rectProgress*<br/>
から *PDC* 座標のプログレスバーの外接する四角形。

*nProgressTotal*<br/>
から進行状況の合計値。

*nProgressCurr*<br/>
から現在の進行状況の値。

*clrBar*<br/>
から開始色。 `CMFCBaseVisualManager` これは無視されます。 派生クラスでは、カラーグラデーションに使用できます。

*clrProgressBarDest*<br/>
から最後の色。 `CMFCBaseVisualManager` これは無視されます。 派生クラスでは、カラーグラデーションに使用できます。

*clrProgressText*<br/>
から進行状況のテキストの色。 `CMFCBaseVisualManager` これは無視されます。 テキストの色はによって定義され `afxGlobalData.clrBtnText` ます。

*bProgressText*<br/>
から進行状況のテキストを表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a> CMFCBaseVisualManager:: FillReBarPane

現在の Windows テーマを使用して rebar コントロールの背景を塗りつぶします。

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*pBar*<br/>
から背景を描画する必要があるペインへのポインター。

*rectClient*<br/>
から塗りつぶす領域の外接する四角形。

### <a name="return-value"></a>戻り値

Theme API が有効な場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a> CMFCBaseVisualManager:: GetStandardWindowsTheme

現在の Windows テーマを取得します。

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>戻り値

現在選択されている Windows テーマの色。 次のいずれかの列挙値を指定できます。

- `WinXpTheme_None` -テーマが有効になっていません。

- `WinXpTheme_NonStandard` -非標準のテーマが選択されています (つまり、テーマは選択されていますが、以下の一覧からは選択されていません)。

- `WinXpTheme_Blue` -blue theme (Luna)。

- `WinXpTheme_Olive` -オリーブテーマ。

- `WinXpTheme_Silver` -シルバーテーマ。

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a> CMFCBaseVisualManager:: UpdateSystemColors

を呼び出して、 `OpenThemeData` さまざまなコントロール (ウィンドウ、ツールバー、ボタンなど) を描画するハンドルを取得します。

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>解説

内部使用のみ。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
