---
title: クラス
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
ms.openlocfilehash: ac64a3feac5d124c2bfa67fc857dad5045c2dd28
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754890"
---
# <a name="cmfcbasevisualmanager-class"></a>クラス

派生ビジュアル マネージャーと Windows テーマ API 間のレイヤー。

`CMFCBaseVisualManager`UxTheme.dll が使用可能な場合は読み込み、Windows テーマ API メソッドへのアクセスを管理します。

このクラスは内部使用専用です。

## <a name="syntax"></a>構文

```
class CMFCBaseVisualManager: public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[マネージャーマネージャー](#cmfcbasevisualmanager)|`CMFCBaseVisualManager` オブジェクトを構築して初期化します。|
|`CMFCBaseVisualManager::~CMFCBaseVisualManager`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[:Dロー チェック ボックス](#drawcheckbox)|現在の Windows テーマを使用してチェック ボックス コントロールを描画します。|
|[をクリック :Dします。](#drawcomboborder)|現在の Windows テーマを使用してコンボ ボックスの境界線を描画します。|
|[をクリック :Dします。](#drawcombodropbutton)|現在の Windows テーマを使用してコンボ ボックスのドロップダウン ボタンを描画します。|
|[ダブルクリックトビラのマネージャー::Dロープッシュボタン](#drawpushbutton)|現在の Windows テーマを使用してプッシュ ボタンを描画します。|
|[:Dローラジオボタン](#drawradiobutton)|現在の Windows テーマを使用して、ラジオ ボタン コントロールを描画します。|
|[をクリック :Dします。](#drawstatusbarprogress)|現在の Windows テーマを使用して、ステータス バー コントロール ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) にプログレス バーを描画します。|
|[ウィンドウウィンドウ::フィルバーペイン](#fillrebarpane)|現在の Windows テーマを使用して、Rebar コントロールの背景を塗りつぶします。|
|[ウィンドウズマネージャー::ウィンドウズテーマ](#getstandardwindowstheme)|現在の Windows テーマを取得します。|

### <a name="protected-methods"></a>プロテクト メソッド

|||
|-|-|
|名前|説明|
|[テーマをクリーンアップします。](#cleanupthemes)|で`CloseThemeData`取得されたすべてのハンドルを`UpdateSystemColors`呼び出します。|
|[システムカラーの更新](#updatesystemcolors)|ウィンドウ`OpenThemeData`、ツールバー、ボタンなど、さまざまなコントロールを描画するためのハンドルを取得するための呼び出し。|

## <a name="remarks"></a>解説

このクラスのオブジェクトを直接インスタンス化する必要はありません。

すべてのビジュアル マネージャーの基本クラスであるため[、CMFCVisualManager::GetInstance](../../mfc/reference/cmfcvisualmanager-class.md#getinstance)を呼び出して、現在のビジュアル マネージャーへのポインターを取得し、そのポインターを`CMFCBaseVisualManager`使用するためのメソッドにアクセスするだけです。 ただし、現在の Windows テーマを使用してコントロールを表示する必要がある場合は、インターフェイスを`CMFCVisualManagerWindows`使用することをおし、

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[ビジュアル マネージャー](../../mfc/reference/cmfcbasevisualmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx ビジュアルマネージャー.h

## <a name="cmfcbasevisualmanagercleanupthemes"></a><a name="cleanupthemes"></a>テーマをクリーンアップします。

で`CloseThemeData`取得されたすべてのハンドルを`UpdateSystemColors`呼び出します。

```cpp
void CleanUpThemes();
```

### <a name="remarks"></a>解説

内部使用専用です。

## <a name="cmfcbasevisualmanagercmfcbasevisualmanager"></a><a name="cmfcbasevisualmanager"></a>マネージャーマネージャー

`CMFCBaseVisualManager` オブジェクトを構築して初期化します。

```
CMFCBaseVisualManager();
```

## <a name="cmfcbasevisualmanagerdrawcheckbox"></a><a name="drawcheckbox"></a>:Dロー チェック ボックス

現在の Windows テーマを使用してチェック ボックス コントロールを描画します。

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
[in]デバイス コンテキストへのポインター

*Rect*<br/>
[in]チェック ボックスの外接する四角形。

*b強調表示*<br/>
[in]チェック ボックスを強調表示するかどうかを指定します。

*nステート*<br/>
[in] 0 がチェックされていない場合は、1 はチェックされた正常、

混合正常の場合は 2。

*b有効*<br/>
[in]チェック ボックスを有効にするかどうかを指定します。

*bPressed*<br/>
[in]チェック ボックスを押すかどうかを指定します。

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*nState*の値は、次のチェック ボックス スタイルに対応します。

|nステート|チェック ボックスのスタイル|
|------------|---------------------|
|0|CBS_UNCHECKEDNORMAL|
|1|CBS_CHECKEDNORMAL|
|2|CBS_MIXEDNORMAL|

## <a name="cmfcbasevisualmanagerdrawcomboborder"></a><a name="drawcomboborder"></a>をクリック :Dします。

現在の Windows テーマを使用してコンボ ボックスの境界線を描画します。

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
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]コンボ ボックスの枠線の外接する四角形。

*b無効*<br/>
[in]コンボ ボックスの境界線を無効にするかどうかを指定します。

*ビスドロップ*<br/>
[in]コンボ ボックスの境界線を下にドロップするかどうかを指定します。

*bIs強調表示*<br/>
[in]コンボ ボックスの境界線を強調表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawcombodropbutton"></a><a name="drawcombodropbutton"></a>をクリック :Dします。

現在の Windows テーマを使用してコンボ ボックスのドロップダウン ボタンを描画します。

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
|*pDC*|[in]デバイス コンテキストへのポインター。|
|*Rect*|[in]コンボ ボックスのドロップダウン ボタンの外接する四角形。|
|*b無効*|[in]コンボ ボックスのドロップダウン ボタンが無効かどうかを指定します。|
|*ビスドロップ*|[in]コンボ ボックスのドロップダウン ボタンをドロップダウンするかどうかを指定します。|
|*bIs強調表示*|[in]コンボ ボックスのドロップダウン ボタンを強調表示するかどうかを指定します。|

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawpushbutton"></a><a name="drawpushbutton"></a>ダブルクリックトビラのマネージャー::Dロープッシュボタン

現在の Windows テーマを使用してプッシュ ボタンを描画します。

```
virtual BOOL DrawPushButton(
    CDC* pDC,
    CRect rect,
    CMFCButton* pButton,
    UINT uiState);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]プッシュ ボタンの外接する四角形。

*ボタン*<br/>
[in]描画する[CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)オブジェクトへのポインター。

*ui状態*<br/>
[in]無視。 状態は*pButton*から取得されます。

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawradiobutton"></a><a name="drawradiobutton"></a>:Dローラジオボタン

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

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Rect*<br/>
[in]ラジオ ボタンの外接する四角形。

*b強調表示*<br/>
[in]ラジオ ボタンを強調表示するかどうかを指定します。

*bチェック*<br/>
[in]ラジオ ボタンをオンにするかどうかを指定します。

*b有効*<br/>
[in]ラジオ ボタンを有効にするかどうかを指定します。

*bPressed*<br/>
[in]ラジオ ボタンを押すかどうかを指定します。

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerdrawstatusbarprogress"></a><a name="drawstatusbarprogress"></a>をクリック :Dします。

現在の Windows テーマを使用して、ステータス バー コントロール ( [CMFCStatusBar クラス](../../mfc/reference/cmfcstatusbar-class.md)) に進行状況バーを描画します。

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
[in]デバイス コンテキストへのポインター。

*をクリックします。*<br/>
[in]ステータス バーへのポインター。 この値は無視されます。

*レクトプログレス*<br/>
[in]*pDC*座標の進行状況バーの外接する四角形。

*nProgressTotal*<br/>
[in]進行状況の合計値。

*nProgressCurr*<br/>
[in]現在の進行状況の値。

*clrBar*<br/>
[in]開始色。 `CMFCBaseVisualManager`これは無視されます。 派生クラスは、カラー グラデーションに使用できます。

*clrProgressBarDest*<br/>
[in]終了色。 `CMFCBaseVisualManager`これは無視されます。 派生クラスは、カラー グラデーションに使用できます。

*clrProgressText*<br/>
[in]進捗状況のテキストの色。 `CMFCBaseVisualManager`これは無視されます。 テキストの色は で`afxGlobalData.clrBtnText`定義されます。

*bProgressText*<br/>
[in]進行状況テキストを表示するかどうかを指定します。

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagerfillrebarpane"></a><a name="fillrebarpane"></a>ウィンドウウィンドウ::フィルバーペイン

現在の Windows テーマを使用して、Rebar コントロールの背景を塗りつぶします。

```
virtual void FillReBarPane(
    CDC* pDC,
    CBasePane* pBar,
    CRect rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*pバー*<br/>
[in]背景を描画するペインへのポインター。

*レクトクライアント*<br/>
[in]塗りつぶす領域の外接する四角形。

### <a name="return-value"></a>戻り値

テーマ API が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcbasevisualmanagergetstandardwindowstheme"></a><a name="getstandardwindowstheme"></a>ウィンドウズマネージャー::ウィンドウズテーマ

現在の Windows テーマを取得します。

```
virtual WinXpTheme GetStandardWindowsTheme();
```

### <a name="return-value"></a>戻り値

現在選択されている Windows テーマの色。 次の列挙値のいずれかです。

- `WinXpTheme_None`- テーマが有効になっていません。

- `WinXpTheme_NonStandard`- 標準以外のテーマが選択されています(テーマが選択されているが、下のリストからは選択されていません)。

- `WinXpTheme_Blue`- 青いテーマ(ルナ)。

- `WinXpTheme_Olive`- オリーブのテーマ

- `WinXpTheme_Silver`- シルバーのテーマ。

## <a name="cmfcbasevisualmanagerupdatesystemcolors"></a><a name="updatesystemcolors"></a>システムカラーの更新

ウィンドウ`OpenThemeData`、ツールバー、ボタンなど、さまざまなコントロールを描画するためのハンドルを取得するための呼び出し。

```cpp
void UpdateSystemColors();
```

### <a name="remarks"></a>解説

内部使用専用です。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
