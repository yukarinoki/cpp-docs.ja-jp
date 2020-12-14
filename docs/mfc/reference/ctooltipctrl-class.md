---
description: '詳細情報: CToolTipCtrl クラス'
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
ms.openlocfilehash: bd263d0ada7ad85169eb551dd136f81b480534e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345031"
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
|[CToolTipCtrl:: CToolTipCtrl](#ctooltipctrl)|`CToolTipCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CToolTipCtrl:: Activate](#activate)|ツールヒントコントロールをアクティブにし、非アクティブにします。|
|[CToolTipCtrl:: AddTool](#addtool)|ツールをツールヒントコントロールに登録します。|
|[CToolTipCtrl:: AdjustRect](#adjustrect)|ツールヒントコントロールのテキスト表示の四角形とそのウィンドウの四角形との間で変換を行います。|
|[CToolTipCtrl:: Create](#create)|ツールヒントコントロールを作成し、オブジェクトにアタッチし `CToolTipCtrl` ます。|
|[CToolTipCtrl:: CreateEx](#createex)|指定された Windows 拡張スタイルを使用してツールヒントコントロールを作成し、オブジェクトにアタッチし `CToolTipCtrl` ます。|
|[CToolTipCtrl::D elTool](#deltool)|ツールヒントコントロールからツールを削除します。|
|[CToolTipCtrl:: GetBubbleSize](#getbubblesize)|ツールヒントのサイズを取得します。|
|[CToolTipCtrl:: GetCurrentTool](#getcurrenttool)|現在のツールヒントコントロールに表示されるツールヒントウィンドウのサイズ、位置、テキストなどの情報を取得します。|
|[CToolTipCtrl:: GetDelayTime](#getdelaytime)|ツールヒントコントロールに現在設定されている、初期、ポップアップ、および再表示の期間を取得します。|
|[CToolTipCtrl:: GetMargin](#getmargin)|ツールヒントウィンドウに設定されている上下左右の余白を取得します。|
|[CToolTipCtrl:: Getmaxヒントの幅](#getmaxtipwidth)|ツールヒントウィンドウの最大の幅を取得します。|
|[CToolTipCtrl:: GetText](#gettext)|ツールヒントコントロールがツールに対して保持するテキストを取得します。|
|[CToolTipCtrl:: GetTipBkColor](#gettipbkcolor)|ツールヒントウィンドウの背景色を取得します。|
|[CToolTipCtrl:: Get? Textcolor](#gettiptextcolor)|ツールヒントウィンドウのテキストの色を取得します。|
|[CToolTipCtrl:: GetTitle](#gettitle)|現在のツールヒントコントロールのタイトルを取得します。|
|[CToolTipCtrl:: GetToolCount](#gettoolcount)|ツールヒントコントロールによって保持されているツールの数を取得します。|
|[CToolTipCtrl:: GetToolInfo](#gettoolinfo)|ツールヒントコントロールがツールに関して保持する情報を取得します。|
|[CToolTipCtrl:: System.windows.media.visualtreehelper.hittest](#hittest)|指定したツールの外接する四角形内にあるかどうかを判断するポイントをテストします。 存在する場合は、ツールに関する情報を取得します。|
|[CToolTipCtrl::P op](#pop)|表示されているツールヒントウィンドウを表示から削除します。|
|[CToolTipCtrl::P opup](#popup)|現在のツールヒントコントロールを最後のマウスメッセージの座標に表示します。|
|[CToolTipCtrl:: RelayEvent](#relayevent)|処理のためのツールヒントコントロールにマウスメッセージを渡します。|
|[CToolTipCtrl:: SetDelayTime](#setdelaytime)|ツールヒントコントロールの初期、ポップアップ、および再表示の継続時間を設定します。|
|[CToolTipCtrl:: SetMargin](#setmargin)|ツールヒントウィンドウの上下左右の余白を設定します。|
|[CToolTipCtrl:: SetMaxTipWidth](#setmaxtipwidth)|ツールヒントウィンドウの最大幅を設定します。|
|[CToolTipCtrl:: SetTipBkColor](#settipbkcolor)|ツールヒントウィンドウの背景色を設定します。|
|[CToolTipCtrl:: Set? Textcolor](#settiptextcolor)|ツールヒントウィンドウのテキストの色を設定します。|
|[CToolTipCtrl:: SetTitle](#settitle)|標準アイコンとタイトル文字列をツールヒントに追加します。|
|[CToolTipCtrl:: SetToolInfo](#settoolinfo)|ツールのツールヒントによって保持される情報を設定します。|
|[CToolTipCtrl:: SetToolRect](#settoolrect)|ツールの新しい外接する四角形を設定します。|
|[CToolTipCtrl:: SetWindowTheme](#setwindowtheme)|ツールヒントウィンドウの視覚スタイルを設定します。|
|[CToolTipCtrl:: Update](#update)|現在のツールを強制的に再描画します。|
|[CToolTipCtrl:: UpdateTipText](#updatetiptext)|ツールのツールヒントテキストを設定します。|

## <a name="remarks"></a>解説

"ツール" は、子ウィンドウやコントロールなどのウィンドウ、またはウィンドウのクライアント領域内のアプリケーション定義の四角形領域のいずれかです。 ツールヒントは、ほとんどの場合は非表示になります。ユーザーがカーソルをツールに置いて、約1分の1秒間に移動した場合にのみ表示されます。 ツールヒントはカーソルの近くに表示され、ユーザーがマウスボタンをクリックするか、カーソルをツールから移動すると消えます。

`CToolTipCtrl` ツールヒントの初期時間と期間、ツールヒントテキストを囲む余白の幅、ツールヒントウィンドウの幅、ツールヒントの背景とテキストの色を制御する機能を提供します。 1つのツールヒントコントロールで、複数のツールに関する情報を提供できます。

クラスは、 `CToolTipCtrl` Windows コモンツールヒントコントロールの機能を提供します。 このコントロール (および `CToolTipCtrl` クラス) は、windows 95/98 および WINDOWS NT バージョン3.51 以降で実行されているプログラムに対してのみ使用できます。

ツールヒントを有効にする方法の詳細については、「 [CFrameWnd から派生していない Windows のツールヒント](../../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)」を参照してください。

の使用方法の詳細について `CToolTipCtrl` は、「 [Controls](../../mfc/controls-mfc.md) and [using CToolTipCtrl](../../mfc/using-ctooltipctrl.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CToolTipCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxcmn.h

## <a name="ctooltipctrlactivate"></a><a name="activate"></a> CToolTipCtrl:: Activate

ツールヒントコントロールをアクティブ化または非アクティブ化するには、この関数を呼び出します。

```cpp
void Activate(BOOL bActivate);
```

### <a name="parameters"></a>パラメーター

*bActivate*<br/>
ツールヒントコントロールをアクティブまたは非アクティブにするかどうかを指定します。

### <a name="remarks"></a>解説

*Bactivate* が TRUE の場合、コントロールはアクティブになります。FALSE の場合、非アクティブ化されます。

ツールヒントコントロールがアクティブになると、コントロールに登録されているツール上にカーソルがあるときにツールヒント情報が表示されます。非アクティブになると、カーソルがツール上にある場合でも、ツールヒントの情報は表示されません。

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="ctooltipctrladdtool"></a><a name="addtool"></a> CToolTipCtrl:: AddTool

ツールをツールヒントコントロールに登録します。

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

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*nIDText*<br/>
ツールのテキストを含む文字列リソースの ID。

*lpRectTool*<br/>
ツールの外接する四角形の座標を格納している [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。 座標は、 *pWnd* によって識別されるウィンドウのクライアント領域の左上隅を基準としています。

*nIDTool*<br/>
ツールの ID。

*lpszText*<br/>
ツールのテキストへのポインター。 このパラメーターに LPSTR_TEXTCALLBACK 値が含まれている場合、TTN_NEEDTEXT 通知メッセージは、 *pWnd* が指すウィンドウの親に送られます。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

*LpRectTool* パラメーターと *nIDTool* パラメーターの両方が有効であるか、 *lpRectTool* が NULL の場合、 *nIDTool* は0である必要があります。

ツールヒントコントロールは、複数のツールに関連付けることができます。 ツールをツールヒントコントロールに登録するには、この関数を呼び出します。これにより、ツールヒントに格納されている情報が、カーソルがツール上にあるときに表示されます。

> [!NOTE]
> を使用して、ツールヒントを静的コントロールに設定することはできません `AddTool` 。

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="ctooltipctrladjustrect"></a><a name="adjustrect"></a> CToolTipCtrl:: AdjustRect

ツールヒントコントロールのテキスト表示の四角形とそのウィンドウの四角形との間で変換を行います。

```
BOOL AdjustRect(
    LPRECT lprc,
    BOOL bLarger = TRUE);
```

### <a name="parameters"></a>パラメーター

*lprc*<br/>
ツールヒントウィンドウの四角形またはテキスト表示の四角形のいずれかを保持する [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。

*bLarger*<br/>
TRUE の場合、 *lprc* はテキスト表示の四角形を指定するために使用され、対応するウィンドウの四角形を受け取ります。 FALSE の場合、 *lprc* はウィンドウの四角形を指定するために使用され、対応するテキスト表示の四角形を受け取ります。

### <a name="return-value"></a>戻り値

四角形が正常に調整された場合は0以外の。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメンバー関数は、ウィンドウの四角形からツールヒントコントロールのテキスト表示の四角形を計算します。または、指定したテキスト表示の四角形を表示するために必要なツールヒントウィンドウの四角形を計算します。

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_ADJUSTRECT](/windows/win32/Controls/ttm-adjustrect)の動作を実装します。

## <a name="ctooltipctrlcreate"></a><a name="create"></a> CToolTipCtrl:: Create

ツールヒントコントロールを作成し、オブジェクトにアタッチし `CToolTipCtrl` ます。

```
virtual BOOL Create(CWnd* pParentWnd, DWORD dwStyle = 0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
ツールヒントコントロールの親ウィンドウ (通常は) を指定し `CDialog` ます。 NULL にすることはできません。

*dwStyle*<br/>
ツールヒントコントロールのスタイルを指定します。 詳細については、「 **解説** 」を参照してください。

### <a name="return-value"></a>戻り値

オブジェクトが正常に作成された場合は0以外の場合は `CToolTipCtrl` 。それ以外の場合は0。

### <a name="remarks"></a>解説

を作成する `CToolTipCtrl` には、2つの手順を実行します。 まず、コンストラクターを呼び出し `CToolTipCtrl` てオブジェクトを構築した後、を呼び出して `Create` ツールヒントコントロールを作成し、オブジェクトにアタッチし `CToolTipCtrl` ます。

*DwStyle* パラメーターには、[ウィンドウスタイル](../../mfc/reference/styles-used-by-mfc.md#window-styles)の任意の組み合わせを指定できます。 また、ツールヒントコントロールには、TTS_ALWAYSTIP と TTS_NOPREFIX という2つのクラス固有のスタイルがあります。

|スタイル|説明|
|-----------|-------------|
|TTS_ALWAYSTIP|ツールヒントコントロールのオーナーウィンドウがアクティブか非アクティブかに関係なく、カーソルがツール上にあるときにツールヒントが表示されるように指定します。 このスタイルがないと、ツールのオーナーウィンドウがアクティブなときにツールヒントコントロールが表示されますが、非アクティブになっているときは表示されません。|
|TTS_NOPREFIX|このスタイルは、システムが文字列からアンパサンド (&) 文字を削除しないようにします。 ツールヒントコントロールに TTS_NOPREFIX スタイルが設定されていない場合、アンパサンド文字が自動的に除去されます。これにより、アプリケーションは、メニュー項目としても、ツールヒントコントロールのテキストとしても、同じ文字列を使用できます。|

ツールヒントコントロールには、コントロールの作成時に指定するかどうかに関係なく、WS_POPUP と WS_EX_TOOLWINDOW のウィンドウスタイルがあります。

拡張 windows スタイルを使用してツールヒントコントロールを作成するには、の代わりに [CToolTipCtrl:: CreateEx](#createex) を呼び出し `Create` ます。

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="ctooltipctrlcreateex"></a><a name="createex"></a> CToolTipCtrl:: CreateEx

コントロール (子ウィンドウ) を作成し、オブジェクトに関連付け `CToolTipCtrl` ます。

```
virtual BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwStyle = 0,
    DWORD dwStyleEx = 0);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
コントロールの親であるウィンドウへのポインター。

*dwStyle*<br/>
ツールヒントコントロールのスタイルを指定します。 詳細については、「[作成](#create)」の「**解説**」を参照してください。

*Dwスタイル Ex*<br/>
作成するコントロールの拡張スタイルを指定します。 拡張 Windows スタイルの一覧については、Windows SDK の [CreateWindowEx](/windows/win32/api/winuser/nf-winuser-createwindowexw)の *dwexstyle* パラメーターを参照してください。

### <a name="return-value"></a>戻り値

成功した場合は0以外。それ以外の場合は0。

### <a name="remarks"></a>解説

`CreateEx` `Create` Windows 拡張スタイルの先頭 **WS_EX_** によって指定された拡張 windows スタイルを適用するには、の代わりにを使用します。

## <a name="ctooltipctrlctooltipctrl"></a><a name="ctooltipctrl"></a> CToolTipCtrl:: CToolTipCtrl

`CToolTipCtrl` オブジェクトを構築します。

```
CToolTipCtrl();
```

### <a name="remarks"></a>解説

`Create`オブジェクトを構築した後で、を呼び出す必要があります。

### <a name="example"></a>例

[!code-cpp[NVC_MFCControlLadenDialog#74](../../mfc/codesnippet/cpp/ctooltipctrl-class_1.h)]

## <a name="ctooltipctrldeltool"></a><a name="deltool"></a> CToolTipCtrl::D elTool

ツールヒントコントロールでサポートされているツールのコレクションから、 *pWnd* および *nIDTool* によって指定されたツールを削除します。

```cpp
void DelTool(
    CWnd* pWnd,
    UINT_PTR nIDTool = 0);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*nIDTool*<br/>
ツールの ID。

## <a name="ctooltipctrlgetbubblesize"></a><a name="getbubblesize"></a> CToolTipCtrl:: GetBubbleSize

ツールヒントのサイズを取得します。

```
CSize GetBubbleSize(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>パラメーター

*lpToolInfo*<br/>
ツールヒントの [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 構造体へのポインター。

### <a name="return-value"></a>戻り値

ツールヒントのサイズ。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_GETBUBBLESIZE](/windows/win32/Controls/ttm-getbubblesize)の動作を実装します。

## <a name="ctooltipctrlgetcurrenttool"></a><a name="getcurrenttool"></a> CToolTipCtrl:: GetCurrentTool

現在のツールヒントコントロールによって表示されるツールヒントウィンドウのサイズ、位置、テキストなどの情報を取得します。

```
BOOL GetCurrentTool(LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>パラメーター

*lpToolInfo*\
入出力現在のツールヒントウィンドウに関する情報を受け取る [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 構造体へのポインター。

### <a name="return-value"></a>戻り値

情報が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [TTM_GETCURRENTTOOL](/windows/win32/Controls/ttm-getcurrenttool) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、現在のツールヒントウィンドウに関する情報を取得します。

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#6](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_2.cpp)]

## <a name="ctooltipctrlgetdelaytime"></a><a name="getdelaytime"></a> CToolTipCtrl:: GetDelayTime

ツールヒントコントロールに対して現在設定されている、初期、ポップアップ、および再表示の期間を取得します。

```
int GetDelayTime(DWORD dwDuration) const;
```

### <a name="parameters"></a>パラメーター

*dwDuration*<br/>
取得する duration 値を指定するフラグ。 このパラメーターには、次のいずれかの値を指定できます。

- ポインターがツールの外接する四角形内で静止している場合、ツールヒントウィンドウが表示されたままになる時間の長さを取得 TTDT_AUTOPOP ます。

- ツールヒントウィンドウが表示される前に、ツールの外接する四角形内でポインターが静止している必要がある時間の長さを取得 TTDT_INITIAL します。

- ポインターがツール間を移動したときに、後続のツールヒントウィンドウが表示されるまでにかかる時間を TTDT_RESHOW 取得します。

### <a name="return-value"></a>戻り値

指定された遅延時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_GETDELAYTIME](/windows/win32/Controls/ttm-getdelaytime)の動作を実装します。

## <a name="ctooltipctrlgetmargin"></a><a name="getmargin"></a> CToolTipCtrl:: GetMargin

ツールヒントウィンドウに対して設定されている上下左右の余白を取得します。

```cpp
void GetMargin(LPRECT lprc) const;
```

### <a name="parameters"></a>パラメーター

*lprc*<br/>
`RECT`余白情報を受け取る構造体のアドレス。 [RECT](/windows/win32/api/windef/ns-windef-rect)構造体のメンバーは、外接する四角形を定義していません。 このメッセージのために、構造体のメンバーは次のように解釈されます。

|メンバー|表現|
|------------|--------------------|
|`top`|上罫線とツールヒントテキストの上端の間の距離 (ピクセル単位)。|
|`left`|左罫線と先端テキストの左端の間の距離 (ピクセル単位)。|
|`bottom`|下罫線と先端テキストの下端との間の距離 (ピクセル単位)。|
|`right`|右罫線と先端テキストの右端の間の距離 (ピクセル単位)。|

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_GETMARGIN](/windows/win32/Controls/ttm-getmargin)の動作を実装します。

## <a name="ctooltipctrlgetmaxtipwidth"></a><a name="getmaxtipwidth"></a> CToolTipCtrl:: Getmaxヒントの幅

ツールヒントウィンドウの最大の幅を取得します。

```
int GetMaxTipWidth() const;
```

### <a name="return-value"></a>戻り値

ツールヒントウィンドウの最大幅。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_GETMAXTIPWIDTH](/windows/win32/Controls/ttm-getmaxtipwidth)の動作を実装します。

## <a name="ctooltipctrlgettext"></a><a name="gettext"></a> CToolTipCtrl:: GetText

ツールヒントコントロールがツールに対して保持するテキストを取得します。

```cpp
void GetText(
    CString& str,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>パラメーター

*str*<br/>
`CString`ツールのテキストを受け取るオブジェクトへの参照。

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*nIDTool*<br/>
ツールの ID。

### <a name="remarks"></a>解説

このツールは、 *pWnd* パラメーターと *nIDTool* パラメーターによって識別されます。 以前のの呼び出しによってツールヒントコントロールにそのツールが既に登録されている場合 `CToolTipCtrl::AddTool` 、 *str* パラメーターによって参照されるオブジェクトには、ツールのテキストが割り当てられます。

## <a name="ctooltipctrlgettipbkcolor"></a><a name="gettipbkcolor"></a> CToolTipCtrl:: GetTipBkColor

ツールヒントウィンドウの背景色を取得します。

```
COLORREF GetTipBkColor() const;
```

### <a name="return-value"></a>戻り値

背景色を表す [COLORREF](/windows/win32/gdi/colorref) 値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_GETTIPBKCOLOR](/windows/win32/Controls/ttm-gettipbkcolor)の動作を実装します。

## <a name="ctooltipctrlgettiptextcolor"></a><a name="gettiptextcolor"></a> CToolTipCtrl:: Get? Textcolor

ツールヒントウィンドウのテキストの色を取得します。

```
COLORREF GetTipTextColor() const;
```

### <a name="return-value"></a>戻り値

テキストの色を表す [COLORREF](/windows/win32/gdi/colorref) 値。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_GETTIPTEXTCOLOR](/windows/win32/Controls/ttm-gettiptextcolor)の動作を実装します。

## <a name="ctooltipctrlgettitle"></a><a name="gettitle"></a> CToolTipCtrl:: GetTitle

現在のツールヒントコントロールのタイトルを取得します。

```cpp
void GetTitle(PTTGETTITLE pttgt) const;
```

### <a name="parameters"></a>パラメーター

*pttgt*\
入出力ツールヒントコントロールに関する情報を格納している [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle) 構造体へのポインター。 このメソッドから制御が戻るときに、 [TTGETTITLE](/windows/win32/api/commctrl/ns-commctrl-ttgettitle)構造体の *psztitle* メンバーはタイトルのテキストを指します。

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [TTM_GETTITLE](/windows/win32/Controls/ttm-gettitle) メッセージを送信します。

## <a name="ctooltipctrlgettoolcount"></a><a name="gettoolcount"></a> CToolTipCtrl:: GetToolCount

ツールヒントコントロールに登録されているツールの数を取得します。

```
int GetToolCount() const;
```

### <a name="return-value"></a>戻り値

ツールヒントコントロールに登録されているツールの数。

## <a name="ctooltipctrlgettoolinfo"></a><a name="gettoolinfo"></a> CToolTipCtrl:: GetToolInfo

ツールヒントコントロールがツールに関して保持する情報を取得します。

```
BOOL GetToolInfo(
    CToolInfo& ToolInfo,
    CWnd* pWnd,
    UINT_PTR nIDTool = 0) const;
```

### <a name="parameters"></a>パラメーター

*ToolInfo*<br/>
`TOOLINFO`ツールのテキストを受け取るオブジェクトへの参照。

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*nIDTool*<br/>
ツールの ID。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

`hwnd` `uId` *CToolInfo* によって参照される [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa)構造体のおよびメンバーは、ツールを識別します。 以前のの呼び出しによってツールヒントコントロールにツールが登録されている場合 `AddTool` 、 `TOOLINFO` 構造体にはツールに関する情報が格納されます。

## <a name="ctooltipctrlhittest"></a><a name="hittest"></a> CToolTipCtrl:: System.windows.media.visualtreehelper.hittest

指定したツールの外接する四角形内にあるかどうかを判断するポイントをテストします。存在する場合は、ツールに関する情報を取得します。

```
BOOL HitTest(
    CWnd* pWnd,
    CPoint pt,
    LPTOOLINFO lpToolInfo) const;
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*pt*<br/>
`CPoint`テストする点の座標を格納しているオブジェクトへのポインター。

*lpToolInfo*<br/>
ツールに関する情報を格納している [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 構造体へのポインター。

### <a name="return-value"></a>戻り値

ヒットテスト情報によって指定された点がツールの外接する四角形内にある場合は0以外。それ以外の場合は0です。

### <a name="remarks"></a>解説

この関数が0以外の値を返す場合、 *lpToolInfo* が指す構造体には、そのポイントがある四角形を含むツールの情報が格納されます。

`TTHITTESTINFO`構造体は次のように定義されます。

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

   ポイントがツールの外接する四角形内にある場合の点の座標を指定します。

- `ti`

   ツールに関する情報。 構造体の詳細については `TOOLINFO` 、「 [CToolTipCtrl:: GetToolInfo](#gettoolinfo)」を参照してください。

## <a name="ctooltipctrlpop"></a><a name="pop"></a> CToolTipCtrl::P op

表示されているツールヒントウィンドウをビューから削除します。

```cpp
void Pop();
```

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_POP](/windows/win32/Controls/ttm-pop)の動作を実装します。

## <a name="ctooltipctrlpopup"></a><a name="popup"></a> CToolTipCtrl::P opup

現在のツールヒントコントロールを最後のマウスメッセージの座標に表示します。

```cpp
void Popup();
```

### <a name="remarks"></a>解説

このメソッドは、Windows SDK で説明されている [TTM_POPUP](/windows/win32/Controls/ttm-popup) メッセージを送信します。

### <a name="example"></a>例

次のコード例では、ツールヒントウィンドウを表示します。

[!code-cpp[NVC_MFC_CToolBarCtrl_s1#7](../../mfc/reference/codesnippet/cpp/ctooltipctrl-class_3.cpp)]

## <a name="ctooltipctrlrelayevent"></a><a name="relayevent"></a> CToolTipCtrl:: RelayEvent

処理のためのツールヒントコントロールにマウスメッセージを渡します。

```cpp
void RelayEvent(LPMSG lpMsg);
```

### <a name="parameters"></a>パラメーター

*lpMsg*<br/>
リレーするメッセージが格納されている [MSG](/windows/win32/api/winuser/ns-winuser-msg) 構造体へのポインター。

### <a name="remarks"></a>解説

ツールヒントコントロールは、次のメッセージだけを処理します。これらのメッセージは、によって送信され `RelayEvent` ます。

|WM_LBUTTONDOWN|WM_MOUSEMOVE|
|---------------------|-------------------|
|WM_LBUTTONUP|WM_RBUTTONDOWN|
|WM_MBUTTONDOWN|WM_RBUTTONUP|
|WM_MBUTTONUP||

### <a name="example"></a>例

  [CPropertySheet:: GetTabControl](../../mfc/reference/cpropertysheet-class.md#gettabcontrol)の例を参照してください。

## <a name="ctooltipctrlsetdelaytime"></a><a name="setdelaytime"></a> CToolTipCtrl:: SetDelayTime

ツールヒントコントロールの遅延時間を設定します。

```cpp
void SetDelayTime(UINT nDelay);

void SetDelayTime(
    DWORD dwDuration,
    int iTime);
```

### <a name="parameters"></a>パラメーター

*nDelay*<br/>
新しい遅延時間をミリ秒単位で指定します。

*dwDuration*<br/>
取得する duration 値を指定するフラグ。 有効な値の説明については、「 [CToolTipCtrl:: GetDelayTime](#getdelaytime) 」を参照してください。

*iTime*<br/>
指定された遅延時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

遅延時間は、ツールヒントウィンドウが表示される前に、ツール上にカーソルを残しておく必要がある時間の長さです。 既定の遅延時間は500ミリ秒です。

## <a name="ctooltipctrlsetmargin"></a><a name="setmargin"></a> CToolTipCtrl:: SetMargin

ツールヒントウィンドウの上下左右の余白を設定します。

```cpp
void SetMargin(LPRECT lprc);
```

### <a name="parameters"></a>パラメーター

*lprc*<br/>
`RECT`設定する余白情報を格納している構造体のアドレス。 構造体のメンバーは、 `RECT` 外接する四角形を定義していません。 余白情報の説明については、「 [CToolTipCtrl:: GetMargin](#getmargin) 」を参照してください。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_SETMARGIN](/windows/win32/Controls/ttm-setmargin)の動作を実装します。

## <a name="ctooltipctrlsetmaxtipwidth"></a><a name="setmaxtipwidth"></a> CToolTipCtrl:: SetMaxTipWidth

ツールヒントウィンドウの最大幅を設定します。

```
int SetMaxTipWidth(int iWidth);
```

### <a name="parameters"></a>パラメーター

*iWidth*<br/>
設定するツールヒントウィンドウの最大幅。

### <a name="return-value"></a>戻り値

前の最大の先端の幅。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_SETMAXTIPWIDTH](/windows/win32/Controls/ttm-setmaxtipwidth)の動作を実装します。

## <a name="ctooltipctrlsettipbkcolor"></a><a name="settipbkcolor"></a> CToolTipCtrl:: SetTipBkColor

ツールヒントウィンドウの背景色を設定します。

```cpp
void SetTipBkColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

<bpt id="p1">*</bpt>clr<ept id="p1">*</ept><br/>
新しい背景色。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_SETTIPBKCOLOR](/windows/win32/Controls/ttm-settipbkcolor)の動作を実装します。

## <a name="ctooltipctrlsettiptextcolor"></a><a name="settiptextcolor"></a> CToolTipCtrl:: Set? Textcolor

ツールヒントウィンドウのテキストの色を設定します。

```cpp
void SetTipTextColor(COLORREF clr);
```

### <a name="parameters"></a>パラメーター

<bpt id="p1">*</bpt>clr<ept id="p1">*</ept><br/>
新しいテキストの色。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_SETTIPTEXTCOLOR](/windows/win32/Controls/ttm-settiptextcolor)の動作を実装します。

## <a name="ctooltipctrlsettitle"></a><a name="settitle"></a> CToolTipCtrl:: SetTitle

標準アイコンとタイトル文字列をツールヒントに追加します。

```
BOOL SetTitle(
    UINT uIcon,
    LPCTSTR lpstrTitle);
```

### <a name="parameters"></a>パラメーター

*uIcon*<br/>
Windows SDK の [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)の *アイコン* を参照してください。

*lpstrTitle*<br/>
タイトル文字列へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、Win32 メッセージ [TTM_SETTITLE](/windows/win32/Controls/ttm-settitle)の動作を実装します。

## <a name="ctooltipctrlsettoolinfo"></a><a name="settoolinfo"></a> CToolTipCtrl:: SetToolInfo

ツールのツールヒントによって保持される情報を設定します。

```cpp
void SetToolInfo(LPTOOLINFO lpToolInfo);
```

### <a name="parameters"></a>パラメーター

*lpToolInfo*<br/>
設定する情報を指定する [TOOLINFO](/windows/win32/api/commctrl/ns-commctrl-tttoolinfoa) 構造体へのポインター。

## <a name="ctooltipctrlsettoolrect"></a><a name="settoolrect"></a> CToolTipCtrl:: SetToolRect

ツールの新しい外接する四角形を設定します。

```cpp
void SetToolRect(
    CWnd* pWnd,
    UINT_PTR nIDTool,
    LPCRECT lpRect);
```

### <a name="parameters"></a>パラメーター

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*nIDTool*<br/>
ツールの ID。

*lpRect*<br/>
新しい外接する四角形を指定する [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体へのポインター。

## <a name="ctooltipctrlsetwindowtheme"></a><a name="setwindowtheme"></a> CToolTipCtrl:: SetWindowTheme

ツールヒントウィンドウの視覚スタイルを設定します。

```
HRESULT SetWindowTheme(LPCWSTR pszSubAppName);
```

### <a name="parameters"></a>パラメーター

*pszSubAppName*<br/>
設定する visual スタイルを含む Unicode 文字列へのポインター。

### <a name="return-value"></a>戻り値

戻り値は使用されません。

### <a name="remarks"></a>解説

このメンバー関数は、Windows SDK で説明されているように、 [TTM_SETWINDOWTHEME](/windows/win32/Controls/ttm-setwindowtheme) メッセージの機能をエミュレートします。

## <a name="ctooltipctrlupdate"></a><a name="update"></a> CToolTipCtrl:: Update

現在のツールを強制的に再描画します。

```cpp
void Update();
```

## <a name="ctooltipctrlupdatetiptext"></a><a name="updatetiptext"></a> CToolTipCtrl:: UpdateTipText

このコントロールのツールのツールヒントテキストを更新します。

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

*pWnd*<br/>
ツールが格納されているウィンドウへのポインター。

*nIDTool*<br/>
ツールの ID。

*nIDText*<br/>
ツールのテキストを含む文字列リソースの ID。

## <a name="see-also"></a>関連項目

[CWnd クラス](../../mfc/reference/cwnd-class.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)<br/>
[CToolBar クラス](../../mfc/reference/ctoolbar-class.md)
