---
title: CMFCDesktopAlertWnd Class
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::Create
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetCaptionHeight
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetDialogSize
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetLastPos
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::GetTransparency
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::HasSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnBeforeShow
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnClickLinkButton
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::OnDraw
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::ProcessCommand
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationSpeed
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAnimationType
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetAutoCloseTime
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetSmallCaption
- AFXDESKTOPALERTWND/CMFCDesktopAlertWnd::SetTransparency
helpviewer_keywords:
- CMFCDesktopAlertWnd [MFC], Create
- CMFCDesktopAlertWnd [MFC], GetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], GetAnimationType
- CMFCDesktopAlertWnd [MFC], GetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], GetCaptionHeight
- CMFCDesktopAlertWnd [MFC], GetDialogSize
- CMFCDesktopAlertWnd [MFC], GetLastPos
- CMFCDesktopAlertWnd [MFC], GetTransparency
- CMFCDesktopAlertWnd [MFC], HasSmallCaption
- CMFCDesktopAlertWnd [MFC], OnBeforeShow
- CMFCDesktopAlertWnd [MFC], OnClickLinkButton
- CMFCDesktopAlertWnd [MFC], OnCommand
- CMFCDesktopAlertWnd [MFC], OnDraw
- CMFCDesktopAlertWnd [MFC], ProcessCommand
- CMFCDesktopAlertWnd [MFC], SetAnimationSpeed
- CMFCDesktopAlertWnd [MFC], SetAnimationType
- CMFCDesktopAlertWnd [MFC], SetAutoCloseTime
- CMFCDesktopAlertWnd [MFC], SetSmallCaption
- CMFCDesktopAlertWnd [MFC], SetTransparency
ms.assetid: 73a2dd7b-ea84-4ae2-9830-7cf6e8dd2425
ms.openlocfilehash: cf453b6e69f012bedaf0bd91b5eaf11f7caffa12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752449"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class

この`CMFCDesktopAlertWnd`クラスは、イベントをユーザーに通知するために画面に表示されるモードレス ダイアログ ボックスの機能を実装します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#create)|デスクトップ通知ウィンドウを作成および初期化します。|
|[をクリックします。](#getanimationspeed)|アニメーションの速度を返します。|
|[次のコマンドを実行します。](#getanimationtype)|アニメーションの種類を返します。|
|[をクリックします。](#getautoclosetime)|自動終了タイムアウトを返します。|
|[ウィンドウの種類::キャプションの高さ](#getcaptionheight)|キャプションの高さを返します。|
|[ウィンドウの種類::取得ダイアログ サイズ](#getdialogsize)||
|[をクリックします。](#getlastpos)|画面上のデスクトップ通知ウィンドウの最後の有効な位置を返します。|
|[を取得します。](#gettransparency)|透明度レベルを返します。|
|[ウィンドウの種類::小さなキャプション](#hassmallcaption)|デスクトップ通知ウィンドウを小さいキャプションで表示するかどうかを指定します。|
|[ショーの前に次のメッセージが表示されます。](#onbeforeshow)||
|[ウィンドウの種類::クリックリンクボタン](#onclicklinkbutton)|ユーザーがデスクトップ通知メニューにあるリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。|
|[を切り取った](#oncommand)|フレームワークは、ユーザーがメニューから項目を選択したとき、子コントロールが通知メッセージを送信するとき、またはアクセラレータ キーストロークが変換されたときに、このメンバー関数を呼び出します。 [(CWnd をオーバーライドします::コマンドの実行](../../mfc/reference/cwnd-class.md#oncommand)|
|[を切り取る](#ondraw)||
|[を:Pロセスコマンド](#processcommand)||
|[を設定します。](#setanimationspeed)|新しいアニメーション速度を設定します。|
|[を切り取る::アニメーションタイプを設定します。](#setanimationtype)|アニメーションの種類を設定します。|
|[を切り取る::自動閉じる時間を設定します。](#setautoclosetime)|自動クローズ タイムアウトを設定します。|
|[ウィンドウの種類::セットスモールキャプション](#setsmallcaption)|小さいキャプションと標準キャプションを切り替えます。|
|[を切り取る::透過性を設定します。](#settransparency)|透明度レベルを設定します。|

## <a name="remarks"></a>解説

デスクトップ通知ウィンドウは、透明にすることができ、アニメーション効果で表示され、(指定した遅延の後、またはユーザーが閉じるボタンをクリックして閉じたときに)消える可能性があります。

デスクトップ通知ウィンドウには、アイコン、メッセージ テキスト (ラベル)、およびリンクを含む既定のダイアログ ボックスを含めることもできます。 または、デスクトップ通知ウィンドウにアプリケーションのリソースからのカスタム ダイアログを含めることができます。

デスクトップ通知ウィンドウは、2 つの手順で作成します。 まず、コンストラクタを呼び出して`CMFCDesktopAlertWnd`オブジェクトを構築します。 次に[、CMFCDesktopAlertWnd::メンバー](#create)関数を呼び出してウィンドウを作成し、`CMFCDesktopAlertWnd`オブジェクトにアタッチします。

この`CMFCDesktopAlertWnd`オブジェクトは、デスクトップ通知ウィンドウのクライアント領域を埋める特別な子ダイアログ ボックスを作成します。 ダイアログボックスは、その上に配置されているすべてのコントロールを所有します。

ポップアップ ウィンドウにカスタム ダイアログ ボックスを表示するには、次の手順を実行します。

1. `CMFCDesktopAlertDialog` の派生クラスを作成します。

1. リソースに子ダイアログ ボックス テンプレートを作成します。

1. 呼び出し[CMFCDesktopAlertWnd::](#create)ダイアログ ボックス テンプレートのリソース ID と派生クラスのランタイム クラス情報へのポインターを使用して作成します。

1. ホストされたコントロールから送信されるすべての通知を処理するようにカスタム ダイアログ ボックスをプログラムするか、ホストされたコントロールがこれらの通知を直接処理するようにプログラムします。

デスクトップ通知ウィンドウの動作を制御するには、次の関数を使用します。

- を呼び出すことによってアニメーションの種類[を設定します](#setanimationtype)。 有効なオプションには、展開、スライド、フェードがあります。

- アニメーション フレームの速度を設定するには[、CMFCDesktopAlertWnd:::アニメーションスピードを呼び](#setanimationspeed)出します。

- を呼び出すことによって、透過性[レベルを設定します](#settransparency)。

- キャプションのサイズを小さくに変更するには[、CMFCDesktopAlertWnd::SetSmallCaption](#setsmallcaption)を呼び出します。 小さいキャプションは高さ 7 ピクセルです。

## <a name="example"></a>例

次の例は、クラスのさまざまなメソッドを使用してオブジェクト`CMFCDesktopAlertWnd`を構成する方法`CMFCDesktopAlertWnd`を示しています。 この例では、アニメーションの種類の設定、ポップアップ ウィンドウの透過表示の設定、警告ウィンドウに小さなキャプションの表示を指定する方法、および警告ウィンドウが自動的に閉じるまでの時間を設定する方法を示します。 この例では、デスクトップ通知ウィンドウを作成して初期化する方法も示します。 このコード スニペットは[、デスクトップ警告デモのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxDesktop アラート Wnd.h

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a>をクリックします。

デスクトップ通知ウィンドウを作成および初期化します。

```
virtual BOOL Create(
    CWnd* pWndOwner,
    UINT uiDlgResID,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1),
    CRuntimeClass* pRTIDlgBar = RUNTIME_CLASS(CMFCDesktopAlertDialog));

virtual BOOL Create(
    CWnd* pWndOwner,
    CMFCDesktopAlertWndInfo& params,
    HMENU hMenu = NULL,
    CPoint ptPos = CPoint(-1,-1));
```

### <a name="parameters"></a>パラメーター

*オーナー*<br/>
[イン、アウト]警告ウィンドウの所有者を指定します。 その所有者は、デスクトップ通知ウィンドウのすべての通知を受信します。 この値を NULL にすることはできません。

*ウイドグルレスID*<br/>
[in]警告ウィンドウのリソース ID を指定します。

*Hmenu*<br/>
[in]ユーザーがメニュー ボタンをクリックしたときに表示されるメニューを指定します。 NULL の場合、メニュー ボタンは表示されません。

*ptPos*<br/>
[in]画面座標を使用して、警告ウィンドウが表示される初期位置を指定します。 このパラメーターが (-1, -1) の場合は、画面の右下隅に警告ウィンドウが表示されます。

*バール*<br/>
[in]通知ウィンドウのクライアント領域をカバーするカスタム ダイアログ ボックス クラスのランタイム クラス情報。

*params*<br/>
[in]警告ウィンドウの作成に使用するパラメータを指定します。

### <a name="return-value"></a>戻り値

警告ウィンドウが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを呼び出して、警告ウィンドウを作成します。 警告ウィンドウのクライアント領域には、ユーザーに表示されるすべてのコントロールをホストする子ダイアログ ボックスが含まれています。

1 つ目のメソッド オーバーロードは、アプリケーションのリソースから読み込まれる子ダイアログ ボックスを含む警告ウィンドウを作成します。 最初のメソッド オーバーロードでは、カスタム ダイアログ ボックス クラスのランタイム クラス情報を指定することもできます。

2 番目のメソッド オーバーロードは、既定のコントロールを含む警告ウィンドウを作成します。 表示するコントロールを指定するには、[クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)を変更します。

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a>をクリックします。

アニメーションの速度を返します。

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>戻り値

警告ウィンドウのアニメーション速度 (ミリ秒単位)。

### <a name="remarks"></a>解説

アニメーション速度は、警告ウィンドウの開閉速度を示します。

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a>次のコマンドを実行します。

アニメーションの種類を返します。

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>戻り値

次のいずれかのアニメーションの種類。

- NO_ANIMATION

- 展開

- スライド

- フェード

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a>をクリックします。

自動終了タイムアウトを返します。

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>戻り値

警告ウィンドウが自動的に閉じるまでの時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

このメソッドを使用して、警告ウィンドウが自動的に閉じるまでの時間を決定します。

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a>ウィンドウの種類::キャプションの高さ

キャプションの高さを返します。

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>戻り値

キャプションの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、派生クラスでオーバーライドできます。 ポップアップ ウィンドウに小さいキャプションが表示される場合は、小さいキャプションの高さ (7 ピクセル) を返すか、または Windows API`GetSystemMetrics(SM_CYSMCAPTION)`関数から取得した値を既定の実装で返します。

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a>をクリックします。

画面のデスクトップ通知ウィンドウの最後の位置を返します。

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>戻り値

画面座標で示した点。

### <a name="remarks"></a>解説

このメソッドは、画面上の警告ウィンドウの最後の有効な位置を返します。

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a>を取得します。

透明度レベルを返します。

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>戻り値

0 ~ 255 の透明度レベル。. 値が大きいほど、ウィンドウは不透明になります。

### <a name="remarks"></a>解説

このメソッドは、警告ウィンドウの現在の透過性レベルを取得するために使います。

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a>ウィンドウの種類::小さなキャプション

デスクトップ通知ウィンドウに小さいキャプションまたは標準サイズのキャプションがあるかどうかを指定します。

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>戻り値

ポップアップ ウィンドウが小さいキャプションで表示される場合は TRUE。ポップアップ ウィンドウが標準サイズのキャプション付きで表示される場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、ポップアップ ウィンドウに小さいキャプションまたは標準サイズのキャプションがあるかどうかを判断するために使います。 既定では、小さいキャプションは 7 ピクセルの高さです。 通常サイズのキャプションの高さは、 Windows API 関数`GetSystemMetrics(SM_CYCAPTION)`を呼び出すことで取得できます。

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a>ショーの前に次のメッセージが表示されます。

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>パラメーター

[in]*CPoint&*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a>ウィンドウの種類::クリックリンクボタン

ユーザーがデスクトップ通知メニューにあるリンク ボタンをクリックしたときに、フレームワークによって呼び出されます。

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>パラメーター

*UICmdID*<br/>
[in]このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

常に FALSE です。

### <a name="remarks"></a>解説

ユーザーが通知ウィンドウのリンクをクリックしたときに通知を受け取る場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a>を切り取った

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

[in]*wパラム*<br/>

[in]*lパラム*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a>を切り取る

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a>を:Pロセスコマンド

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>パラメーター

[in]*hwnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a>を設定します。

新しいアニメーション速度を設定します。

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>パラメーター

*nスピード*<br/>
[in]新しいアニメーション速度をミリ秒単位で指定します。

### <a name="remarks"></a>解説

警告ウィンドウのアニメーション速度を設定します。 既定のアニメーション速度は 30 ミリ秒です。

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a>を切り取る::アニメーションタイプを設定します。

アニメーションの種類を設定します。

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>パラメーター

*type*<br/>
[in]アニメーションの種類を指定します。

### <a name="remarks"></a>解説

アニメーションの種類を設定します。 次のいずれかの値を指定できます。

- NO_ANIMATION

- 展開

- スライド

- フェード

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a>を切り取る::自動閉じる時間を設定します。

自動クローズ タイムアウトを設定します。

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>パラメーター

*n時間*<br/>
[in]警告ウィンドウが自動的に閉じるまでの時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

ユーザーがウィンドウを操作しない場合、指定した時間が経過すると、警告ウィンドウは自動的に閉じられます。

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a>ウィンドウの種類::セットスモールキャプション

小さいサイズと標準サイズのキャプションを切り替えます。

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>パラメーター

*小さなキャプション*<br/>
[in]警告ウィンドウに小さいキャプションを表示するように指定する場合は TRUE。それ以外の場合は FALSE を指定して、警告ウィンドウに標準サイズのキャプションを表示するように指定します。

### <a name="remarks"></a>解説

小さいサイズまたは標準サイズのキャプションを表示します。 既定では、小さいキャプションは 7 ピクセルの高さです。 通常のキャプションのサイズは、 Windows API 関数`GetSystemMetrics(SM_CYCAPTION)`を呼び出して取得できます。

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a>を切り取る::透過性を設定します。

ポップアップ ウィンドウの透明度レベルを設定します。

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>パラメーター

*n透明性*<br/>
[in]透明度レベルを指定します。 この値は 0 ~ 255 の範囲で指定する必要があります。 値が大きいほど、ウィンドウは不透明になります。

### <a name="remarks"></a>解説

ポップアップ ウィンドウの透明度レベルを設定します。

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a>ウィンドウの種類::取得ダイアログ サイズ

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)
