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
- AFXGLOBALS/AFX_GLOBAL_DATA::IsD2DInitialized
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
ms.openlocfilehash: 0fd8143564beecccd8943f3ceba531e8697151d1
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850325"
---
# <a name="afxglobaldata-structure"></a>AFX_GLOBAL_DATA 構造体

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
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D`、 `DirectWrite`、および `WIC` の各ファクトリを初期化します。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。|
|[AFX_GLOBAL_DATA::Is32BitIcons](#is32biticons)|定義済みの 32 ビット アイコンがサポートされているかどうかを示します。|
|[AFX_GLOBAL_DATA::IsD2DInitialized](#isd2dinitialized)|`D2D` が初期化されているかどうかを調べます。|
|[AFX_GLOBAL_DATA::IsDwmCompositionEnabled](#isdwmcompositionenabled)|Windows の [DwmIsCompositionEnabled](/windows/desktop/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) のメソッドを簡単な方法で呼び出すことができます。|
|[AFX_GLOBAL_DATA::IsHighContrastMode](#ishighcontrastmode)|イメージが現在、ハイ コントラストで表示されているかどうかを判定します。|
|[AFX_GLOBAL_DATA::OnSettingChange](#onsettingchange)|デスクトップのメニュー アニメーションとタスクバーの自動非表示機能の現在の状態を検出します。|
|[AFX_GLOBAL_DATA::RegisterWindowClass](#registerwindowclass)|指定された MFC ウィンドウ クラスを登録します。|
|[AFX_GLOBAL_DATA::ReleaseTaskBarRefs](#releasetaskbarrefs)|GetITaskbarList メソッドおよび GetITaskbarList3 メソッドを通じて取得されたインターフェイスを解放します。|
|[AFX_GLOBAL_DATA::Resume](#resume)|Windows の [テーマと視覚スタイル](/windows/desktop/Controls/visual-styles-overview)をサポートするメソッドにアクセスする内部関数ポインターを再初期化します。|
|[AFX_GLOBAL_DATA::SetLayeredAttrib](#setlayeredattrib)|Windows の [SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes) メソッドを簡単な方法で呼び出すことができます。|
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

### <a name="remarks"></a>Remarks

`AFX_GLOBAL_DATA` 構造体内のデータのほとんどは、アプリケーションの起動時に初期化されます。

### <a name="inheritance-hierarchy"></a>継承階層

`AFX_GLOBAL_DATA`

### <a name="requirements"></a>必要条件

**ヘッダー :** afxglobals.h

## <a name="bisosalphablendingsupport"></a> AFX_GLOBAL_DATA::bIsOSAlphaBlendingSupport

オペレーティング システムがアルファ ブレンドをサポートしているかどうかを示します。

```
BOOL  bIsOSAlphaBlendingSupport;
```

### <a name="remarks"></a>Remarks

TRUE は、アルファ ブレンドがサポートされていることを示しますそれ以外の場合、FALSE です。

## <a name="cleanup"></a> AFX_GLOBAL_DATA::CleanUp

ブラシ、フォント、DLL など、フレームワークにより割り当てられたリソースを解放します。

```
void CleanUp();
```

## <a name="d2d1makerotatematrix"></a> AFX_GLOBAL_DATA::D2D1MakeRotateMatrix

指定した点を中心に指定した角度ずつ回転する回転変換を作成します。

```
HRESULT D2D1MakeRotateMatrix(
    FLOAT angle,
    D2D1_POINT_2F center,
    D2D1_MATRIX_3X2_F *matrix);
```

### <a name="parameters"></a>パラメーター

*angle*<br/>
時計回りの回転角度 (度単位)。

*Center*<br/>
回転の中心点。

*matrix*<br/>
このメソッドが戻るときに、新しい回転変換が含まれています。 このパラメーターは、記憶域を割り当てる必要があります。

### <a name="return-value"></a>戻り値

それ以外の場合、正常終了した場合またはエラー値を返します。

## <a name="drawparentbackground"></a> AFX_GLOBAL_DATA::DrawParentBackground

指定領域にコントロールの親の背景を描画します。

```
BOOL DrawParentBackground(
    CWnd* pWnd,
    CDC* pDC,
    LPRECT lpRect = NULL);
```

### <a name="parameters"></a>パラメーター

*我が物*<br/>
[in]コントロールのウィンドウへのポインター。

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*lpRect*<br/>
[in]描画する領域に外接する四角形を指すポインター。 既定値は、NULL です。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

## <a name="drawtextonglass"></a> AFX_GLOBAL_DATA::DrawTextOnGlass

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
[in]ウィンドウのテーマ データへのハンドル、または NULL。 フレームワークは、このパラメーターが NULL でないテーマがサポートされている場合、テキストを描画するために、指定されたテーマを使用します。 それ以外の場合、フレームワークは、テーマを使用せずにテキストを描画します。

使用して、 [OpenThemeData](/windows/desktop/api/uxtheme/nf-uxtheme-openthemedata) HTHEME を作成します。

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*iPartId*<br/>
[in]目的のテキストの外観を備えたコントロールの部分。 詳細については、「 [Parts and States (パーツと状態)](/windows/desktop/controls/parts-and-states)」の表の「Parts (パーツ)」列を参照してください。 この値が 0 の場合、テキストは既定のフォント、またはデバイス コンテキストに選択されているフォントで描画されます。

*iStateId*<br/>
[in]目的のテキストの外観を備えたコントロールの状態。 詳細については、「 [Parts and States (パーツと状態)](/windows/desktop/controls/parts-and-states)」の表の「States (状態)」列を参照してください。

*strText*<br/>
[in]描画するテキスト。

*rect*<br/>
[in]指定したテキストが描画される領域の境界です。

*dwFlags*<br/>
[in]指定したテキストの描画方法を指定するフラグのビットごとの組み合わせ (OR)。

場合、 *hTheme*パラメーターが`NULL`テーマがサポートされており、有効になっていないか、*フォーマット*のパラメーター、 [CDC::DrawText](../../mfc/reference/cdc-class.md#drawtext)メソッドが有効なについて説明しますフラグ。 テーマがサポートされている場合、 *dwFlags*のパラメーター、 [DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex)メソッドが有効なフラグについて説明します。

*nGlowSize*<br/>
[in]指定したテキストを描画する前に、背景に描画される光彩効果のサイズ。 既定値は 0 です。

*clrText*<br/>
[in]指定したテキストを描画する色です。 既定値は既定の色です。

### <a name="return-value"></a>戻り値

テーマは、指定したテキストを描画するために使用する場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

テーマは、アプリケーションの視覚スタイルを定義します。 場合、テキストの描画にテーマが使用できません、 *hTheme*パラメーターが null の場合、または、 [DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex)メソッドがサポートされていません場合[デスクトップ ウィンドウ マネージャー](/windows/desktop/dwm/dwm-overview) (DWM) の構成無効です。

## <a name="enableaccessibilitysupport"></a> AFX_GLOBAL_DATA::EnableAccessibilitySupport

Microsoft Active Accessibility のサポートを有効または無効にします。

```
void EnableAccessibilitySupport(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]ユーザー補助のサポートを有効にする場合は TRUEユーザー補助のサポートを無効にする場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>Remarks

Active Accessibility は、プログラムと支援技術製品と共に、Windows オペレーティング システムの作業を改善する COM ベース テクノロジです。 ユーザー インターフェイス要素に関する情報を公開するための信頼性の高いメソッドを提供します。 ただし、Microsoft UI オートメーションと呼ばれる新しいユーザー補助モデルでは、使用できるようになりました。 2 つのテクノロジの比較は、次を参照してください。 [UI オートメーションと Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)します。

使用して、 [AFX_GLOBAL_DATA::IsAccessibilitySupport](#isaccessibilitysupport) Microsoft Active Accessibility のサポートが有効になっているかどうかを判断するメソッド。

## <a name="excludetag"></a> AFX_GLOBAL_DATA::ExcludeTag

指定された XML タグ ペアを、指定されたバッファーから削除します。

```
BOOL ExcludeTag(
    CString& strBuffer,
    LPCTSTR lpszTag,
    CString& strTag,
    BOOL bIsCharsList = FALSE);
```

### <a name="parameters"></a>パラメーター

*strBuffer*<br/>
[in]テキストのバッファー。

*lpszTag*<br/>
[in]タグと終了 XML タグのペアの名前。

*strTag*<br/>
[out]このメソッドが戻るとき、 *strTag*パラメーターには間にある開始タグと終了 XML タグで指定されたテキストが含まれています、 *lpszTag*パラメーター。 先頭または末尾の空白は結果からトリミングされます。

*bIsCharsList*<br/>
[in]エスケープ文字のシンボルを変換する場合は True、 *strTag*パラメーターに実際のエスケープ文字。変換を実行するには、ない場合は FALSE。既定値は FALSE です。 詳細については、「解説」を参照してください。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

XML タグのペアは開始と指定したバッファー内のテキストの実行の終了を示すタグの開閉をという名前で構成されます。 *StrBuffer*パラメーターが、バッファーを指定します、 *lpszTag*パラメーターは XML タグの名前を指定します。

次の表に、シンボルを使用して、指定したバッファー内のエスケープ文字のセットをエンコードします。 TRUE に指定、 *bIsCharsList*内のシンボルを変換するパラメーター、 *strTag*パラメーターに実際のエスケープ文字。 次の表には、 [_T()](../../c-runtime-library/data-type-mappings.md)マクロを記号を指定し、文字の文字列をエスケープします。

|シンボル|エスケープ文字|
|------------|----------------------|
|_T("\\\t")|_T("\t")|
|_T("\\\n")|_T("\n")|
|_T("\\\r")|_T("\r")|
|_T("\\\b")|_T("\b")|
|_T("LT")|_T("\<")|
|_T("GT")|_T(">")|
|_T("AMP")|_T("&")|

## <a name="getcolor"></a> AFX_GLOBAL_DATA::GetColor

指定されたユーザー インターフェイス要素の現在の色を取得します。

```
COLORREF GetColor(int nColor);
```

### <a name="parameters"></a>パラメーター

*nColor*<br/>
[in]色を取得、ユーザー インターフェイス要素を指定する値。 有効な値の一覧は、次を参照してください。、 *nIndex*のパラメーター、 [GetSysColor](/windows/desktop/api/winuser/nf-winuser-getsyscolor)メソッド。

### <a name="return-value"></a>戻り値

指定されたユーザー インターフェイス要素の RGB カラー値。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

場合、 *nColor*パラメーターが範囲外には、戻り値は 0。 0 は有効な RGB 値でもあるので、システム カラーが現在のオペレーティング システムでサポートされているかどうかを判断するのにこのメソッドを使用できません。 代わりに、使用、 [GetSysColorBrush](/windows/desktop/api/winuser/nf-winuser-getsyscolorbrush)メソッドで、色がサポートされていない場合は NULL を返します。

## <a name="getdirect2dfactory"></a> AFX_GLOBAL_DATA::GetDirect2dFactory

グローバル データに格納されている ID2D1Factory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。

```
ID2D1Factory* GetDirect2dFactory();
```

### <a name="return-value"></a>戻り値

ID2D1Factory インターフェイスの場合は、ファクトリの作成が成功すると、または作成が失敗する場合は NULL または現在のオペレーティング システムへのポインターは、D2D のサポートを必要はありません。

## <a name="gethandcursor"></a>  AFX_GLOBAL_DATA::GetHandCursor

手の形に類似して、識別子を持つ IDC_HAND は、定義済みのカーソルを取得します。

```
HCURSOR GetHandCursor();
```

### <a name="return-value"></a>戻り値

手形カーソルのハンドル。

## <a name="getnonclientmetrics"></a> AFX_GLOBAL_DATA::GetNonClientMetrics

最小化されていないウィンドウの非クライアント領域に関連付けられたメトリックを取得します。

```
BOOL GetNonClientMetrics(NONCLIENTMETRICS& info);
```

### <a name="parameters"></a>パラメーター

*情報*<br/>
[入力、出力]A [NONCLIENTMETRICS](/windows/desktop/api/winuser/ns-winuser-tagnonclientmetricsa)最小化されていないウィンドウの非クライアント領域に関連付けられているスケーラブルなメトリックを含む構造体。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

## <a name="gettextheight"></a> AFX_GLOBAL_DATA::GetTextHeight

現在のフォントのテキスト文字の高さを取得します。

```
int GetTextHeight(BOOL bHorz = TRUE);
```

### <a name="parameters"></a>パラメーター

*bHorz*<br/>
[in]テキストの水平方向に実行時に、文字の高さを取得する場合は TRUEテキストの垂直方向に実行時に、文字の高さを取得する場合は FALSE。 既定値は TRUE です。

### <a name="return-value"></a>戻り値

そのベースラインから測定されますが、現在のフォントの高さ。

## <a name="getwicfactory"></a> AFX_GLOBAL_DATA::GetWICFactory

グローバル データに格納されている IWICImagingFactory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。

```
IWICImagingFactory* GetWICFactory();
```

### <a name="return-value"></a>戻り値

IWICImagingFactory インターフェイスの場合は、ファクトリの作成が成功すると、または作成が失敗する場合は NULL または現在のオペレーティング システムへのポインターは、WIC のサポートを必要はありません。

## <a name="getwritefactory"></a> AFX_GLOBAL_DATA::GetWriteFactory

グローバル データに格納されている IDWriteFactory インターフェイスへのポインターを返します。 インターフェイスが初期化されていない場合は、既定のパラメーターでインターフェイスが作成されます。

```
IDWriteFactory* GetWriteFactory();
```

### <a name="return-value"></a>戻り値

IDWriteFactory インターフェイスの場合は、ファクトリの作成が成功すると、または作成が失敗する場合は NULL または現在のオペレーティング システムへのポインターは、DirectWrite のサポートを必要はありません。

## <a name="initd2d"></a> AFX_GLOBAL_DATA::InitD2D

D2D、DirectWrite と WIC のファクトリを初期化します。 このメソッドは、メイン ウィンドウが初期化される前に呼び出します。

```
BOOL InitD2D(
    D2D1_FACTORY_TYPE d2dFactoryType = D2D1_FACTORY_TYPE_SINGLE_THREADED,
    DWRITE_FACTORY_TYPE writeFactoryType = DWRITE_FACTORY_TYPE_SHARED);
```

### <a name="parameters"></a>パラメーター

*d2dFactoryType*<br/>
D2D ファクトリとリソースのスレッド処理モデルを作成します。

*writeFactoryType*<br/>
書き込みのファクトリ オブジェクトが共有か分離かどうかを指定する値

### <a name="return-value"></a>戻り値

かどうか、ファクトリが intilalizrd、FALSE、それ以外の場合に TRUE を返します

## <a name="is32biticons"></a> AFX_GLOBAL_DATA::Is32BitIcons

定義済みの 32 ビット アイコンがサポートされているかどうかを示します。

```
BOOL Is32BitIcons() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、定義済みの 32 ビット アイコンがサポートされています。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

このメソッドは、フレームワークは、32 ビットの組み込みアイコンをサポートしている場合、オペレーティング システムは、16 ビット/ピクセル以上をサポートしている場合とイメージはハイ コントラスト表示されていない場合に TRUE を返します。

## <a name="isaccessibilitysupport"></a> AFX_GLOBAL_DATA::IsAccessibilitySupport

Microsoft Active Accessibility のサポートが有効かどうかを示します。

```
BOOL IsAccessibilitySupport() const;
```

### <a name="return-value"></a>戻り値

ユーザー補助のサポートが有効な場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

Microsoft Active Accessibility は、以前のソリューションのアプリケーションにアクセスできるようにしました。 Microsoft UI オートメーションは Microsoft Windows 用の新しいユーザー補助モデルは、支援技術製品のニーズに対応するためのものし、自動テスト ツール。

使用して、 [AFX_GLOBAL_DATA::EnableAccessibilitySupport](#enableaccessibilitysupport)メソッドを有効または Active Accessibility のサポートを無効にします。

## <a name="isd2dinitialized"></a> AFX_GLOBAL_DATA::IsD2DInitialized

D2D が初期化されたかどうかを決定します。

```
BOOL IsD2DInitialized() const;
```

### <a name="return-value"></a>戻り値

D2D の初期化された場合は TRUE。それ以外の場合は FALSE です。

## <a name="isdwmcompositionenabled"></a> AFX_GLOBAL_DATA::IsDwmCompositionEnabled

Windows の [DwmIsCompositionEnabled](/windows/desktop/api/dwmapi/nf-dwmapi-dwmiscompositionenabled) のメソッドを簡単な方法で呼び出すことができます。

```
BOOL IsDwmCompositionEnabled();
```

### <a name="return-value"></a>戻り値

TRUE の場合[デスクトップ ウィンドウ マネージャー](/windows/desktop/dwm/dwm-overview) (DWM) コンポジションを有効になっている、それ以外は FALSE。

## <a name="ishighcontrastmode"></a> AFX_GLOBAL_DATA::IsHighContrastMode

イメージが現在、ハイ コントラストで表示されているかどうかを判定します。
```
BOOL IsHighContrastMode() const;
```

### <a name="return-value"></a>戻り値

イメージは、黒または白のハイ コントラスト モードで現在表示されている場合は TRUE。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

黒のハイ コントラスト モードでは、周縁が光源が白、背景が黒に。 白のハイ コントラスト モードでは、周縁が光源が黒、バック グラウンドが白にです。

## <a name="iswindowslayersupportavailable"></a> :Iswindowslayersupportavailable

オペレーティング システムがレイヤード ウィンドウをサポートするかどうかを示します。

```
BOOL IsWindowsLayerSupportAvailable() const;
```

### <a name="return-value"></a>戻り値

TRUE の場合、レイヤード ウィンドウがサポートされています。それ以外の場合、FALSE です。

### <a name="remarks"></a>Remarks

レイヤード ウィンドウはサポートされている場合*スマート ドッキング*マーカーがレイヤード ウィンドウを使用します。

## <a name="m_busebuiltin32biticons"></a> AFX_GLOBAL_DATA::m_bUseBuiltIn32BitIcons

事前定義された 32 ビット カラー アイコンと低解像度のアイコンのどちらをフレームワークで使用するかを指定します。

```
BOOL  m_bUseBuiltIn32BitIcons;
```

### <a name="remarks"></a>Remarks

TRUE は、フレームワークが 32 ビット カラー アイコンを使用することを指定しますFALSE には、低解像度アイコンを指定します。 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`コンス トラクターを TRUE には、このメンバーを初期化します。

このメンバーは、アプリケーションの起動時に設定する必要があります。

## <a name="m_busesystemfont"></a> AFX_GLOBAL_DATA::m_bUseSystemFont

メニュー、ツール バー、およびリボンに対してシステム フォントが使用されるかどうかを示します。

```
BOOL m_bUseSystemFont;
```

### <a name="remarks"></a>Remarks

TRUE は、システム フォントを使用するを指定しますそれ以外の場合、FALSE です。 `AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`コンス トラクターを FALSE には、このメンバーを初期化します。

このメンバーをテストすることは、フォントを決定するためにフレームワークを使用する唯一の方法ではありません。 `AFX_GLOBAL_DATA::UpdateFonts`メソッドはどのような visual スタイルがメニューのツールバー、およびリボンに適用される使用可能な判断を既定と代替のフォントもテストします。

## <a name="m_hcurhand"></a> AFX_GLOBAL_DATA::m_hcurHand

手の形のカーソルのハンドルを格納します。

```
HCURSOR m_hcurHand;
```

## <a name="m_hcurstretch"></a> AFX_GLOBAL_DATA::m_hcurStretch

水平方向の伸縮カーソルのハンドルを格納します。

```
HCURSOR m_hcurStretch;
```

## <a name="m_hcurstretchvert"></a> AFX_GLOBAL_DATA::m_hcurStretchVert

垂直方向の伸縮カーソルのハンドルを格納します。

```
HCURSOR m_hcurStretchVert;
```

## <a name="m_hicontool"></a> AFX_GLOBAL_DATA::m_hiconTool

ツール アイコンのハンドルを格納します。

```
HICON m_hiconTool;
```

## <a name="m_nautohidetoolbarmargin"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarMargin

左端の自動的に隠すツールバーからドッキング バーの左側にあるのオフセットを指定します。

```
int  m_nAutoHideToolBarMargin;
```

### <a name="remarks"></a>Remarks

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`コンス トラクターは、4 ピクセルにこのメンバーを初期化します。

## <a name="m_nautohidetoolbarspacing"></a> AFX_GLOBAL_DATA::m_nAutoHideToolBarSpacing

自動的に隠すツール バーの間の間隔を指定します。

```
int   m_nAutoHideToolBarSpacing;
```

### <a name="remarks"></a>Remarks

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`コンス トラクターは、14 のピクセルには、このメンバーを初期化します。

## <a name="m_ndragframethicknessdock"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessDock

ドッキングされた状態を示すために使用するドラッグ フレームの太さを指定します。

```
int  m_nDragFrameThicknessDock;
```

### <a name="remarks"></a>Remarks

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`コンス トラクターが 3 ピクセルには、このメンバーを初期化します。

## <a name="m_ndragframethicknessfloat"></a> AFX_GLOBAL_DATA::m_nDragFrameThicknessFloat

浮動小数点状態を示すために使用するドラッグ フレームの太さを指定します。

```
int  m_nDragFrameThicknessFloat;
```

### <a name="remarks"></a>Remarks

`AFX_GLOBAL_DATA::AFX_GLOBAL_DATA`コンス トラクターは、4 ピクセルにこのメンバーを初期化します。

## <a name="onsettingchange"></a> AFX_GLOBAL_DATA::OnSettingChange

デスクトップのメニュー アニメーションとタスクバーの自動非表示機能の現在の状態を検出します。

```
void OnSettingChange();
```

### <a name="remarks"></a>Remarks

このメソッドは、framework の変数をユーザーのデスクトップの特定の属性の状態に設定します。 このメソッドは、メニューのアニメーション、メニューのフェードおよびタスク バーの自動非表示機能の現在の状態を検出します。

## <a name="registerwindowclass"></a> AFX_GLOBAL_DATA::RegisterWindowClass

指定された MFC ウィンドウ クラスを登録します。

```
CString RegisterWindowClass(LPCTSTR lpszClassNamePrefix);
```

### <a name="parameters"></a>パラメーター

*lpszClassNamePrefix*<br/>
[in]登録ウィンドウ クラスの名前。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、登録されているクラスの修飾名それ以外の場合、[リソース例外](exception-processing.md#afxthrowresourceexception)します。

### <a name="remarks"></a>Remarks

戻り値はコロン区切りの一覧、 *lpszClassNamePrefix*パラメーター文字列、および現在のアプリケーション インスタンスのハンドルの 16 進数のテキスト表現の矢印は、アプリケーションのカーソル識別子を持つ IDC_ARROW; は、カーソル背景のブラシ。 MFC ウィンドウ クラスの登録の詳細については、次を参照してください。 [AfxRegisterClass](../../mfc/reference/application-information-and-management.md#afxregisterclass)します。

## <a name="resume"></a> AFX_GLOBAL_DATA::Resume

Windows テーマと視覚スタイルをサポートするメソッドにアクセスする内部関数ポインターを再初期化します。

```
BOOL Resume();
```

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。 デバッグ モードでは、このメソッドは、このメソッドが成功したかどうかをアサートします。

### <a name="remarks"></a>Remarks

フレームワークが受信すると、このメソッドが呼び出されます、 [WM_POWERBROADCAST](/windows/desktop/Power/wm-powerbroadcast)メッセージ。

## <a name="setlayeredattrib"></a> AFX_GLOBAL_DATA::SetLayeredAttrib

Windows の [SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes) メソッドを簡単な方法で呼び出すことができます。

```
BOOL SetLayeredAttrib(
    HWND hwnd,
    COLORREF crKey,
    BYTE bAlpha,
    DWORD dwFlags);
```

### <a name="parameters"></a>パラメーター

*hwnd*<br/>
[in]レイヤード ウィンドウへのハンドルします。

*crKey*<br/>
[in]透過色キーを[デスクトップ ウィンドウ マネージャー](/windows/desktop/dwm/dwm-overview)レイヤード ウィンドウの作成に使用します。

*bAlpha*<br/>
[in]レイヤード ウィンドウの不透明度を記述するために使用するアルファ値。

*dwFlags*<br/>
[in]使用するメソッド パラメーターを指定するフラグのビットごとの組み合わせ (OR)。 使用する LWA_COLORKEY の指定、 *crKey*透過色としてパラメーター。 使用する LWA_ALPHA の指定、 *bAlpha*レイヤード ウィンドウの不透明度を決定するパラメーター。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。

## <a name="setmenufont"></a> AFX_GLOBAL_DATA::SetMenuFont

指定された論理フォントを作成します。

```
BOOL SetMenuFont(
    LPLOGFONT lpLogFont,
    BOOL bHorz);
```

### <a name="parameters"></a>パラメーター

*lpLogFont*<br/>
[in]フォントの属性を格納する構造体へのポインター。

*bHorz*<br/>
[in]テキストを水平方向に実行するように指定する場合は TRUEテキストが垂直方向に実行するように指定する場合は FALSE。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は TRUE。それ以外の場合、FALSE です。 デバッグ モードでは、このメソッドは、このメソッドが成功したかどうかをアサートします。

### <a name="remarks"></a>Remarks

このメソッドは、水平正規フォントを下線付きのフォントを作成し、既定のメニュー項目に使用されるフォントを太字します。 このメソッドは、必要に応じて通常縦書きフォントを作成します。 論理フォントの詳細については、次を参照してください。 [CFont::CreateFontIndirect](../../mfc/reference/cfont-class.md#createfontindirect)します。

## <a name="updatefonts"></a> AFX_GLOBAL_DATA::UpdateFonts

フレームワークにより使用される論理フォントを再初期化します。

```
void UpdateFonts();
```

### <a name="remarks"></a>Remarks

論理フォントの詳細については、次を参照してください。`CFont::CreateFontIndirect`します。

## <a name="updatesyscolors"></a> AFX_GLOBAL_DATA::UpdateSysColors

フレームワークで使用される色、色深度、ブラシ、ペン、およびイメージを初期化します。

```
void UpdateSysColors();
```

## <a name="biswindows7"></a> AFX_GLOBAL_DATA::bIsWindows7

Windows 7 またはそれ以降、アプリケーションが実行されているかどうかを示します。

```
BOOL bIsWindows7;
```

## <a name="clractivecaptiongradient"></a> AFX_GLOBAL_DATA::clrActiveCaptionGradient

アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。

```
COLORREF clrActiveCaptionGradient;
```

## <a name="clrinactivecaptiongradient"></a> AFX_GLOBAL_DATA::clrInactiveCaptionGradient

非アクティブなキャプションのグラデーションの色を指定します。 通常、ドッキング ペインで使用されます。

```
COLORREF clrInactiveCaptionGradient;
```

## <a name="getitaskbarlist"></a> AFX_GLOBAL_DATA::GetITaskbarList

作成し、グローバル データへのポインターを格納、`ITaskBarList`インターフェイス。

```
ITaskbarList *GetITaskbarList();
```

### <a name="return-value"></a>戻り値

ポインター、`ITaskbarList`インターフェイスをタスク バーのリスト オブジェクトの作成が成功した場合作成が失敗した場合、または現在のオペレーティング システムが Windows 7 より小さい場合は NULL です。

## <a name="getitaskbarlist3"></a> AFX_GLOBAL_DATA::GetITaskbarList3

作成し、グローバル データへのポインターを格納、`ITaskBarList3`インターフェイス。

```
ITaskbarList3 *GetITaskbarList3();
```

### <a name="return-value"></a>戻り値

ポインター、`ITaskbarList3`インターフェイスをタスク バーのリスト オブジェクトの作成が成功した場合作成が失敗した場合、または現在のオペレーティング システムが Windows 7 より小さい場合は NULL です。

## <a name="getshellautohidebars"></a> AFX_GLOBAL_DATA::GetShellAutohideBars

シェルの自動非表示バーの位置を決定します。

```
int GetShellAutohideBars();
```

### <a name="return-value"></a>戻り値

自動の位置を指定するフラグをエンコードされた整数値には、バーが非表示にします。 次の値に組み合わせることもできます。AFX_AUTOHIDE_BOTTOM、AFX_AUTOHIDE_TOP、AFX_AUTOHIDE_LEFT、AFX_AUTOHIDE_RIGHT します。

## <a name="releasetaskbarrefs"></a> AFX_GLOBAL_DATA::ReleaseTaskBarRefs

経由で取得したインターフェイスを解放、`GetITaskbarList`と`GetITaskbarList3`メソッド。

```
void ReleaseTaskBarRefs();
```

## <a name="shellcreateitemfromparsingname"></a> AFX_GLOBAL_DATA::ShellCreateItemFromParsingName

解析名からシェル項目オブジェクトを作成して初期化します。

```
HRESULT ShellCreateItemFromParsingName(
    PCWSTR pszPath,
    IBindCtx *pbc,
    REFIID riid,
    void **ppv);
```

### <a name="parameters"></a>パラメーター

*pszPath*<br/>
[in]表示名へのポインター。

*pbc*<br/>
解析操作を制御するバインド コンテキストへのポインター。

*riid*<br/>
インターフェイス ID への参照

*ppv*<br/>
[out]この関数が戻るときに要求されたインターフェイス ポインターが含まれています。 *riid*します。 通常これは`IShellItem`または`IShellItem2`します。

### <a name="return-value"></a>戻り値

成功した場合は S_OK を返します。それ以外の場合エラー値。

## <a name="see-also"></a>関連項目

[階層図](../hierarchy-chart.md)<br/>
[構造体、スタイル、コールバック関数とメッセージ マップ](structures-styles-callbacks-and-message-maps.md)<br/>
[COLORREF](/windows/desktop/gdi/colorref)<br/>
[パーツと状態](/windows/desktop/controls/parts-and-states)<br/>
[CDC::DrawText](cdc-class.md#drawtext)<br/>
[DrawThemeTextEx](/windows/desktop/api/uxtheme/nf-uxtheme-drawthemetextex)<br/>
[デスクトップ ウィンドウ マネージャー](/windows/desktop/dwm/dwm-overview)<br/>
[DWM 合成を有効化と制御](/windows/desktop/dwm/composition-ovw)<br/>
[UI オートメーションと Microsoft Active Accessibility](/dotnet/framework/ui-automation/ui-automation-and-microsoft-active-accessibility)<br/>
[GetSysColor 関数](/windows/desktop/api/winuser/nf-winuser-getsyscolor)<br/>
[GetSysColorBrush](/windows/desktop/api/winuser/nf-winuser-getsyscolorbrush)<br/>
[NONCLIENTMETRICS 構造体](/windows/desktop/api/winuser/ns-winuser-tagnonclientmetricsa)<br/>
[AfxRegisterClass](application-information-and-management.md#afxregisterclass)<br/>
[AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)<br/>
[SetLayeredWindowAttributes](/windows/desktop/api/winuser/nf-winuser-setlayeredwindowattributes)
