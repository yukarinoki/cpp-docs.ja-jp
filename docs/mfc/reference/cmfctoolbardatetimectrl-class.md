---
title: CMFCToolBarDateTimeCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CMFCToolBarDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CanBeStretched
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::CopyFrom
- AFXTOOLBARDATETIMECTRL/CMFCToolBarButton::ExportToMenuButton
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetByCmd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetDateTimeCtrl
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetHwnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::GetTimeAll
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::HaveHotBorder
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::NotifyCommand
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnAddToCustomizePage
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnChangeParentWnd
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnClick
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnCtlColor
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnGlobalFontsChanged
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnMove
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnShow
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::OnUpdateToolTip
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTime
- AFXTOOLBARDATETIMECTRL/CMFCToolBarDateTimeCtrl::SetTimeAll
helpviewer_keywords:
- CMFCToolBarDateTimeCtrl [MFC], CMFCToolBarDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], CanBeStretched
- CMFCToolBarDateTimeCtrl [MFC], CopyFrom
- CMFCToolBarButton [MFC], ExportToMenuButton
- CMFCToolBarDateTimeCtrl [MFC], GetByCmd
- CMFCToolBarDateTimeCtrl [MFC], GetDateTimeCtrl
- CMFCToolBarDateTimeCtrl [MFC], GetHwnd
- CMFCToolBarDateTimeCtrl [MFC], GetTime
- CMFCToolBarDateTimeCtrl [MFC], GetTimeAll
- CMFCToolBarDateTimeCtrl [MFC], HaveHotBorder
- CMFCToolBarDateTimeCtrl [MFC], NotifyCommand
- CMFCToolBarDateTimeCtrl [MFC], OnAddToCustomizePage
- CMFCToolBarDateTimeCtrl [MFC], OnChangeParentWnd
- CMFCToolBarDateTimeCtrl [MFC], OnClick
- CMFCToolBarDateTimeCtrl [MFC], OnCtlColor
- CMFCToolBarDateTimeCtrl [MFC], OnGlobalFontsChanged
- CMFCToolBarDateTimeCtrl [MFC], OnMove
- CMFCToolBarDateTimeCtrl [MFC], OnShow
- CMFCToolBarDateTimeCtrl [MFC], OnUpdateToolTip
- CMFCToolBarDateTimeCtrl [MFC], SetTime
- CMFCToolBarDateTimeCtrl [MFC], SetTimeAll
ms.assetid: a3853cb9-8ebc-444f-a1e4-9cf905e24c18
ms.openlocfilehash: 9aebd55f19a6687554d8d8378ef84ed5932025a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372173"
---
# <a name="cmfctoolbardatetimectrl-class"></a>CMFCToolBarDateTimeCtrl クラス

日時指定コントロールを含むツール バー ボタン。

## <a name="syntax"></a>構文

```
class CMFCToolBarDateTimeCtrl : public CMFCToolBarButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ウィンドウズツール バーの日付](#cmfctoolbardatetimectrl)|`CMFCToolBarDateTimeCtrl` オブジェクトを構築します。|
|`CMFCToolBarDateTimeCtrl::~CMFCToolBarDateTimeCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCツールバーデイトタイムCtrl::缶詰ストレッチ](#canbestretched)|ユーザーがカスタマイズ中にボタンを伸張できるかどうかを指定します。 [(CMFCツールバーボタンをオーバーライドします。:缶詰ストレッチ](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched).)|
|[ウィンドウズバーの日付を指定します。](#copyfrom)|別のツール バー ボタンのプロパティを現在のボタンにコピーします。 [(CMFCツールバーボタンをオーバーライドします。.](../../mfc/reference/cmfctoolbarbutton-class.md#copyfrom)|
|`CMFCToolBarDateTimeCtrl::DuplicateData`|将来利用するために予約されています。|
|[メニューボタンをクリックします。](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)|ツールバー ボタンからメニューにテキストをコピーします。|
|`CMFCToolBarDateTimeCtrl::CreateObject`|このクラス型の動的インスタンスを作成するために、フレームワークで使用されます。|
|[ウィンドウズバーバーデートタイムCtrl::ゲットバイコマンド](#getbycmd)|指定したコマンド`CMFCToolBarDateTimeCtrl`ID を持つアプリケーション内の最初のオブジェクトを取得します。|
|[ウィンドウズバーの日付を指定します。](#getdatetimectrl)|日時指定コントロールへのポインターを返します。|
|[ウィンドウズバー](#gethwnd)|ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。 [(CMFCツールバーボタンをオーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)|
|`CMFCToolBarDateTimeCtrl::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[ウィンドウズバーの日付を指定します。](#gettime)|選択した時刻を日時指定コントロールから取得し、指定した[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体に配置します。|
|[ウィンドウズバーバーデートタイムCtrl::ゲットタイムオール](#gettimeall)|指定したコマンド ID を持つタイム ピッカー コントロール ボタンから選択した時刻を返します。|
|[ウィンドウズツールバーデイトタイムCtrl::フトボーダー](#havehotborder)|ユーザーがボタンを選択したときにボタンの境界線を表示するかどうかを指定します。 [(CMFCツールバーボタンをオーバーライドします::フアホボーダー](../../mfc/reference/cmfctoolbarbutton-class.md#havehotborder).)|
|[コマンドを通知します。](#notifycommand)|ボタンが[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを処理するかどうかを指定します。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)|
|[ウィンドウズバーの日付を表示します。](#onaddtocustomizepage)|ボタンが **[カスタマイズ**] ダイアログ ボックスに追加されたときに、フレームワークによって呼び出されます。 (CMFC ツールバー ボタンをオーバーライド[します。:アドオンをカスタマイズページ](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage).)|
|`CMFCToolBarDateTimeCtrl::OnCalculateSize`|指定したデバイス コンテキストとドッキング状態のボタンのサイズを計算するために、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします::計算サイズ](../../mfc/reference/cmfctoolbarbutton-class.md#oncalculatesize).)|
|[ウィンドウズバーの日付を指定します。](#onchangeparentwnd)|ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::オンチェンジペアレントウンド](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd).)|
|[クリック時](#onclick)|ユーザーがコントロールをクリックしたときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:クリック時](../../mfc/reference/cmfctoolbarbutton-class.md#onclick).)|
|[ウィンドウズバーの日付を指定します。](#onctlcolor)|親ツール バーがWM_CTLCOLOR メッセージを処理するときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)|
|`CMFCToolBarDateTimeCtrl::OnDraw`|指定したスタイルとオプションを使用してボタンを描画するために、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::OnDraw](../../mfc/reference/cmfctoolbarbutton-class.md#ondraw).)|
|`CMFCToolBarDateTimeCtrl::OnDrawOnCustomizeList`|[**カスタマイズ**] ダイアログ ボックスの **[コマンド**] ウィンドウにボタンを描画するために、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#ondrawoncustomizelist)|
|[変更されたグローバルフォント](#onglobalfontschanged)|グローバル フォントが変更されたときに、フレームワークによって呼び出されます。 ([オーバーライドします。](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)|
|[ウィンドウズバーバーデイトタイムCtrl::オンムーブ](#onmove)|親ツール バーが移動したときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:オンムーブ](../../mfc/reference/cmfctoolbarbutton-class.md#onmove).)|
|[ウィンドウズバー](#onshow)|ボタンが表示または非表示になったときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします::オンショー](../../mfc/reference/cmfctoolbarbutton-class.md#onshow).)|
|`CMFCToolBarDateTimeCtrl::OnSize`|親ツール バーのサイズまたは位置が変更され、この変更によってボタンのサイズが変更されたときに、フレームワークによって呼び出されます。 [(CMFCツールバーボタンをオーバーライドします。:オンサイズ](../../mfc/reference/cmfctoolbarbutton-class.md#onsize).)|
|[ツール ヒントをクリックします。](#onupdatetooltip)|親ツール バーがツールヒント テキストを更新するときに、フレームワークによって呼び出されます。 (オーバーライド[CMFCツールバーボタン::オンアップデートツールチップ](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip).)|
|`CMFCToolBarDateTimeCtrl::Serialize`|このオブジェクトをアーカイブから読み取るか、アーカイブに書き込みます[(CMFCToolBarButton::Serialize](../../mfc/reference/cmfctoolbarbutton-class.md#serialize).)|
|`CMFCToolBarDateTimeCtrl::SetStyle`|ツール バー ボタンのスタイルを設定します。 (オーバーライド[CMFCツールバーボタン::セットスタイル](../../mfc/reference/cmfctoolbarbutton-class.md#setstyle).)|
|[ウィンドウズバーの日付を指定します。](#settime)|時刻指定コントロールの時刻と日付を設定します。|
|[ウィンドウズバーの日付を指定します。](#settimeall)|指定したコマンド ID を持つタイム ピッカー コントロールのすべてのインスタンスで、時刻と日付を設定します。|

## <a name="remarks"></a>解説

日付と時刻の選択コントロールを使用する方法の例については、サンプル プロジェクトを参照してください。 コントロール ボタンをツール バーに追加する方法については、「[チュートリアル : ツールバーにコントロールを配置](../../mfc/walkthrough-putting-controls-on-toolbars.md)する 」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[ウィンドウズバー](../../mfc/reference/cmfctoolbardatetimectrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールバー日時ctrl.h

## <a name="cmfctoolbardatetimectrlcanbestretched"></a><a name="canbestretched"></a>CMFCツールバーデイトタイムCtrl::缶詰ストレッチ

ユーザーがカスタマイズ中にボタンを伸張できるかどうかを指定します。

```
virtual BOOL CanBeStretched() const;
```

### <a name="return-value"></a>戻り値

このメソッドは TRUE を返します。

### <a name="remarks"></a>解説

既定では、フレームワークでは、ユーザーがカスタマイズ中にツール バー ボタンを伸ばすことを許可しません。 このメソッドは、カスタマイズ中にユーザーが日付と時刻のツール バー ボタンを伸ばすことができるようにして、基本クラスの実装 ( [CMFCToolBarButton::CanBeStretch](../../mfc/reference/cmfctoolbarbutton-class.md#canbestretched)) を拡張します。

## <a name="cmfctoolbardatetimectrlcmfctoolbardatetimectrl"></a><a name="cmfctoolbardatetimectrl"></a>ウィンドウズツール バーの日付

[オブジェクトを](../../mfc/reference/cmfctoolbardatetimectrl-class.md)作成して初期化します。

```
CMFCToolBarDateTimeCtrl(
    UINT uiID,
    int iImage,
    DWORD dwStyle=0,
    int iWidth=0);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]コントロール ID。

*iイメージ*<br/>
[in]ツール バーのオブジェクト内のイメージの`CMFCToolBarImages`インデックス。

*Dwstyle*<br/>
[in]ユーザーがボタンを`CMFCToolBarDateTimeCtrlImpl`クリックしたときに作成されるウィンドウのスタイル。

*幅*<br/>
[in]コントロールの幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このオブジェクトは、システムの日付と時刻に初期化されます。 内部`CMFCToolBarDateTimeCtrlImpl`オブジェクトのウィンドウ スタイルには *、dwStyle*パラメータ、WS_CHILDスタイル、およびWS_VISIBLEスタイルが含まれます。 これらのスタイルは、 を使用`CMFCToolBarDateTimeCtrl::SetStyle`して変更することはできません。 コントロールのスタイルを変更するために使用`SetStyle`します。 `CMFCToolBarDateTimeCtrl`

### <a name="example"></a>例

クラスのオブジェクトを構築する方法を次の例に`CMFCToolBarDateTimeCtrl`示します。 このコード スニペットは、[ツールバーの日付時刻の選択のサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_ToolbarDateTimePicker#1](../../mfc/reference/codesnippet/cpp/cmfctoolbardatetimectrl-class_1.cpp)]

## <a name="cmfctoolbardatetimectrlcopyfrom"></a><a name="copyfrom"></a>ウィンドウズバーの日付を指定します。

別のツール バー ボタンのプロパティを現在のボタンにコピーします。

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>パラメーター

*src*<br/>
[in]コピー元のボタンへの参照。

### <a name="remarks"></a>解説

このツール バー ボタンに別のツール バー ボタンをコピーします。 *src*は 型`CMFCToolBarDateTimeCtrl`でなければなりません。

## <a name="cmfctoolbardatetimectrlexporttomenubutton"></a><a name="exporttomenubutton"></a>メニューボタンをクリックします。

ツールバー ボタンからメニューにテキストをコピーします。

```
virtual BOOL ExportToMenuButton(CMFCToolBarMenuButton& menuButton) const;
```

### <a name="parameters"></a>パラメーター

*メニューボタン*<br/>
[in]ターゲット メニュー ボタンへの参照。

### <a name="return-value"></a>戻り値

このメソッドは TRUE を返します。

### <a name="remarks"></a>解説

このメソッドは、コントロールのコマンド ID に関連付けられている文字列リソースを読み込むことによって、基本クラスの実装 ( [CMFCToolBarButton::ExportToMenuButton](../../mfc/reference/cmfctoolbarbutton-class.md#exporttomenubutton)) をオーバーライドします。 文字列リソースの詳細については[、「CStringT::ロード文字列](../../atl-mfc-shared/reference/cstringt-class.md#loadstring)」を参照してください。

## <a name="cmfctoolbardatetimectrlgetbycmd"></a><a name="getbycmd"></a>ウィンドウズバーバーデートタイムCtrl::ゲットバイコマンド

指定したコマンド`CMFCToolBarDateTimeCtrl`ID を持つアプリケーション内の最初のオブジェクトを取得します。

```
static CMFCToolBarDateTimeCtrl* __stdcall GetByCmd(UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]取得するボタンのコマンド ID。

### <a name="return-value"></a>戻り値

指定した`CMFCToolBarDateTimeCtrl`コマンド ID を持つアプリケーション内の最初の`CMFCToolBarDateTimeCtrl`オブジェクト。

### <a name="remarks"></a>解説

この共有ユーティリティ メソッドは、指定されたコマンド ID を持つタイム ピッカー コントロールのすべてのインスタンスの時刻と日付を設定または取得するために[、CMFCToolBarDateTimeCtrl::SetTimeAll](#settimeall)および[CMFCToolBarDateTimeCtrl::GetTimeAll](#gettimeall)などのメソッドによって使用されます。

## <a name="cmfctoolbardatetimectrlgetdatetimectrl"></a><a name="getdatetimectrl"></a>ウィンドウズバーの日付を指定します。

日時指定コントロールへのポインターを返します。

```
CDateTimeCtrl* GetDateTimeCtrl() const;
```

### <a name="return-value"></a>戻り値

日時指定コントロールへのポインター。コントロールが存在しない場合は NULL。

### <a name="remarks"></a>解説

クラス`CMFCToolBarDateTimeCtrl`は、ツール`m_pWndDateTime`バーに`CMFCToolBarDateTimeCtrl`オブジェクトを挿入するときにデータ メンバーを初期化します。

## <a name="cmfctoolbardatetimectrlgethwnd"></a><a name="gethwnd"></a>ウィンドウズバー

ツール バー ボタンに関連付けられているウィンドウ ハンドルを取得します。

```
virtual HWND GetHwnd();
```

### <a name="return-value"></a>戻り値

日付と時刻のツール バー ボタンに関連付けられているウィンドウ ハンドル。

### <a name="remarks"></a>解説

このメソッドは、[メソッド](../../mfc/reference/cmfctoolbarbutton-class.md#gethwnd)をオーバーライドします。

## <a name="cmfctoolbardatetimectrlgettime"></a><a name="gettime"></a>ウィンドウズバーの日付を指定します。

関連付けられた日時指定コントロールから選択した時刻を取得し、指定した[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体に配置します。

```
BOOL GetTime(COleDateTime& timeDest) const;
DWORD GetTime(CTime& timeDest) const;
DWORD GetTime(LPSYSTEMTIME pTimeDest) const;
```

### <a name="parameters"></a>パラメーター

*タイムデスト*<br/>
[アウト]最初のオーバーロードでは、システム時刻情報を受け取る[COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。 2 番目のオーバーロードでは、システム時刻情報を受け取る[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。

*最も多い*<br/>
[アウト]システム時刻情報を受け取る[システム時間](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。 NULL にすることはできません。

### <a name="return-value"></a>戻り値

最初のオーバーロードでは[、COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトに時刻が正常に書き込まれた場合は 0 以外の値を返します。それ以外の場合は 0。 2 番目と 3 番目のオーバーロードでは、戻り値は[、NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange)構造体に設定された dwFlag メンバーと等しい DWORD です。

### <a name="remarks"></a>解説

このメソッドは、日付と時刻の選択が日時に設定されているかどうかを示す[NMDATETIMECHANGE](/windows/win32/api/commctrl/ns-commctrl-nmdatetimechange)構造体メンバー dwFlags を設定します。 値がGDT_NONEに等しい場合、コントロールは status`no date`に設定され、DTS_SHOWNONEスタイルが使用されます。 返される値がGDT_VALIDに等しい場合、システム時刻は正常にデスティネーションロケーションに保存されます。

## <a name="cmfctoolbardatetimectrlgettimeall"></a><a name="gettimeall"></a>ウィンドウズバーバーデートタイムCtrl::ゲットタイムオール

指定したコマンド ID を持つタイム ピッカー コントロール ボタンからユーザーが選択した時刻を返します。

```
static BOOL GetTimeAll(
    UINT uiCmd,
    COleDateTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    CTime& timeDest);

static DWORD GetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeDest);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]ツール バー ボタンのコマンド ID を指定します。

*タイムデスト*<br/>
[アウト]最初のオーバーロードでは、システム時刻情報を受け取る[COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。 2 番目のオーバーロードでは、システム時刻情報を受け取る[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクト。

*最も多い*<br/>
[アウト]システム時刻情報を受け取る[システム時間](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。 NULL にすることはできません。

### <a name="return-value"></a>戻り値

フレームワークがコマンド ID *uiCmd*に一致するツール バー ボタンを見つけられない場合、戻り値は最初のオーバーロードでは 0 になり、他のオーバーロードではGDT_NONE。 ツール バー ボタンが見つかった場合、戻り値は[、その](#gettime)ボタンの呼び出しからの戻り値と同じです。 戻り値 0 または GDT_NONE は、ボタンが見つかったときに発生する`GetTime`可能性があります。

### <a name="remarks"></a>解説

このメソッドは、指定されたコマンド ID を持つツール バー ボタンを検索し、そのボタンの[メソッドを呼び出します](#gettime)。

## <a name="cmfctoolbardatetimectrlhavehotborder"></a><a name="havehotborder"></a>ウィンドウズツールバーデイトタイムCtrl::フトボーダー

ユーザーがボタンを選択したときにボタンの境界線を表示するかどうかを指定します。

```
virtual BOOL HaveHotBorder() const;
```

### <a name="return-value"></a>戻り値

ボタンが選択されているときに境界線を表示する場合は 0 以外の値を指定します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、コントロールが表示されている場合は 0 以外の値を返します。

## <a name="cmfctoolbardatetimectrlnotifycommand"></a><a name="notifycommand"></a>コマンドを通知します。

ボタンが[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを処理するかどうかを指定します。

```
virtual BOOL NotifyCommand(int iNotifyCode);
```

### <a name="parameters"></a>パラメーター

*コード*<br/>
[in]コマンドに関連付けられている通知メッセージ。

### <a name="return-value"></a>戻り値

ボタンがWM_COMMAND メッセージを処理する場合は TRUE、親ツール バーによってメッセージを処理することを示す FALSE。

### <a name="remarks"></a>解説

フレームワークは、親ウィンドウに[WM_COMMAND](/windows/win32/menurc/wm-command)メッセージを送信する際に、このメソッドを呼び出します。

このメソッドは[、DTN_DATETIMECHANGE](/windows/win32/Controls/dtn-datetimechange)通知を処理することによって基本クラスの実装 ( [CMFCToolBarButton::NotifyCommand](../../mfc/reference/cmfctoolbarbutton-class.md#notifycommand)) を拡張します。 内部時刻ステータスを更新し、同じコマンド ID`CMFCToolBarDateTimeCtrl`を持つすべてのオブジェクトの time プロパティを更新します。

## <a name="cmfctoolbardatetimectrlonaddtocustomizepage"></a><a name="onaddtocustomizepage"></a>ウィンドウズバーの日付を表示します。

ボタンが **[カスタマイズ**] ダイアログ ボックスに追加されたときに、フレームワークによって呼び出されます。

```
virtual void OnAddToCustomizePage();
```

### <a name="remarks"></a>解説

このメソッドは、このオブジェクトと同じコマンド ID を持つツール バーの最初の日付と時刻コントロールからプロパティをコピーすることで、基本クラスの実装[CMFCToolBarButton::OnAddToCustomizePage](../../mfc/reference/cmfctoolbarbutton-class.md#onaddtocustomizepage)を拡張します。 このメソッドは、このオブジェクトと同じコマンド ID を持つ日付と時刻のコントロールを持つツール バーがない場合、何も実行しません。

**[カスタマイズ**] ダイアログ ボックスの詳細については、「 [CMFCToolBarsCustomizeDialog クラス](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)」を参照してください。

## <a name="cmfctoolbardatetimectrlonchangeparentwnd"></a><a name="onchangeparentwnd"></a>ウィンドウズバーの日付を指定します。

ボタンが新しいツール バーに挿入されたときに、フレームワークによって呼び出されます。

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]新しい親ウィンドウ。

### <a name="remarks"></a>解説

このメソッドは、内部`CMFCToolBarDateTimeCtrlImpl`オブジェクトを再作成することによって、基本クラスの実装 ( [CMFCToolBarButton::OnChangeParentWnd](../../mfc/reference/cmfctoolbarbutton-class.md#onchangeparentwnd)) をオーバーライドします。

## <a name="cmfctoolbardatetimectrlonclick"></a><a name="onclick"></a>クリック時

ユーザーがコントロールをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClick(
    CWnd* pWnd,
    BOOL bDelay = TRUE);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
[in]未使用。

*bディレイ*<br/>
[in]未使用。

### <a name="return-value"></a>戻り値

ボタンがクリック メッセージを処理する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、内部`CMFCToolBarDateTimeCtrlImpl`オブジェクトが表示されている場合は 0 以外の値を返すことによって、基本クラスの実装[CMFCToolBarButton::OnClick](../../mfc/reference/cmfctoolbarbutton-class.md#onclick)をオーバーライドします。

## <a name="cmfctoolbardatetimectrlonctlcolor"></a><a name="onctlcolor"></a>ウィンドウズバーの日付を指定します。

親ツール バーがWM_CTLCOLOR メッセージを処理するときに、フレームワークによって呼び出されます。

```
virtual HBRUSH OnCtlColor(
    CDC* pDC,
    UINT nCtlColor);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンを表示するデバイス コンテキスト。

*をクリックします。*<br/>
[in]未使用。

### <a name="return-value"></a>戻り値

フレームワークがボタンの背景を描画するために使用するグローバル ブラシへのハンドル。

### <a name="remarks"></a>解説

このメソッドは、指定されたデバイス コンテキストのテキストと背景色をそれぞれグローバル テキストと背景色に設定することで、基本クラスの実装[CMFCToolBarButton::OnCtlColor](../../mfc/reference/cmfctoolbarbutton-class.md#onctlcolor)をオーバーライドします。

アプリケーションで使用できるグローバル オプションの詳細については、「 [AFX_GLOBAL_DATAの構造](../../mfc/reference/afx-global-data-structure.md)」を参照してください。

## <a name="cmfctoolbardatetimectrlonglobalfontschanged"></a><a name="onglobalfontschanged"></a>変更されたグローバルフォント

グローバル フォントが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnGlobalFontsChanged();
```

### <a name="remarks"></a>解説

このメソッドは、コントロールのフォントをグローバル フォントのフォントに変更することで、基本クラスの実装 ( [CMFCToolBarButton::OnGlobalFontsChanged](../../mfc/reference/cmfctoolbarbutton-class.md#onglobalfontschanged)) を拡張します。

アプリケーションで使用できるグローバル オプションの詳細については、「 [AFX_GLOBAL_DATAの構造](../../mfc/reference/afx-global-data-structure.md)」を参照してください。

## <a name="cmfctoolbardatetimectrlonmove"></a><a name="onmove"></a>ウィンドウズバーバーデイトタイムCtrl::オンムーブ

親ツール バーが移動したときに、フレームワークによって呼び出されます。

```
virtual void OnMove();
```

### <a name="remarks"></a>解説

このメソッドは、内部`CMFCToolBarDateTimeCtrlImpl`オブジェクトの位置を更新することによって、既定のクラスの実装 ( [CMFCToolBarButton::OnMove](../../mfc/reference/cmfctoolbarbutton-class.md#onmove)) をオーバーライドします。

## <a name="cmfctoolbardatetimectrlonshow"></a><a name="onshow"></a>ウィンドウズバー

ボタンが表示または非表示になったときに、フレームワークによって呼び出されます。

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>パラメーター

*bショー*<br/>
[in]ボタンを表示するかどうかを指定します。 このパラメーターが TRUE の場合、ボタンは表示されます。 それ以外の場合、ボタンは表示されません。

### <a name="remarks"></a>解説

このメソッドは *、bShow*が TRUE の場合はボタンを表示することによって、基本クラスの実装を拡張します ( [CMFCToolBarButton::OnShow](../../mfc/reference/cmfctoolbarbutton-class.md#onshow)) 。 それ以外の場合、このメソッドはボタンを非表示にします。

## <a name="cmfctoolbardatetimectrlonsize"></a><a name="onsize"></a>ウィンドウズバーの日付を指定します。

親ツール バーのサイズまたは位置が変更され、この変更によってボタンのサイズが変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnSize(int iSize);
```

### <a name="parameters"></a>パラメーター

*iサイズ*<br/>
[in]ボタンの新しい幅 (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、内部`CMFCToolBarDateTimeCtrlImpl`オブジェクトのサイズと位置を更新することによって、既定のクラスの実装 ( [CMFCToolBarButton::OnSize](../../mfc/reference/cmfctoolbarbutton-class.md#onsize)) をオーバーライドします。

## <a name="cmfctoolbardatetimectrlonupdatetooltip"></a><a name="onupdatetooltip"></a>ツール ヒントをクリックします。

親ツール バーがツールヒント テキストを更新するときに、フレームワークによって呼び出されます。

```
virtual BOOL OnUpdateToolTip(
    CWnd* pWndParent,
    int iButtonIndex,
    CToolTipCtrl& wndToolTip,
    CString& str);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]親ウィンドウ。

*ボタンインデックス*<br/>
[in]親ボタン コレクション内のボタンの 0 から始まるインデックス。

*wnd ツールヒント*<br/>
[in]ツールヒント テキストを表示するコントロール。

*Str*<br/>
[アウト]更新`CString`されたツールヒント テキストを受け取るオブジェクト。

### <a name="return-value"></a>戻り値

メソッドがツールヒント テキストを更新する場合は 0 以外の値を返します。それ以外の場合は 0。

### <a name="remarks"></a>解説

このメソッドは、ボタンに関連付けられているツールヒント テキストを表示することによって、基本クラスの実装 ( [CMFCToolBarButton::OnUpdateToolTip](../../mfc/reference/cmfctoolbarbutton-class.md#onupdatetooltip)) を拡張します。 ボタンが水平方向にドッキングされていない場合、このメソッドは何も実行せず、FALSE を返します。

## <a name="cmfctoolbardatetimectrlsettime"></a><a name="settime"></a>ウィンドウズバーの日付を指定します。

時刻指定コントロールの時刻と日付を設定します。

```
BOOL SetTime(const COleDateTime& timeNew);
BOOL SetTime(const CTime* timeNew);
BOOL SetTime(LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>パラメーター

*時間新しい*<br/>
[in]最初のバージョンでは、コントロールが設定される時刻を含む[COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクトへの参照。 2 番目のバージョンでは、コントロールが設定される時刻を含む[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへのポインター。

*新しい時間*<br/>
[in]コントロールが設定される時刻を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

日付と時刻の選択コントロールの時刻を設定するには[、CDateTimeCtrl::SetTime](../../mfc/reference/cdatetimectrl-class.md#settime)を呼び出します。

## <a name="cmfctoolbardatetimectrlsettimeall"></a><a name="settimeall"></a>ウィンドウズバーの日付を指定します。

指定したコマンド ID を持つタイム ピッカー コントロールのすべてのインスタンスで、時刻と日付を設定します。

```
static BOOL SetTimeAll(
    UINT uiCmd,
    const COleDateTime& timeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    const CTime* pTimeNew);

static BOOL SetTimeAll(
    UINT uiCmd,
    LPSYSTEMTIME pTimeNew=NULL);
```

### <a name="parameters"></a>パラメーター

*Uicmd*<br/>
[in]ツール バー ボタンのコマンド ID を指定します。

*時間新しい*<br/>
[in]最初のバージョンでは、コントロールが設定される時刻を含む[COleDateTime クラス](../../atl-mfc-shared/reference/coledatetime-class.md)オブジェクト。 2 番目のバージョンでは、コントロールが設定される時刻を含む[CTime](../../atl-mfc-shared/reference/ctime-class.md)オブジェクトへのポインター。

*新しい時間*<br/>
[in]コントロールが設定される時刻を含む[SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime)構造体へのポインター。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

指定したコマンド ID を持つツール バー ボタンを検索し[、CMFCToolBarDateTimeCtrl::SetTime](#settime)を呼び出すことによって、日時の選択コントロールに時刻を設定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)
