---
title: AFX_GLOBAL_DATA 構造体
ms.date: 11/04/2016
f1_keywords:
- AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA
- AFXGLOBALS/AFX_GLOBAL_DATA::CleanUp
- AFXGLOBALS/AFX_GLOBAL_DATA::D2D1MakeRotateMatrix
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawParentBackground
- AFXGLOBALS/AFX_GLOBAL_DATA::DrawTextOnGlass
- AFXGLOBALS/AFX_GLOBAL_DATA::ExcludeTag
- AFXGLOBALS/AFX_GLOBAL_DATA::GetColor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetDirect2dFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetHandCursor
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList
- AFXGLOBALS/AFX_GLOBAL_DATA::GetITaskbarList3
- AFXGLOBALS/AFX_GLOBAL_DATA::GetNonClientMetrics
- AFXGLOBALS/AFX_GLOBAL_DATA::GetShellAutohideBars
- AFXGLOBALS/AFX_GLOBAL_DATA::GetTextHeight
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWICFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::GetWriteFactory
- AFXGLOBALS/AFX_GLOBAL_DATA::InitD2D
- AFXGLOBALS/AFX_GLOBAL_DATA::Is32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
- AFXGLOBALS/AFX_GLOBAL_DATA::IsDwmCompositionEnabled
- AFXGLOBALS/AFX_GLOBAL_DATA::IsHighContrastMode
- AFXGLOBALS/AFX_GLOBAL_DATA::OnSettingChange
- AFXGLOBALS/AFX_GLOBAL_DATA::RegisterWindowClass
- AFXGLOBALS/AFX_GLOBAL_DATA::ReleaseTaskBarRefs
- AFXGLOBALS/AFX_GLOBAL_DATA::Resume
- AFXGLOBALS/AFX_GLOBAL_DATA::SetLayeredAttrib
- AFXGLOBALS/AFX_GLOBAL_DATA::SetMenuFont
- AFXGLOBALS/AFX_GLOBAL_DATA::ShellCreateItemFromParsingName
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateFonts
- AFXGLOBALS/AFX_GLOBAL_DATA::UpdateSysColors
- AFXGLOBALS/AFX_GLOBAL_DATA::EnableAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsAccessibilitySupport
- AFXGLOBALS/AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport
- AFXGLOBALS/AFX_GLOBAL_DATA::bIsWindows7
- AFXGLOBALS/AFX_GLOBAL_DATA::clrActiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::clrInactiveCaptionGradient
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons
- AFXGLOBALS/AFX_GLOBAL_DATA::m_bUseSystemFont
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurHand
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretch
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hcurStretchVert
- AFXGLOBALS/AFX_GLOBAL_DATA::m_hiconTool
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessDock
- AFXGLOBALS/AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat
helpviewer_keywords:
- AFX_GLOBAL_DATA structure [MFC]
- AFX_GLOBAL_DATA constructor
ms.assetid: c7abf2fb-ad5e-4336-a01d-260c29ed53a2
ms.openlocfilehash: 0361d535a31526c5f7b79fdd4eab046dad0435cc
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752873"
---
# <a name="afx_global_data-structure"></a>AFX_GLOBAL_DATA 構造体

`AFX_GLOBAL_DATA` 構造体は、フレームワークを管理するため、またはアプリケーションの外観および動作をカスタマイズするために使用されるフィールドおよびメソッドを格納します。

## <a name="syntax"></a>構文

```
struct AFX_GLOBAL_DATA
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`|`AFX_GLOBAL_DATA` 構造体を構築します。|
|`AFX_GLOBAL_DATA::~AFX_GLOBAL_DATA`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[AFX_GLOBAL_DATA::CleanUp](#cleanup)|ブラシ、フォント、DLL など、フレームワークにより割り当てられたリソースを解放します。|
|[AFX_GLOBAL_DATA::D2D1MakeRotateMatrix](#d2d1makerotatematrix)|指定した点を中心に指定した角度ずつ回転する回転変換を作成します。|
|[AFX_GLOBAL_DATA::DrawParentBackground](#drawparentbackground)|指定領域にコントロールの親の背景を描画します。|
|[AFX_GLOBAL_DATA::DrawTextOnGlass](#drawtextonglass)|指定されたテーマの視覚スタイルで、指定されたテキストを描画します。|
|[AFX_GLOBAL_DATA::ExcludeTag](#excludetag)|指定された XML タグ ペアを、指定されたバッファーから削除します。|
|[AFX_GLOBAL_DATA::GetColor](#getcolor)|指定されたユーザー インターフェイス要素の現在の色を取得します。|
|[AFX_GLOBAL_DATA::GetDirect2dFactory](#getdirect2dfactory)|グローバル データに格納されている `ID2D1Factory` インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。|
|[AFX_GLOBAL_DATA::GetHandCursor](#gethandcursor)|手の形をした組み込みカーソル (識別子は `IDC_HAND`) を取得します。|
|[AFX_GLOBAL_DATA::GetITaskbarList](#getitaskbarlist)|ITaskBarList インターフェイスへのポインターを作成し、グローバル データに格納します。|
|[AFX_GLOBAL_DATA::GetITaskbarList3](#getitaskbarlist3)|ITaskBarList3 インターフェイスへのポインターを作成し、グローバル データに格納します。|
|[AFX_GLOBAL_DATA::GetNonClientMetrics](#getnonclientmetrics)|最小化されていないウィンドウの非クライアント領域に関連付けられたメトリックを取得します。|
|[AFX_GLOBAL_DATA::GetShellAutohideBars](#getshellautohidebars)|シェルの自動非表示バーの位置を決定します。|
|[AFX_GLOBAL_DATA::GetTextHeight](#gettextheight)|現在のフォントのテキスト文字の高さを取得します。|
|[AFX_GLOBAL_DATA::GetWICFactory](#getwicfactory)|グローバル データに格納されている `IWICImagingFactory` インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。|
|[AFX_GLOBAL_DATA::GetWriteFactory](#getwritefactory)|グローバル データに格納されている `IDWriteFactory` インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。|
|[AFX_GLOBAL_DATA::InitD2D](#initd2d)|`D2D`、 `DirectWrite`、および `WIC` の各ファクトリを初期化します。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|定義済みの 32 ビット アイコンがサポートされているかどうかを示します。|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D` が初期化されているかどうかを調べます。|
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Windows の [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) のメソッドを簡単な方法で呼び出すことができます。|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|イメージが現在、ハイ コントラストで表示されているかどうかを判定します。|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|デスクトップのメニュー アニメーションとタスクバーの自動非表示機能の現在の状態を検出します。|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|指定された MFC ウィンドウ クラスを登録します。|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|GetITaskbarList メソッドおよび GetITaskbarList3 メソッドを通じて取得されたインターフェイスを解放します。|
|[AFX_GLOBAL_DATA::Resume](#resume)|Windows の [テーマと視覚スタイル](/windows/win32/Controls/visual-styles-overview)をサポートするメソッドにアクセスする内部関数ポインターを再初期化します。|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Windows の [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) メソッドを簡単な方法で呼び出すことができます。|
|[AFX_GLOBAL_DATA::SetMenuFont](#setmenufont)|指定された論理フォントを作成します。|
|[AFX_GLOBAL_DATA::ShellCreateItemFromParsingName](#shellcreateitemfromparsingname)|解析名からシェル項目オブジェクトを作成して初期化します。|
|[AFX_GLOBAL_DATA::UpdateFonts](#updatefonts)|フレームワークにより使用される論理フォントを再初期化します。|
|[AFX_GLOBAL_DATA::UpdateSysColors](#updatesyscolors)|フレームワークで使用される色、色深度、ブラシ、ペン、およびイメージを初期化します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)|Microsoft Active Accessibility のサポートを有効または無効にします。 Active Accessibility は、ユーザー インターフェイス要素に関する情報を公開するための信頼できる方法を提供します。|
|[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)|Microsoft Active Accessibility のサポートが有効かどうかを示します。|
|[AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable](#iswindowslayersupportavailable)|オペレーティング システムがレイヤード ウィンドウをサポートするかどうかを示します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport](#bisosalphablendingsupport)|現在のオペレーティング システムがアルファ ブレンドをサポートするかどうかを示します。|
|[AFX_GLOBAL_DATA::bIsWindows7](#biswindows7)|アプリケーションが Windows 7 OS 以上で実行されているかどうかを示します。|
|[AFX_GLOBAL_DATA::clrActiveCaptionGradient](#clractivecaptiongradient)|アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。|
|[AFX_GLOBAL_DATA::clrInactiveCaptionGradient](#clrinactivecaptiongradient)|アクティブでないキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。|
|[AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons](#m_busebuiltin32biticons)|事前定義された 32 ビット カラー アイコンと低解像度のアイコンのどちらをフレームワークで使用するかを指定します。|
|[AFX_GLOBAL_DATA::m_bUseSystemFont](#m_busesystemfont)|メニュー、ツール バー、およびリボンに対してシステム フォントが使用されるかどうかを示します。|
|[AFX_GLOBAL_DATA::m_hcurHand](#m_hcurhand)|手の形のカーソルのハンドルを格納します。|
|[AFX_GLOBAL_DATA::m_hcurStretch](#m_hcurstretch)|水平方向の伸縮カーソルのハンドルを格納します。|
|[AFX_GLOBAL_DATA::m_hcurStretchVert](#m_hcurstretchvert)|垂直方向の伸縮カーソルのハンドルを格納します。|
|[AFX_GLOBAL_DATA::m_hiconTool](#m_hicontool)|ツール アイコンのハンドルを格納します。|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin](#m_nautohidetoolbarmargin)|左端の自動的に隠すツール バーからドッキング バーの左側までのオフセットを指定します。|
|[AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing](#m_nautohidetoolbarspacing)|自動的に隠すツール バーの間の間隔を指定します。|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessDock](#m_ndragframethicknessdock)|ドッキング状態を知らせるのに使用するドラッグ フレームの幅を指定します。|
|[AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat](#m_ndragframethicknessfloat)|フローティング状態を知らせるのに使用するドラッグ フレームの幅を指定します。|

### <a name="remarks"></a>解説

`AFX_GLOBAL_DATA` 構造体内のデータのほとんどは、アプリケーションの起動時に初期化されます。

### <a name="inheritance-hierarchy"></a>継承階層

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>必要条件

**ヘッダー :** afxglobals.h

## <a name="afx_global_databisosalphablendingsupport"></a><a name="bisosalphablendingsupport"></a>AFX_GLOBAL_DATA::bisosAlphaブレンドサポート

オペレーティング システムがアルファ ブレンドをサポートするかどうかを示します。

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>解説

TRUE はアルファ ブレンディングがサポートされていることを示します。それ以外の場合は FALSE。

## <a name="afx_global_datacleanup"></a><a name="cleanup"></a>AFX_GLOBAL_DATA::クリーンアップ

ブラシ、フォント、DLL など、フレームワークにより割り当てられたリソースを解放します。

```cpp
void CleanUp();
```

## <a name="afx_global_datad2d1makerotatematrix"></a><a name="d2d1makerotatematrix"></a>AFX_GLOBAL_DATA::D2D1回転マトリックス

指定した点を中心に指定した角度ずつ回転する回転変換を作成します。

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>パラメーター

*angle*<br/>
時計回りの回転角度 (°)。

*センター*<br/>
回転するポイント。

*マトリックス*<br/>
このメソッドが返されるときに、新しい回転変換を格納します。 このパラメーターのストレージを割り振る必要があります。

### <a name="return-value"></a>戻り値

成功した場合はS_OKを返し、それ以外の場合はエラー値を返します。

## <a name="afx_global_datadrawparentbackground"></a><a name="drawparentbackground"></a>AFX_GLOBAL_DATA::Dローペアレントバックグラウンド

指定領域にコントロールの親の背景を描画します。

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]コントロールのウィンドウへのポインター。

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*Lprect*<br/>
[in]描画する領域に境界を持つ四角形へのポインター。 既定値は NULL です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="afx_global_datadrawtextonglass"></a><a name="drawtextonglass"></a>AFX_GLOBAL_DATA::Dローテキストオングラス

指定されたテーマの視覚スタイルで、指定されたテキストを描画します。

```
BOOL DrawTextOnGlass(
    HTHEME hTheme,
    CDC* pDC,
    int iPartId,
    int iStateId,
    CString strText,
    CRect rect,
    DWORD dwFlags,
    int nGlowSize = 0,
    COLORREF clrText = (COLORREF)-1);
```

### <a name="parameters"></a>パラメーター

*hTheme*<br/>
[in]ウィンドウのテーマ データへのハンドル、または NULL。 フレームワークは、このパラメーターが NULL ではなく、テーマがサポートされている場合、指定されたテーマを使用してテキストを描画します。 それ以外の場合、フレームワークは、テーマを使用せずにテキストを描画します。

HTHEME を作成するには[、OpenThemeData](/windows/win32/api/uxtheme/nf-uxtheme-openthemedata)メソッドを使用します。

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*をクリックします。*<br/>
[in]目的のテキストの外観を持つコントロールパーツ。 詳細については、「 [Parts and States (パーツと状態)](/windows/win32/controls/parts-and-states)」の表の「Parts (パーツ)」列を参照してください。 この値が 0 の場合、テキストは既定のフォント、またはデバイス コンテキストに選択されているフォントで描画されます。

*を指定します。*<br/>
[in]目的のテキストの外観を持つコントロールの状態。 詳細については、「 [Parts and States (パーツと状態)](/windows/win32/controls/parts-and-states)」の表の「States (状態)」列を参照してください。

*str テキスト*<br/>
[in]描画するテキスト。

*Rect*<br/>
[in]指定したテキストが描画される領域の境界。

*dwFlags*<br/>
[in]指定したテキストの描画方法を指定するフラグのビットごとの組み合わせ (OR)。

*hTheme*パラメーターが`NULL`サポートされていない場合、またはテーマがサポートされておらず、有効になっていない場合は[、cdc::DrawText](../../mfc/reference/cdc-class.md#drawtext)メソッドの*nFormat*パラメーターは有効なフラグを記述します。 テーマがサポートされている場合は[、DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)メソッドの*dwFlags*パラメーターは、有効なフラグを記述します。

*nグローサイズ*<br/>
[in]指定したテキストを描画する前に背景に描画されるグロー効果のサイズ。 既定値は 0 です。

*clrText*<br/>
[in]指定したテキストが描画される色。 既定値は既定の色です。

### <a name="return-value"></a>戻り値

指定したテキストの描画にテーマを使用する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

テーマは、アプリケーションの視覚スタイルを定義します。 hTheme パラメーターが NULL の場合、または[DrawThemeTextEx](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)メソッドがサポートされていない場合、または[デスクトップ ウィンドウ マネージャー](/windows/win32/dwm/dwm-overview) (DWM) コンポジションが無効になっている場合は、テーマを使用してテキストを描画しません。 *hTheme*

## <a name="afx_global_dataenableaccessibilitysupport"></a><a name="enableaccessibilitysupport"></a>AFX_GLOBAL_DATA::アクセシビリティサポートを有効にする

Microsoft Active Accessibility のサポートを有効または無効にします。

```cpp
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]ユーザー補助サポートを有効にする場合は TRUE。ユーザー補助サポートを無効にする場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

アクティブ アクセシビリティは、プログラムと Windows オペレーティング システムが支援技術製品と連携する方法を向上させる COM ベースのテクノロジです。 ユーザー インターフェイス要素に関する情報を公開するための信頼性の高いメソッドを提供します。 ただし、Microsoft UI オートメーションと呼ばれる新しいアクセシビリティ モデルが利用可能になりました。 2 つのテクノロジの比較については、「 [UI オートメーションと Microsoft のアクティブなアクセシビリティ](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)」を参照してください。

[AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport)メソッドを使用して、マイクロソフトのアクティブ なアクセシビリティ サポートが有効になっているかどうかを確認します。

## <a name="afx_global_dataexcludetag"></a><a name="excludetag"></a>AFX_GLOBAL_DATA::除外タグ

指定された XML タグ ペアを、指定されたバッファーから削除します。

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
[in]テキストのバッファー。

*タグ*<br/>
[in]開始タグと終了 XML タグのペアの名前。

*ストタグ*<br/>
[アウト]このメソッドが返されるときに*strTag*パラメーターには *、lpszTag*パラメーターで指定された開始 XML タグと終了 XML タグの間にあるテキストが含まれます。 先頭または末尾の空白は結果から削除されます。

*ビシャリスト*<br/>
[in]*strTag*パラメーター内のエスケープ文字のシンボルを実際のエスケープ文字に変換する場合は TRUE。変換を実行しない場合は FALSE。デフォルト値は FALSE です。 詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

XML タグのペアは、指定されたバッファー内のテキストの実行の開始と終了を示す名前付き開始タグと終了タグで構成されます。 *strBuffer*パラメーターはバッファーを指定し *、lpszTag*パラメーターは XML タグの名前を指定します。

指定したバッファー内のエスケープ文字のセットをエンコードするには、次の表の記号を使用します。 *strTag*パラメーターのシンボルを実際のエスケープ文字に変換するには *、bIsCharsList*パラメーターに TRUE を指定します。 次の表では[、_T()](../../c-runtime-library/data-type-mappings.md)マクロを使用して、記号とエスケープ文字ストリングを指定します。

|Symbol|エスケープ文字|
|------------|----------------------|
|_T("\t")\\|_T(「\t」)|
|_T("\n")\\|_T("\n")|
|_T("\r")\\|_T("\r")|
|_T("\b")\\|_T("\b")|
|_T(「LT」)|_T("\<")|
|_T(「GT」)|_T(「>」)|
|_T(「AMP」)|_T(「&」)|

## <a name="afx_global_datagetcolor"></a><a name="getcolor"></a>AFX_GLOBAL_DATA::ゲットカラー

指定されたユーザー インターフェイス要素の現在の色を取得します。

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>パラメーター

*nカラー*<br/>
[in]色を取得するユーザー インターフェイス要素を指定する値。 有効な値の一覧については、[メソッド](/windows/win32/api/winuser/nf-winuser-getsyscolor)の*nIndex*パラメーターを参照してください。

### <a name="return-value"></a>戻り値

指定したユーザー インターフェイス要素の RGB カラー値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

*nColor*パラメーターが範囲外の場合、戻り値は 0 です。 ゼロも有効な RGB 値であるため、このメソッドを使用して、現在のオペレーティング システムでシステムカラーがサポートされているかどうかを判断することはできません。 代わりに、色がサポートされていない場合は NULL を返す[GetSysColorBrush](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush)メソッドを使用します。

## <a name="afx_global_datagetdirect2dfactory"></a><a name="getdirect2dfactory"></a>AFX_GLOBAL_DATA::ゲットダイレクト2dファクトリー

グローバル データに格納されている ID2D1Factory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>戻り値

ファクトリの作成が成功した場合は ID2D1Factory インターフェイスへのポインタ、または作成に失敗した場合、または現在のオペレーション システムが D2D をサポートしていない場合は NULL。

## <a name="afx_global_datagethandcursor"></a><a name="gethandcursor"></a>AFX_GLOBAL_DATA::ゲットハンドカーソル

手に似ていて、識別子がIDC_HANDされている定義済みカーソルを取得します。

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>戻り値

ハンド カーソルのハンドル。

## <a name="afx_global_datagetnonclientmetrics"></a><a name="getnonclientmetrics"></a>AFX_GLOBAL_DATA::クライアントメトリック

最小化されていないウィンドウの非クライアント領域に関連付けられたメトリックを取得します。

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>パラメーター

*情報*<br/>
[イン、アウト]最小化されていないウィンドウの非クライアント領域に関連付けられたスケーラブルなメトリックを含む[NONCLIENTMETRICS](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw)構造体。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="afx_global_datagettextheight"></a><a name="gettextheight"></a>AFX_GLOBAL_DATA::テキストの高さを取得します。

現在のフォントのテキスト文字の高さを取得します。

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>パラメーター

*bHorz*<br/>
[in]テキストが水平方向に実行される場合に文字の高さを取得する場合は TRUE。テキストが垂直方向に実行される場合に文字の高さを取得する場合は FALSE。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

現在のフォントの高さ(アセンダーからディセンダーまで)

## <a name="afx_global_datagetwicfactory"></a><a name="getwicfactory"></a>AFX_GLOBAL_DATA::ゲットウィックファクトリー

グローバル データに格納されている IWICImagingFactory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>戻り値

ファクトリの作成が成功した場合は IWICImagingFactory インターフェイスへのポインタ、または作成に失敗した場合、または現在のオペレーション システムに WIC サポートがない場合は NULL を返します。

## <a name="afx_global_datagetwritefactory"></a><a name="getwritefactory"></a>AFX_GLOBAL_DATA::書き込み工場

グローバル データに格納されている IDWriteFactory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>戻り値

ファクトリの作成が成功した場合は IDWriteFactory インターフェイスへのポインター、または作成に失敗した場合、または現在のオペレーション システムが DirectWrite をサポートしていない場合は NULL。

## <a name="afx_global_datainitd2d"></a><a name="initd2d"></a>AFX_GLOBAL_DATA::InitD2D

D2D、ダイレクトライト、および WIC ファクトリを初期化します。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>パラメーター

*d2dファクトリータイプ*<br/>
D2D ファクトリのスレッド モデルと、それが作成するリソース。

*書き込みファクトリタイプ*<br/>
書き込みファクトリ オブジェクトを共有するか分離するかを指定する値。

### <a name="return-value"></a>戻り値

ファクトリがインティラリスドである場合は TRUE を返します。

## <a name="afx_global_datais32biticons"></a><a name="is32biticons"></a>AFX_GLOBAL_DATA::Is32ビットアイコン

定義済みの 32 ビット アイコンがサポートされているかどうかを示します。

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>戻り値

定義済みの 32 ビット アイコンがサポートされている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

フレームワークが 32 ビットの組み込みアイコンをサポートしている場合、およびオペレーティング システムが 16 ビット/ピクセル以上をサポートしている場合、およびイメージがハイ コントラストで表示されない場合、このメソッドは TRUE を返します。

## <a name="afx_global_dataisaccessibilitysupport"></a><a name="isaccessibilitysupport"></a>AFX_GLOBAL_DATA::IsAccessibilityサポート

Microsoft Active Accessibility のサポートが有効かどうかを示します。

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>戻り値

ユーザー補助サポートが有効になっている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

Microsoft アクティブ アクセシビリティは、アプリケーションをアクセシビリティ対応にするための以前のソリューションでした。 Microsoft UI オートメーションは、Microsoft Windows の新しいアクセシビリティ モデルであり、支援技術製品と自動テスト ツールのニーズに対応することを目的としています。

アクティブ アクセシビリティ サポートを有効または無効にするには[、AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)メソッドを使用します。

## <a name="afx_global_dataisd2dinitialized"></a><a name="isd2dinitialized"></a>AFX_GLOBAL_DATA::IsD2D初期化

D2D が初期化されたかどうかを判断します。

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>戻り値

D2D が初期化された場合は TRUE。それ以外の場合は FALSE。

## <a name="afx_global_dataisdwmcompositionenabled"></a><a name="isdwmcompositionenabled"></a>AFX_GLOBAL_DATA::IsDwm コンポジションが有効

Windows の [DwmIsCompositionEnabled](/windows/win32/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) のメソッドを簡単な方法で呼び出すことができます。

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>戻り値

デスクトップ[ウィンドウ マネージャー](/windows/win32/dwm/dwm-overview) (DWM) の構成が有効になっている場合は TRUE。それ以外の場合は FALSE。

## <a name="afx_global_dataishighcontrastmode"></a><a name="ishighcontrastmode"></a>AFX_GLOBAL_DATA::ハイコントラストモード

イメージが現在、ハイ コントラストで表示されているかどうかを判定します。

```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>戻り値

イメージが現在黒または白のハイ コントラスト モードで表示されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

黒のハイコントラスト モードでは、ライトに面したエッジは白で、背景は黒です。 白いハイコントラスト モードでは、ライトに面したエッジは黒で、背景は白です。

## <a name="afx_global_dataiswindowslayersupportavailable"></a><a name="iswindowslayersupportavailable"></a>AFX_GLOBAL_DATA::IsWindows レイヤーサポート利用可能

オペレーティング システムがレイヤード ウィンドウをサポートするかどうかを示します。

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>戻り値

階層化されたウィンドウがサポートされている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

レイヤード ウィンドウがサポートされている場合、*スマート ドッキング*マーカーはレイヤード ウィンドウを使用します。

## <a name="afx_global_datam_busebuiltin32biticons"></a><a name="m_busebuiltin32biticons"></a>AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons

事前定義された 32 ビット カラー アイコンと低解像度のアイコンのどちらをフレームワークで使用するかを指定します。

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>解説

TRUE は、フレームワークが 32 ビットの色のアイコンを使用することを指定します。FALSE は、低解像度のアイコンを指定します。 コンストラクター`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`は、このメンバーを TRUE に初期化します。

このメンバーは、アプリケーションの起動時に設定する必要があります。

## <a name="afx_global_datam_busesystemfont"></a><a name="m_busesystemfont"></a>AFX_GLOBAL_DATA::m_bUseSystemFont

メニュー、ツール バー、およびリボンに対してシステム フォントが使用されるかどうかを示します。

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>解説

TRUE は、システム フォントを使用することを指定します。それ以外の場合は FALSE。 コンストラクター`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`は、このメンバーを FALSE に初期化します。

このメンバーをテストすることは、フレームワークが使用するフォントを決定する唯一の方法ではありません。 この`AFX_GLOBAL_DATA::UpdateFonts`メソッドは、既定のフォントと代替フォントをテストして、メニュー、ツールバー、およびリボンに適用できる表示スタイルを決定します。

## <a name="afx_global_datam_hcurhand"></a><a name="m_hcurhand"></a>AFX_GLOBAL_DATA::m_hcurHand

手の形のカーソルのハンドルを格納します。

```
HCURSOR m_hcurHand;
```

## <a name="afx_global_datam_hcurstretch"></a><a name="m_hcurstretch"></a>AFX_GLOBAL_DATA::m_hcurStretch

水平方向の伸縮カーソルのハンドルを格納します。

```
HCURSOR m_hcurStretch;
```

## <a name="afx_global_datam_hcurstretchvert"></a><a name="m_hcurstretchvert"></a>AFX_GLOBAL_DATA::m_hcurStretchVert

垂直方向の伸縮カーソルのハンドルを格納します。

```
HCURSOR m_hcurStretchVert;
```

## <a name="afx_global_datam_hicontool"></a><a name="m_hicontool"></a>AFX_GLOBAL_DATA::m_hiconTool

ツール アイコンのハンドルを格納します。

```
HICON m_hiconTool;
```

## <a name="afx_global_datam_nautohidetoolbarmargin"></a><a name="m_nautohidetoolbarmargin"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin

左端の自動非表示ツール バーからドッキング バーの左端までのオフセットを指定します。

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>解説

コンストラクター`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`は、このメンバーを 4 ピクセルに初期化します。

## <a name="afx_global_datam_nautohidetoolbarspacing"></a><a name="m_nautohidetoolbarspacing"></a>AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing

自動的に隠すツール バーの間の間隔を指定します。

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>解説

コンストラクター`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`は、このメンバーを 14 ピクセルに初期化します。

## <a name="afx_global_datam_ndragframethicknessdock"></a><a name="m_ndragframethicknessdock"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

ドッキング状態を示すために使用するドラッグ フレームの太さを指定します。

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>解説

コンストラクター`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`は、このメンバーを 3 ピクセルに初期化します。

## <a name="afx_global_datam_ndragframethicknessfloat"></a><a name="m_ndragframethicknessfloat"></a>AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat

フローティング状態を示すために使用するドラッグ フレームの太さを指定します。

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>解説

コンストラクター`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`は、このメンバーを 4 ピクセルに初期化します。

## <a name="afx_global_dataonsettingchange"></a><a name="onsettingchange"></a>AFX_GLOBAL_DATA:オンセッティングチェンジ

デスクトップのメニュー アニメーションとタスクバーの自動非表示機能の現在の状態を検出します。

```cpp
void OnSettingChange();
```

### <a name="remarks"></a>解説

このメソッドは、ユーザーのデスクトップの特定の属性の状態にフレームワーク変数を設定します。 このメソッドは、メニュー アニメーション、メニューフェード、タスクバーの自動非表示機能の現在の状態を検出します。

## <a name="afx_global_dataregisterwindowclass"></a><a name="registerwindowclass"></a>AFX_GLOBAL_DATA:クラスを登録します。

指定された MFC ウィンドウ クラスを登録します。

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>パラメーター

*プレフィックスを指定します。*<br/>
[in]登録するウィンドウ クラスの名前。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、登録されたクラスの修飾名。それ以外の場合は、[リソース例外](exception-processing.md#afxthrowresourceexception)。

### <a name="remarks"></a>解説

戻り値は、コロンで区切られた*lpszClassNamePrefix*パラメーター文字列のリスト、および現在のアプリケーション インスタンスのハンドルの 16 進テキスト表現です。識別子がIDC_ARROWされる矢印カーソルであるアプリケーション カーソル。と背景ブラシ。 MFC ウィンドウ クラスの登録の詳細については、「 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)」を参照してください。

## <a name="afx_global_dataresume"></a><a name="resume"></a>AFX_GLOBAL_DATA::再開

Windows のテーマと視覚スタイルをサポートするメソッドにアクセスする内部関数ポインターを再初期化します。

```
BOOL Resume();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。 デバッグ モードでは、このメソッドが失敗した場合に、このメソッドがアサートします。

### <a name="remarks"></a>解説

このメソッドは、フレームワークが[WM_POWERBROADCAST](/windows/win32/Power/wm-powerbroadcast)メッセージを受信したときに呼び出されます。

## <a name="afx_global_datasetlayeredattrib"></a><a name="setlayeredattrib"></a>AFX_GLOBAL_DATA::セットレイヤードアトリブ

Windows の [SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes) メソッドを簡単な方法で呼び出すことができます。

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*Hwnd*<br/>
[in]レイヤード ウィンドウへのハンドル。

*crKey*<br/>
[in][デスクトップ ウィンドウ マネージャー](/windows/win32/dwm/dwm-overview)がレイヤード ウィンドウを構成するために使用する透明カラー キー。

*bアルファ*<br/>
[in]レイヤード ウィンドウの不透明度を表すために使用されるアルファ値。

*dwFlags*<br/>
[in]使用するメソッド パラメータを指定するフラグのビットごとの組み合わせ (OR)。 透明度の色として*crKey*パラメーターを使用するLWA_COLORKEYを指定します。 LWA_ALPHAを指定して *、bAlpha*パラメーターを使用してレイヤード ウィンドウの不透明度を決定します。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。

## <a name="afx_global_datasetmenufont"></a><a name="setmenufont"></a>AFX_GLOBAL_DATA::セットメニューフォント

指定された論理フォントを作成します。

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*フォント*<br/>
[in]フォントの属性を含む構造体へのポインター。

*bHorz*<br/>
[in]テキストを水平方向に実行するように指定する場合は TRUE。テキストを縦方向に実行するように指定する場合は FALSE。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合は FALSE。 デバッグ モードでは、このメソッドが失敗した場合に、このメソッドがアサートします。

### <a name="remarks"></a>解説

このメソッドは、既定のメニュー項目で使用される水平標準フォント、下線付きフォント、および太字フォントを作成します。 このメソッドは、オプションで標準の垂直フォントを作成します。 論理フォントの詳細については[、「CFont::CreateFontIndirect」](../../mfc/reference/cfont-class.md#createfontindirect)を参照してください。

## <a name="afx_global_dataupdatefonts"></a><a name="updatefonts"></a>AFX_GLOBAL_DATA::更新フォント

フレームワークにより使用される論理フォントを再初期化します。

```cpp
void UpdateFonts();
```

### <a name="remarks"></a>解説

論理フォントの詳細については、を参照`CFont::CreateFontIndirect`してください。

## <a name="afx_global_dataupdatesyscolors"></a><a name="updatesyscolors"></a>AFX_GLOBAL_DATA::更新Sysの色

フレームワークで使用される色、色深度、ブラシ、ペン、およびイメージを初期化します。

```cpp
void UpdateSysColors();
```

## <a name="afx_global_databiswindows7"></a><a name="biswindows7"></a>AFX_GLOBAL_DATA::bIsWindows7

アプリケーションが Windows 7 以降で実行されているかどうかを示します。

```
BOOL bIsWindows7;
```

## <a name="afx_global_dataclractivecaptiongradient"></a><a name="clractivecaptiongradient"></a>AFX_GLOBAL_DATA::クラスエントキャプショングラデーション

アクティブなキャプションのグラデーション色を指定します。 通常、ドッキング ペインで使用されます。

```
COLORREF clrActiveCaptionGradient;
```

## <a name="afx_global_dataclrinactivecaptiongradient"></a><a name="clrinactivecaptiongradient"></a>AFX_GLOBAL_DATA::clrInactiveキャプショングラデーション

非アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="afx_global_datagetitaskbarlist"></a><a name="getitaskbarlist"></a>AFX_GLOBAL_DATA::GetIタスクバーリスト

インターフェイスへのポインターをグローバル データに作成して格納`ITaskBarList`します。

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>戻り値

タスク バー`ITaskbarList`リスト オブジェクトの作成が成功した場合はインターフェイスへのポインター。作成に失敗した場合、または現在のオペレーション システムが Windows 7 より小さい場合は NULL。

## <a name="afx_global_datagetitaskbarlist3"></a><a name="getitaskbarlist3"></a>AFX_GLOBAL_DATA::GetIタスクバーリスト3

インターフェイスへのポインターをグローバル データに作成して格納`ITaskBarList3`します。

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>戻り値

タスク バー`ITaskbarList3`リスト オブジェクトの作成が成功した場合はインターフェイスへのポインター。作成に失敗した場合、または現在のオペレーション システムが Windows 7 より小さい場合は NULL。

## <a name="afx_global_datagetshellautohidebars"></a><a name="getshellautohidebars"></a>AFX_GLOBAL_DATA::ゲットシェルオートハイダバー

シェルの自動非表示バーの位置を決定します。

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>戻り値

自動非表示バーの位置を指定するエンコードされたフラグを持つ整数値。 AFX_AUTOHIDE_BOTTOM、AFX_AUTOHIDE_TOP、AFX_AUTOHIDE_LEFT、AFX_AUTOHIDE_RIGHTの値を組み合わせてもよい。

## <a name="afx_global_datareleasetaskbarrefs"></a><a name="releasetaskbarrefs"></a>AFX_GLOBAL_DATA::タスクバール参照のリリース

メソッドを介して取得`GetITaskbarList`した`GetITaskbarList3`インターフェイスを解放します。

```cpp
void ReleaseTaskBarRefs();
```

## <a name="afx_global_datashellcreateitemfromparsingname"></a><a name="shellcreateitemfromparsingname"></a>AFX_GLOBAL_DATA::名前を作成します。

解析名からシェル項目オブジェクトを作成して初期化します。

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>パラメーター

*パス*<br/>
[in]表示名へのポインター。

*Pbc*<br/>
解析操作を制御するバインド コンテキストへのポインター。

*riid*<br/>
インターフェイス ID への参照。

*Ppv*<br/>
[アウト]この関数が返されるときに、 *riid*で要求されたインターフェイス ポインターを格納します。 これは通常、`IShellItem`または`IShellItem2`になります。

### <a name="return-value"></a>戻り値

成功した場合はS_OKを返します。それ以外の場合はエラー値です。

## <a name="see-also"></a>関連項目

[階層グラフ](../hierarchy-chart.md)<br/>
[構造体、スタイル、コールバック関数とメッセージ マップ](structures-styles-callbacks-and-message-maps.md)<br/>
[COLORREF](/windows/win32/gdi/colorref)<br/>
[Parts and States (パーツと状態)](/windows/win32/controls/parts-and-states)<br/>
[nFormat](cdc-class.md#drawtext)<br/>
[メソッドの](/windows/win32/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[デスクトップ ウィンドウ マネージャー](/windows/win32/dwm/dwm-overview)<br/>
[Enable and Control DWM Composition (DWM の構成の有効化と制御)](/windows/win32/dwm/composition-ovw)<br/>
[UI オートメーションと Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[関数を取得します。](/windows/win32/api/winuser/nf-winuser-getsyscolor)<br/>
[ブラシ](/windows/win32/api/winuser/nf-winuser-getsyscolorbrush)<br/>
[非クライアントメトリックス構造](/windows/win32/api/winuser/ns-winuser-nonclientmetricsw)<br/>
[AfxRegisterClass](application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)<br/>
[SetLayeredWindowAttributes](/windows/win32/api/winuser/nf-winuser-setlayeredwindowattributes)
