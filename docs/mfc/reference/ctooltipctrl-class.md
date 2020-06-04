---
title: CToolTipCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CToolTipCtrl
- AFXCMN/CToolTipCtrl
- AFXCMN/CToolTipCtrl::CToolTipCtrl
- AFXCMN/CToolTipCtrl::Activate
- AFXCMN/CToolTipCtrl::AddTool
- AFXCMN/CToolTipCtrl::AdjustRect
- AFXCMN/CToolTipCtrl::Create
- AFXCMN/CToolTipCtrl::CreateEx
- AFXCMN/CToolTipCtrl::DelTool
- AFXCMN/CToolTipCtrl::GetBubbleSize
- AFXCMN/CToolTipCtrl::GetCurrentTool
- AFXCMN/CToolTipCtrl::GetDelayTime
- AFXCMN/CToolTipCtrl::GetMargin
- AFXCMN/CToolTipCtrl::GetMaxTipWidth
- AFXCMN/CToolTipCtrl::GetText
- AFXCMN/CToolTipCtrl::GetTipBkColor
- AFXCMN/CToolTipCtrl::GetTipTextColor
- AFXCMN/CToolTipCtrl::GetTitle
- AFXCMN/CToolTipCtrl::GetToolCount
- AFXCMN/CToolTipCtrl::GetToolInfo
- AFXCMN/CToolTipCtrl::HitTest
- AFXCMN/CToolTipCtrl::Pop
- AFXCMN/CToolTipCtrl::Popup
- AFXCMN/CToolTipCtrl::RelayEvent
- AFXCMN/CToolTipCtrl::SetDelayTime
- AFXCMN/CToolTipCtrl::SetMargin
- AFXCMN/CToolTipCtrl::SetMaxTipWidth
- AFXCMN/CToolTipCtrl::SetTipBkColor
- AFXCMN/CToolTipCtrl::SetTipTextColor
- AFXCMN/CToolTipCtrl::SetTitle
- AFXCMN/CToolTipCtrl::SetToolInfo
- AFXCMN/CToolTipCtrl::SetToolRect
- AFXCMN/CToolTipCtrl::SetWindowTheme
- AFXCMN/CToolTipCtrl::Update
- AFXCMN/CToolTipCtrl::UpdateTipText
helpviewer_keywords:
- CToolTipCtrl [MFC], CToolTipCtrl
- CToolTipCtrl [MFC], Activate
- CToolTipCtrl [MFC], AddTool
- CToolTipCtrl [MFC], AdjustRect
- CToolTipCtrl [MFC], Create
- CToolTipCtrl [MFC], CreateEx
- CToolTipCtrl [MFC], DelTool
- CToolTipCtrl [MFC], GetBubbleSize
- CToolTipCtrl [MFC], GetCurrentTool
- CToolTipCtrl [MFC], GetDelayTime
- CToolTipCtrl [MFC], GetMargin
- CToolTipCtrl [MFC], GetMaxTipWidth
- CToolTipCtrl [MFC], GetText
- CToolTipCtrl [MFC], GetTipBkColor
- CToolTipCtrl [MFC], GetTipTextColor
- CToolTipCtrl [MFC], GetTitle
- CToolTipCtrl [MFC], GetToolCount
- CToolTipCtrl [MFC], GetToolInfo
- CToolTipCtrl [MFC], HitTest
- CToolTipCtrl [MFC], Pop
- CToolTipCtrl [MFC], Popup
- CToolTipCtrl [MFC], RelayEvent
- CToolTipCtrl [MFC], SetDelayTime
- CToolTipCtrl [MFC], SetMargin
- CToolTipCtrl [MFC], SetMaxTipWidth
- CToolTipCtrl [MFC], SetTipBkColor
- CToolTipCtrl [MFC], SetTipTextColor
- CToolTipCtrl [MFC], SetTitle
- CToolTipCtrl [MFC], SetToolInfo
- CToolTipCtrl [MFC], SetToolRect
- CToolTipCtrl [MFC], SetWindowTheme
- CToolTipCtrl [MFC], Update
- CToolTipCtrl [MFC], UpdateTipText
ms.assetid: 8973f70c-b73a-46c7-908d-758f364b9a97
ms.openlocfilehash: 53a5a5b6871680f9758d140174dcceae6c53f568
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752200"
---
# <a name="ctooltipctrl-class"></a>CToolTipCtrl Class

"ツールヒント コントロール" の機能をカプセル化しています。このコンロトールは、アプリケーションでツールの目的を説明する 1 行のテキストを表示する小さなポップアップ ウィンドウです。

## <a name="syntax"></a>構文

```
class CToolTipCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CツールチップCtrl::CツールチップCtrl](#ctooltipctrl)|`CToolTipCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CツールチップCtrl::アクティブ化](#activate)|ツール ヒント コントロールをアクティブまたは非アクティブにします。|
|[CツールチップCtrl::ツールの追加](#addtool)|ツール ヒント コントロールにツールを登録します。|
|[CツールチップCtrl::アジャストレック](#adjustrect)|ツール ヒント コントロールのテキスト表示四角形とそのウィンドウ四角形の間で変換します。|
|[CツールチップCtrl::作成](#create)|ツール ヒント コントロールを作成し、`CToolTipCtrl`オブジェクトにアタッチします。|
|[CツールチップCtrl::作成します。](#createex)|指定した Windows 拡張スタイルを使用してツール ヒント コントロールを作成`CToolTipCtrl`し、オブジェクトにアタッチします。|
|[CツールチップCtrl::Dエルツール](#deltool)|ツール ヒント コントロールからツールを削除します。|
|[CツールチップCtrl:::ゲットバブルサイズ](#getbubblesize)|ツール ヒントのサイズを取得します。|
|[次のツールヒントCtrl::現在のツールを取得します。](#getcurrenttool)|現在のツールヒント コントロールが表示するツールヒント ウィンドウのサイズ、位置、テキストなどの情報を取得します。|
|[次の値を取得します。](#getdelaytime)|ツール ヒント コントロールに現在設定されている初期、ポップアップ、および再表示の期間を取得します。|
|[CツールチップCtrl::ゲットマージン](#getmargin)|ツール ヒント ウィンドウに設定されている上余白、左余白、下余白、および右余白を取得します。|
|[ウィンドウヒントCtrl::取得最大ヒント幅](#getmaxtipwidth)|ツール ヒント ウィンドウの最大幅を取得します。|
|[次のテキストを取得します。](#gettext)|ツール ヒント コントロールがツールに保持するテキストを取得します。|
|[CツールチップCtrl::ゲットチップBkカラー](#gettipbkcolor)|ツール ヒント ウィンドウの背景色を取得します。|
|[次の文字列を取得します。](#gettiptextcolor)|ツール ヒント ウィンドウのテキストの色を取得します。|
|[CツールチップCtrl::タイトルを取得します。](#gettitle)|現在のツールヒント コントロールのタイトルを取得します。|
|[ツールヒントCtrl::GetToolCount](#gettoolcount)|ツール ヒント コントロールによって管理されるツールの数を取得します。|
|[ツールヒントCtrl::GetToolInfo](#gettoolinfo)|ツール ヒント コントロールがツールに関して保持する情報を取得します。|
|[CツールチップCtrl::ヒットテスト](#hittest)|ポイントが、指定されたツールの外接する四角形内にあるかどうかを判断します。 その場合は、ツールに関する情報を取得します。|
|[CツールチップCtrl::Pop](#pop)|表示されたツール ヒント ウィンドウをビューから削除します。|
|[CツールチップCtrl::Pオップアップ](#popup)|現在のツール ヒント コントロールを、最後のマウス メッセージの座標で表示します。|
|[CツールチップCtrl::リレーイベント](#relayevent)|マウス メッセージをツール ヒント コントロールに渡して処理します。|
|[CツールチップCtrl::セットディレイタイム](#setdelaytime)|ツール ヒント コントロールの初期、ポップアップ、および再表示の継続時間を設定します。|
|[CツールチップCtrl::セットマージン](#setmargin)|ツール ヒント ウィンドウの上下左右の余白を設定します。|
|[CツールチップCtrl::セットマックスチップ幅](#setmaxtipwidth)|ツール ヒント ウィンドウの最大幅を設定します。|
|[CツールチップCtrl::セットチップBkカラー](#settipbkcolor)|ツール ヒント ウィンドウの背景色を設定します。|
|[C ツールヒントCtrl::テキストの色を設定します。](#settiptextcolor)|ツール ヒント ウィンドウのテキストの色を設定します。|
|[CツールチップCtrl::セットタイトル](#settitle)|ツール ヒントに標準アイコンとタイトル文字列を追加します。|
|[CツールチップCtrl::セットツールインフォ](#settoolinfo)|ツールヒントがツールに保持する情報を設定します。|
|[CツールチップCtrl::セットツールレクト](#settoolrect)|ツールの新しい外接する四角形を設定します。|
|[CツールチップCtrl::セットウィンドウテーマ](#setwindowtheme)|ツール ヒント ウィンドウの表示スタイルを設定します。|
|[CツールチップCtrl::更新](#update)|現在のツールを強制的に再描画します。|
|[次のテキストを表示します。](#updatetiptext)|ツールのツール ヒント テキストを設定します。|

## <a name="remarks"></a>解説

"ツール" とは、子ウィンドウやコントロールなどのウィンドウ、またはウィンドウのクライアント領域内のアプリケーション定義の四角形領域です。 ツール ヒントは、ほとんどの場合、ツールにカーソルを置いて約 2 分の 1 の時間そこに残したときにのみ表示されます。 ツール ヒントはカーソルの近くに表示され、ユーザーがマウス ボタンをクリックするか、ツールの外にカーソルを移動すると表示されなくなります。

`CToolTipCtrl`ツール ヒントの初期時間と期間、ツール ヒント テキストの周囲の余白の幅、ツール ヒント ウィンドウ自体の幅、およびツール ヒントの背景色とテキストの色を制御する機能が提供されます。 1 つのツール ヒント コントロールは、複数のツールに情報を提供できます。

この`CToolTipCtrl`クラスは、Windows 共通ツール ヒント コントロールの機能を提供します。 このコントロール (および`CToolTipCtrl`クラス) は、Windows 95/98 および Windows NT バージョン 3.51 以降で実行されているプログラムでのみ使用できます。

ツール ヒントを有効にする方法の詳細については、「 [CFrameWnd から派生していない Windows のツール ヒント](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)」を参照してください。

の詳細`CToolTipCtrl`については、「[コントロール](../../mfc/controls-mfc.md)と[CToolTipCtrl を使用する](../../mfc/using-ctooltipctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxcmn.h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a>CツールチップCtrl::アクティブ化

ツール ヒント コントロールをアクティブまたは非アクティブ化します。

```cpp
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bアクティブ化*<br/>
ツール ヒント コントロールをアクティブにするか非アクティブにするかを指定します。

### <a name="remarks"></a>解説

*bActivate*が TRUE の場合、コントロールはアクティブになります。FALSE の場合は、非アクティブになります。

ツール ヒント コントロールがアクティブな場合、コントロールに登録されているツール上にカーソルが置かれたときは、ツール ヒント情報が表示されます。非アクティブの場合、カーソルがツール上にある場合でも、ツール ヒント情報は表示されません。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a>CツールチップCtrl::ツールの追加

ツール ヒント コントロールにツールを登録します。

```
BOOL AddTool(
    CWnd* pWnd,
    UINT nIDText,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);

BOOL AddTool(
    CWnd* pWnd,
    LPCTSTR lpszText = LPSTR_TEXTCALLBACK,
    LPCRECT lpRectTool = NULL,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*テキスト*<br/>
ツールのテキストを含む文字列リソースの ID。

*ツール*<br/>
ツールの外接する四角形の座標を格納する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。 座標は *、pWnd*で識別されるウィンドウのクライアント領域の左上隅を基準にしています。

*NIDツール*<br/>
ツールの ID。

*lpszText*<br/>
ツールのテキストへのポインター。 このパラメーターにLPSTR_TEXTCALLBACK値が含まれている場合、通知メッセージTTN_NEEDTEXT *pWnd*が指すウィンドウの親に送られます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*lpRectTool*パラメーターと*nIDTool*パラメーターは両方とも有効*lpRectTool*である必要があります。 *nIDTool*

ツール ヒント コントロールは、複数のツールに関連付けることができます。 ツール ヒント コントロールにツールを登録し、ツール上にカーソルが置いたときにツール ヒントに格納されている情報が表示されるようにします。

> [!NOTE]
> ツール ヒントをを使用して`AddTool`静的コントロールに設定することはできません。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a>CツールチップCtrl::アジャストレック

ツールヒント コントロールのテキスト表示四角形とそのウィンドウ四角形の間で変換します。

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>パラメーター

*Lprc*<br/>
ツール ヒント ウィンドウの四角形またはテキスト表示の四角形を保持する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。

*大きく*<br/>
TRUE の場合 *、lprc*を使用してテキスト表示の四角形を指定し、対応するウィンドウ四角形を受け取ります。 FALSE の場合 *、lprc*を使用してウィンドウの四角形を指定し、対応するテキスト表示四角形を受け取ります。

### <a name="return-value"></a>戻り値

四角形が正常に調整された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメンバー関数は、ツール ヒント コントロールのテキスト表示四角形を、そのウィンドウの四角形から計算するか、指定したテキスト表示四角形を表示するために必要なツール ヒント ウィンドウの四角形を計算します。

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect)の動作を実装します。

## <a name="ctooltipctrlcreate"></a><a name="create"></a>CツールチップCtrl::作成

ツール ヒント コントロールを作成し、`CToolTipCtrl`オブジェクトにアタッチします。

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ツール ヒント コントロールの親ウィンドウを指定`CDialog`します。 NULL にすることはできません。

*Dwstyle*<br/>
ツール ヒント コントロールのスタイルを指定します。 詳細**については、「解説」** を参照してください。

### <a name="return-value"></a>戻り値

オブジェクトが正常に`CToolTipCtrl`作成された場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

を`CToolTipCtrl`2 つの手順で作成します。 まず、オブジェクトを構築するコンストラクターを`CToolTipCtrl`呼び出し、`Create`ツール ヒント コントロールを作成してオブジェクトにアタッチ`CToolTipCtrl`する呼び出しを行います。

*dwStyle*パラメーターは、[ウィンドウ スタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の任意の組み合わせにすることができます。 さらに、ツール ヒント コントロールには、TTS_ALWAYSTIP と TTS_NOPREFIX というクラス固有のスタイルが 2 つ用意されています。

|Style|意味|
|-----------|-------------|
|TTS_ALWAYSTIP|ツール ヒント コントロールのオーナー ウィンドウがアクティブか非アクティブかにかかわらず、ツール上にカーソルが置かれるときツール ヒントが表示されるように指定します。 このスタイルを使用しない場合、ツールヒントコントロールは、ツールのオーナー ウィンドウがアクティブな場合には表示されますが、非アクティブの場合は表示されません。|
|TTS_NOPREFIX|このスタイルは、システムがアンパサンド (&) 文字を文字列から取り除くのを防ぎます。 ツール ヒント コントロールにTTS_NOPREFIXスタイルがない場合、システムはアンパサンド文字を自動的に取り除き、アプリケーションがメニュー項目とテキストの両方としてツール ヒント コントロール内の文字列として同じ文字列を使用できるようにします。|

ツール ヒント コントロールには、コントロールの作成時に指定するかどうかに関係なく、WS_POPUPとWS_EX_TOOLWINDOWウィンドウ スタイルがあります。

拡張ウィンドウ スタイルを使用してツール ヒント コントロールを作成するには、代わりに[CToolTipCtrl::CreateEx](#createex)を呼び出`Create`します。

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a>CツールチップCtrl::作成します。

コントロール (子ウィンドウ) を作成し、`CToolTipCtrl`オブジェクトに関連付けます。

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*Dwstyle*<br/>
ツール ヒント コントロールのスタイルを指定します。 詳細については、[作成](#create)の **「解説**」セクションを参照してください。

*ドウスタイルエックス*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の*DwExStyle*パラメーター[を](/windows/win32/api/winuser/nf-winuser-createwindowexw)参照してください。

### <a name="return-value"></a>戻り値

成功した場合は 0 以外の場合は 0 以外の値を返します。

### <a name="remarks"></a>解説

Windows`CreateEx`拡張`Create`スタイルの序文で指定された拡張 Windows スタイルを適用**する代わりに使用WS_EX_。**

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a>CツールチップCtrl::CツールチップCtrl

`CToolTipCtrl` オブジェクトを構築します。

```
CToolTipCtrl();
```

### <a name="remarks"></a>解説

オブジェクトを構築`Create`した後に呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a>CツールチップCtrl::Dエルツール

ツール ヒント コントロールでサポートされているツールのコレクションから *、pWnd*および*nIDTool*で指定されたツールを削除します。

```cpp
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*NIDツール*<br/>
ツールの ID。

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a>CツールチップCtrl:::ゲットバブルサイズ

ツール ヒントのサイズを取得します。

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>パラメーター

*ツール情報*<br/>
ツール ヒントの[TOOLINFO 構造体](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)へのポインター。

### <a name="return-value"></a>戻り値

ツール ヒントのサイズ。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_GETBUBBLESIZE](/windows/win32/Controls/ttm-getbubblesize)の動作を実装します。

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a>次のツールヒントCtrl::現在のツールを取得します。

現在のツールヒント コントロールによって表示されるツールヒント ウィンドウのサイズ、位置、テキストなどの情報を取得します。

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*ツール情報*|[アウト]現在のツールヒント ウィンドウに関する情報を受け取る[TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)構造体へのポインター。|

### <a name="return-value"></a>戻り値

情報が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool)メッセージを送信します。

### <a name="example"></a>例

現在のツールヒント ウィンドウに関する情報を取得するコード例を次に示します。

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a>次の値を取得します。

ツール ヒント コントロールに現在設定されている初期、ポップアップ、および再表示の期間を取得します。

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>パラメーター

*dwDuration*<br/>
取得する期間の値を指定するフラグ。 このパラメーターには、次のいずれかの値を指定できます。

- TTDT_AUTOPOP ツールの外接する四角形内でポインタが静止している場合に、ツール ヒント ウィンドウが表示される時間の長さを取得します。

- TTDT_INITIAL ツール ヒント ウィンドウが表示されるまでに、ツールの外接する四角形内でポインターが固定された状態を維持する必要がある時間を取得します。

- TTDT_RESHOW ポインターが 1 つのツールから別のツールに移動するときに、後続のツール ヒント ウィンドウが表示されるまでにかかる時間を取得します。

### <a name="return-value"></a>戻り値

指定された遅延時間 (ミリ秒)

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_GETDELAYTIME](/windows/win32/Controls/ttm-getdelaytime)の動作を実装します。

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a>CツールチップCtrl::ゲットマージン

ツール ヒント ウィンドウに設定されている上余白、左余白、下余白、および右余白を取得します。

```cpp
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>パラメーター

*Lprc*<br/>
マージン情報を`RECT`受け取る構造体のアドレス。 [RECT](/windows/win32/api/windef/ns-windef-rect)構造体のメンバーは、外接する四角形を定義しません。 このメッセージの目的のために、構造体メンバーは次のように解釈されます。

|メンバー|[表記]|
|------------|--------------------|
|`top`|上の境界線とツール ヒントテキストの上端の間の距離 (ピクセル単位)。|
|`left`|ヒント テキストの左の境界線と左端の間の距離 (ピクセル単位)。|
|`bottom`|下の境界線と先端テキストの下部の距離 (ピクセル単位)。|
|`right`|右の境界線とヒントテキストの右端の間の距離 (ピクセル単位)。|

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin)の動作を実装します。

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a>ウィンドウヒントCtrl::取得最大ヒント幅

ツール ヒント ウィンドウの最大幅を取得します。

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>戻り値

ツール ヒント ウィンドウの最大幅。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth)の動作を実装します。

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a>次のテキストを取得します。

ツール ヒント コントロールがツールに保持するテキストを取得します。

```cpp
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
ツールのテキスト`CString`を受け取るオブジェクトへの参照。

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*NIDツール*<br/>
ツールの ID。

### <a name="remarks"></a>解説

*pWnd*および*nIDTool*パラメーターは、ツールを識別します。 そのツールが以前の呼び出しを通じてツール ヒント コントロール`CToolTipCtrl::AddTool`に登録されている場合 *、str*パラメーターによって参照されるオブジェクトには、ツールのテキストが割り当てられます。

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a>CツールチップCtrl::ゲットチップBkカラー

ツール ヒント ウィンドウの背景色を取得します。

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>戻り値

背景色を表す[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_GETTIPBKCOLOR](/windows/win32/Controls/ttm-gettipbkcolor)の動作を実装します。

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a>次の文字列を取得します。

ツール ヒント ウィンドウのテキストの色を取得します。

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>戻り値

テキストの色を表す[COLORREF](/windows/win32/gdi/colorref)値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_GETTIPTEXTCOLOR](/windows/win32/Controls/ttm-gettiptextcolor)の動作を実装します。

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a>CツールチップCtrl::タイトルを取得します。

現在のツールヒント コントロールのタイトルを取得します。

```cpp
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*pttgt*|[アウト]ツールヒント コントロールに関する情報を含む[TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle)構造体へのポインター。 このメソッドが返されるときに[、TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle)構造体の*pszTitle*メンバーはタイトルのテキストを指します。|

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle)メッセージを送信します。

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a>ツールヒントCtrl::GetToolCount

ツール ヒント コントロールに登録されているツールの数を取得します。

```
int GetToolCount() const;
```

### <a name="return-value"></a>戻り値

ツール ヒント コントロールに登録されているツールの数。

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a>ツールヒントCtrl::GetToolInfo

ツール ヒント コントロールがツールに関して保持する情報を取得します。

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>パラメーター

*ツール情報*<br/>
ツールのテキスト`TOOLINFO`を受け取るオブジェクトへの参照。

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*NIDツール*<br/>
ツールの ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`hwnd` `uId` *CToolInfo*によって参照される[TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)構造体の と のメンバーは、ツールを識別します。 ツールがツール ヒント コントロールに登録されている場合は、前の呼`AddTool`び出`TOOLINFO`しを使用して、ツールに関する情報が構造体に格納されます。

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a>CツールチップCtrl::ヒットテスト

ポイントが指定されたツールの外接する四角形内にあるかどうかを判断し、その場合はツールに関する情報を取得するかどうかをテストします。

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*Pt*<br/>
テスト対象の`CPoint`ポイントの座標を含むオブジェクトへのポインター。

*ツール情報*<br/>
ツールに関する情報を含む[TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)構造体へのポインター。

### <a name="return-value"></a>戻り値

ヒット テスト情報で指定されたポイントがツールの外接する四角形内にある場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

この関数が 0 以外の値を返す場合 *、lpToolInfo*によって指す構造体には、そのポイントがある四角形内のツールに関する情報が格納されます。

構造`TTHITTESTINFO`は次のように定義されます。

```cpp
typedef struct _TT_HITTESTINFO { // tthti
    HWND hwnd;   // handle of tool or window with tool
    POINT pt;    // client coordinates of point to test
    TOOLINFO ti; // receives information about the tool
} TTHITTESTINFO, FAR * LPHITTESTINFO;
```

- `hwnd`

   ツールのハンドルを指定します。

- `pt`

   点がツールの外接する四角形にある場合に、点の座標を指定します。

- `ti`

   ツールに関する情報。 構造の`TOOLINFO`詳細については[、「CToolTipCtrl::GetToolInfo](#gettoolinfo)」を参照してください。

## <a name="ctooltipctrlpop"></a><a name="pop"></a>CツールチップCtrl::Pop

表示されたツール ヒント ウィンドウをビューから削除します。

```cpp
void Pop();
```

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_POP](/windows/win32/Controls/ttm-pop)の動作を実装します。

## <a name="ctooltipctrlpopup"></a><a name="popup"></a>CツールチップCtrl::Pオップアップ

現在のツールヒント コントロールを、最後のマウス メッセージの座標で表示します。

```cpp
void Popup();
```

### <a name="remarks"></a>解説

このメソッドは、Windows SDK に記載されている[TTM_POPUP](/windows/win32/Controls/ttm-popup)メッセージを送信します。

### <a name="example"></a>例

ツールヒント ウィンドウを表示するコード例を次に示します。

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a>CツールチップCtrl::リレーイベント

マウス メッセージをツール ヒント コントロールに渡して処理します。

```cpp
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
中継するメッセージを含む[MSG](/windows/win32/api/winuser/ns-winuser-msg)構造体へのポインター。

### <a name="remarks"></a>解説

ツール ヒント コントロールは、次のメッセージのみを処理します`RelayEvent`。

|WM_LBUTTONDOWN|Wm_mousemove|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>例

  次の例[を](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)参照してください。

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a>CツールチップCtrl::セットディレイタイム

ツール ヒント コントロールの遅延時間を設定します。

```cpp
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>パラメーター

*nディレイ*<br/>
新しい遅延時間をミリ秒単位で指定します。

*dwDuration*<br/>
取得する期間の値を指定するフラグ。 有効な値の説明については[、CToolTipCtrl::GetDelayTime](#getdelaytime)を参照してください。

*iTime*<br/>
指定された遅延時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

遅延時間とは、ツール ヒント ウィンドウが表示されるまでのカーソルがツールに残る時間の長さです。 デフォルトの遅延時間は 500 ミリ秒です。

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a>CツールチップCtrl::セットマージン

ツール ヒント ウィンドウの上下左右の余白を設定します。

```cpp
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>パラメーター

*Lprc*<br/>
設定する`RECT`余白情報を含む構造体のアドレス。 構造体の`RECT`メンバーは、外接する四角形を定義しません。 マージン情報の説明については[、CToolTipCtrl::GetMargin](#getmargin)を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin)の動作を実装します。

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a>CツールチップCtrl::セットマックスチップ幅

ツール ヒント ウィンドウの最大幅を設定します。

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>パラメーター

*幅*<br/>
設定するツール ヒント ウィンドウの最大幅。

### <a name="return-value"></a>戻り値

直前の最大チップ幅。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth)の動作を実装します。

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a>CツールチップCtrl::セットチップBkカラー

ツール ヒント ウィンドウの背景色を設定します。

```cpp
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*Clr*<br/>
新しい背景色。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_SETTIPBKCOLOR](/windows/win32/Controls/ttm-settipbkcolor)の動作を実装します。

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a>C ツールヒントCtrl::テキストの色を設定します。

ツール ヒント ウィンドウのテキストの色を設定します。

```cpp
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

*Clr*<br/>
新しいテキストの色。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_SETTIPTEXTCOLOR](/windows/win32/Controls/ttm-settiptextcolor)の動作を実装します。

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a>CツールチップCtrl::セットタイトル

ツール ヒントに標準アイコンとタイトル文字列を追加します。

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>パラメーター

*uアイコン*<br/>
Windows SDK の[TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)の*アイコン*を参照してください。

*タイトル*<br/>
タイトル文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ[TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)の動作を実装します。

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a>CツールチップCtrl::セットツールインフォ

ツールヒントがツールに保持する情報を設定します。

```cpp
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>パラメーター

*ツール情報*<br/>
設定する情報を指定する[TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)構造体へのポインター。

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a>CツールチップCtrl::セットツールレクト

ツールの新しい外接する四角形を設定します。

```cpp
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*NIDツール*<br/>
ツールの ID。

*Lprect*<br/>
新しい外接する四角形を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体へのポインター。

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a>CツールチップCtrl::セットウィンドウテーマ

ツール ヒント ウィンドウの表示スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
設定する表示スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように[、TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme)メッセージの機能をエミュレートします。

## <a name="ctooltipctrlupdate"></a><a name="update"></a>CツールチップCtrl::更新

現在のツールを強制的に再描画します。

```cpp
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a>次のテキストを表示します。

このコントロールのツールのツール ヒント テキストを更新します。

```cpp
void UpdateTipText(
    LPCTSTR lpszText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);

void UpdateTipText(
    UINT nIDText,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>パラメーター

*lpszText*<br/>
ツールのテキストへのポインター。

*Pwnd*<br/>
ツールを含むウィンドウへのポインター。

*NIDツール*<br/>
ツールの ID。

*テキスト*<br/>
ツールのテキストを含む文字列リソースの ID。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[CToolBar クラス](../../mfc/reference/ctoolbar-class.md)
