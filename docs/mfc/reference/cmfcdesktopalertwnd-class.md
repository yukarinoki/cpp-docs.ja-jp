---
description: '詳細情報: CMFCDesktopAlertWnd クラス'
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
ms.openlocfilehash: 45b75bdbd24a88a7eacff124bb07ac81e7703c31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330092"
---
# <a name="cmfcdesktopalertwnd-class"></a>CMFCDesktopAlertWnd Class

クラスは、 `CMFCDesktopAlertWnd` ユーザーにイベントについて通知するために画面に表示されるモードレスダイアログボックスの機能を実装します。

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCDesktopAlertWnd : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCDesktopAlertWnd:: Create](#create)|デスクトップの [警告] ウィンドウを作成して初期化します。|
|[CMFCDesktopAlertWnd:: Getアニメーション速度](#getanimationspeed)|アニメーションの速度を返します。|
|[CMFCDesktopAlertWnd:: Getアニメーションの種類](#getanimationtype)|アニメーションの種類を返します。|
|[CMFCDesktopAlertWnd:: GetAutoCloseTime](#getautoclosetime)|自動終了のタイムアウトを返します。|
|[CMFCDesktopAlertWnd:: GetCaptionHeight](#getcaptionheight)|キャプションの高さを返します。|
|[CMFCDesktopAlertWnd:: Get Size](#getdialogsize)||
|[CMFCDesktopAlertWnd:: GetLastPos](#getlastpos)|画面上のデスクトップ通知ウィンドウの最後の有効な位置を返します。|
|[CMFCDesktopAlertWnd:: GetTransparency](#gettransparency)|透明度を返します。|
|[CMFCDesktopAlertWnd:: HasSmallCaption](#hassmallcaption)|デスクトップアラートウィンドウを小さいキャプションと共に表示するかどうかを指定します。|
|[CMFCDesktopAlertWnd:: OnBeforeShow](#onbeforeshow)||
|[CMFCDesktopAlertWnd:: OnClickLinkButton](#onclicklinkbutton)|ユーザーがデスクトップの [警告] メニューにあるリンクボタンをクリックすると、フレームワークによって呼び出されます。|
|[CMFCDesktopAlertWnd:: OnCommand](#oncommand)|フレームワークは、ユーザーがメニューから項目を選択したとき、子コントロールが通知メッセージを送信したとき、またはアクセラレータのキーストロークが変換されたときに、このメンバー関数を呼び出します。 ( [CWnd:: OnCommand](../../mfc/reference/cwnd-class.md#oncommand)をオーバーライドします)。|
|[CMFCDesktopAlertWnd:: OnDraw](#ondraw)||
|[CMFCDesktopAlertWnd::P Roて Command](#processcommand)||
|[CMFCDesktopAlertWnd:: Setアニメーション速度](#setanimationspeed)|新しいアニメーション速度を設定します。|
|[CMFCDesktopAlertWnd:: Setアニメーションの種類](#setanimationtype)|アニメーションの種類を設定します。|
|[CMFCDesktopAlertWnd:: SetAutoCloseTime](#setautoclosetime)|自動終了のタイムアウトを設定します。|
|[CMFCDesktopAlertWnd:: SetSmallCaption](#setsmallcaption)|小さいキャプションと通常のキャプションを切り替えます。|
|[CMFCDesktopAlertWnd:: SetTransparency](#settransparency)|透明度レベルを設定します。|

## <a name="remarks"></a>解説

デスクトップ通知ウィンドウは、透明にすることができ、アニメーション効果と共に表示できます。また、指定した遅延の後、またはユーザーが [閉じる] ボタンをクリックして終了したときに、表示されなくなることがあります。

デスクトップの [警告] ウィンドウには、既定のダイアログも含まれます。このダイアログボックスには、アイコン、メッセージテキスト (ラベル)、およびリンクが含まれています。 また、デスクトップの [アラート] ウィンドウには、アプリケーションのリソースからのカスタムダイアログを含めることもできます。

デスクトップの [警告] ウィンドウを作成するには、2つの手順を実行します。 まず、コンストラクターを呼び出してオブジェクトを構築し `CMFCDesktopAlertWnd` ます。 次に、 [CMFCDesktopAlertWnd:: create](#create) メンバー関数を呼び出してウィンドウを作成し、オブジェクトにアタッチし `CMFCDesktopAlertWnd` ます。

オブジェクトは、 `CMFCDesktopAlertWnd` デスクトップの [アラート] ウィンドウのクライアント領域を塗りつぶす、特別な子ダイアログボックスを作成します。 ダイアログは、配置されているすべてのコントロールを所有します。

ポップアップウィンドウにカスタムダイアログボックスを表示するには、次の手順を実行します。

1. `CMFCDesktopAlertDialog` の派生クラスを作成します。

1. リソースに子ダイアログボックステンプレートを作成します。

1. ダイアログボックステンプレートのリソース ID と、派生クラスのランタイムクラス情報へのポインターを使用して、 [CMFCDesktopAlertWnd:: Create](#create) を呼び出します。

1. ホストされているコントロールからのすべての通知を処理するようにカスタムダイアログボックスをプログラミングするか、ホストされているコントロールをプログラミングして、これらの通知を直接処理します。

デスクトップの [警告] ウィンドウの動作を制御するには、次の関数を使用します。

- [CMFCDesktopAlertWnd:: Setanimation type](#setanimationtype)を呼び出して、アニメーションの種類を設定します。 有効なオプションには、展開、スライド、フェードなどがあります。

- [CMFCDesktopAlertWnd:: Setanimation speed](#setanimationspeed)を呼び出すことにより、アニメーションフレーム速度を設定します。

- [CMFCDesktopAlertWnd:: SetTransparency](#settransparency)を呼び出して、透過性レベルを設定します。

- [CMFCDesktopAlertWnd:: SetSmallCaption](#setsmallcaption)を呼び出すことによって、キャプションのサイズを小文字に変更します。 小さいキャプションの高さは7ピクセルです。

## <a name="example"></a>例

次の例は、クラスのさまざまなメソッドを使用してオブジェクトを構成する方法を示してい `CMFCDesktopAlertWnd` `CMFCDesktopAlertWnd` ます。 この例では、アニメーションの種類を設定する方法、ポップアップウィンドウの透明度を設定する方法、警告ウィンドウで小さいキャプションを表示するように指定する方法、およびアラートウィンドウが自動的に閉じるまでの時間を設定する方法を示します。 この例では、デスクトップの [警告] ウィンドウを作成および初期化する方法も示しています。 このコードスニペットは、 [デスクトップアラートのデモサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_DesktopAlertDemo#1](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwnd-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCDesktopAlertWnd](../../mfc/reference/cmfcdesktopalertwnd-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxDesktopAlertWnd

## <a name="cmfcdesktopalertwndcreate"></a><a name="create"></a> CMFCDesktopAlertWnd:: Create

デスクトップの [警告] ウィンドウを作成して初期化します。

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

*pWndOwner*<br/>
[入力、出力]アラートウィンドウの所有者を指定します。 その所有者は、デスクトップアラートウィンドウのすべての通知を受信します。 この値を NULL にすることはできません。

*uiDlgResID*<br/>
からアラートウィンドウのリソース ID を指定します。

*hMenu*<br/>
からユーザーがメニューボタンをクリックしたときに表示されるメニューを指定します。 NULL の場合、メニューボタンは表示されません。

*ptPos*<br/>
から画面座標を使用して、警告ウィンドウが表示される初期位置を指定します。 このパラメーターが (-1,-1) の場合、警告ウィンドウは画面の右下隅に表示されます。

*pRTIDlgBar*<br/>
からアラートウィンドウのクライアント領域をカバーするカスタムダイアログボックスクラスのランタイムクラス情報。

*params*<br/>
から警告ウィンドウの作成に使用するパラメーターを指定します。

### <a name="return-value"></a>戻り値

アラートウィンドウが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アラートウィンドウを作成するには、このメソッドを呼び出します。 [アラート] ウィンドウの [クライアント] 領域には、ユーザーに表示されるすべてのコントロールをホストする子ダイアログボックスが表示されます。

最初のメソッドオーバーロードによって、アプリケーションのリソースから読み込まれる子ダイアログボックスを含む警告ウィンドウが作成されます。 最初のメソッドオーバーロードでは、カスタムダイアログボックスクラスのランタイムクラス情報を指定することもできます。

2番目のメソッドオーバーロードは、既定のコントロールを含む警告ウィンドウを作成します。 [CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)を変更することで、表示するコントロールを指定できます。

## <a name="cmfcdesktopalertwndgetanimationspeed"></a><a name="getanimationspeed"></a> CMFCDesktopAlertWnd:: Getアニメーション速度

アニメーションの速度を返します。

```
UINT GetAnimationSpeed() const;
```

### <a name="return-value"></a>戻り値

警告ウィンドウのアニメーション速度 (ミリ秒単位)。

### <a name="remarks"></a>解説

アニメーションの速度は、[アラート] ウィンドウを開いたり閉じたりする速度を示します。

## <a name="cmfcdesktopalertwndgetanimationtype"></a><a name="getanimationtype"></a> CMFCDesktopAlertWnd:: Getアニメーションの種類

アニメーションの種類を返します。

```
CMFCPopupMenu::ANIMATION_TYPE GetAnimationType();
```

### <a name="return-value"></a>戻り値

次のいずれかのアニメーションの種類。

- NO_ANIMATION

- 折り畳み

- 挿入

- 非

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndgetautoclosetime"></a><a name="getautoclosetime"></a> CMFCDesktopAlertWnd:: GetAutoCloseTime

自動終了のタイムアウトを返します。

```
int GetAutoCloseTime() const;
```

### <a name="return-value"></a>戻り値

アラートウィンドウが自動的に閉じるまでの時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

このメソッドを使用すると、アラートウィンドウが自動的に閉じるまでの時間を指定できます。

## <a name="cmfcdesktopalertwndgetcaptionheight"></a><a name="getcaptionheight"></a> CMFCDesktopAlertWnd:: GetCaptionHeight

キャプションの高さを返します。

```
virtual int GetCaptionHeight();
```

### <a name="return-value"></a>戻り値

キャプションの高さ (ピクセル単位)。

### <a name="remarks"></a>解説

このメソッドは、派生クラスでオーバーライドできます。 既定の実装では、ポップアップウィンドウに小さいキャプション、または Windows API 関数から取得した値が表示される場合、小さいキャプションの高さ値 (7 ピクセル) が返されます `GetSystemMetrics(SM_CYSMCAPTION)` 。

## <a name="cmfcdesktopalertwndgetlastpos"></a><a name="getlastpos"></a> CMFCDesktopAlertWnd:: GetLastPos

画面上のデスクトップ通知ウィンドウの最後の位置を返します。

```
CPoint GetLastPos() const;
```

### <a name="return-value"></a>戻り値

画面座標で表される点。

### <a name="remarks"></a>解説

このメソッドは、画面上の警告ウィンドウの最後の有効な位置を返します。

## <a name="cmfcdesktopalertwndgettransparency"></a><a name="gettransparency"></a> CMFCDesktopAlertWnd:: GetTransparency

透明度を返します。

```
BYTE GetTransparency() const;
```

### <a name="return-value"></a>戻り値

0 ~ 255 の透明度レベル。 値が大きいほど、ウィンドウが不透明になります。

### <a name="remarks"></a>解説

このメソッドは、警告ウィンドウの現在の透明度レベルを取得するために使用します。

## <a name="cmfcdesktopalertwndhassmallcaption"></a><a name="hassmallcaption"></a> CMFCDesktopAlertWnd:: HasSmallCaption

デスクトップのアラートウィンドウのキャプションが小さいか、または標準サイズのキャプションを持つかを指定します。

```
BOOL HasSmallCaption() const;
```

### <a name="return-value"></a>戻り値

ポップアップウィンドウが小さいキャプションで表示される場合は TRUE。ポップアップウィンドウが標準サイズのキャプションで表示される場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを使用して、ポップアップウィンドウのキャプションが小さいか、または標準サイズのキャプションが表示されているかどうかを確認します。 既定では、小さいキャプションは7ピクセルの高さです。 Windows API 関数を呼び出すことによって、標準サイズのキャプションの高さを取得でき `GetSystemMetrics(SM_CYCAPTION)` ます。

## <a name="cmfcdesktopalertwndonbeforeshow"></a><a name="onbeforeshow"></a> CMFCDesktopAlertWnd:: OnBeforeShow

```
virtual BOOL OnBeforeShow(CPoint&);
```

### <a name="parameters"></a>パラメーター

から *CPoint&*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndonclicklinkbutton"></a><a name="onclicklinkbutton"></a> CMFCDesktopAlertWnd:: OnClickLinkButton

ユーザーがデスクトップの [警告] メニューにあるリンクボタンをクリックすると、フレームワークによって呼び出されます。

```
virtual BOOL OnClickLinkButton(UINT uiCmdID);
```

### <a name="parameters"></a>パラメーター

*uiCmdID*<br/>
からこのパラメーターは使用されません。

### <a name="return-value"></a>戻り値

常に FALSE です。

### <a name="remarks"></a>解説

ユーザーが警告ウィンドウのリンクをクリックしたときに通知されるようにする場合は、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfcdesktopalertwndoncommand"></a><a name="oncommand"></a> CMFCDesktopAlertWnd:: OnCommand

```
virtual BOOL OnCommand(
    WPARAM wParam,
    LPARAM lParam);
```

### <a name="parameters"></a>パラメーター

から *wParam*<br/>

から *lParam*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndondraw"></a><a name="ondraw"></a> CMFCDesktopAlertWnd:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndprocesscommand"></a><a name="processcommand"></a> CMFCDesktopAlertWnd::P Roて Command

```
BOOL ProcessCommand(HWND hwnd);
```

### <a name="parameters"></a>パラメーター

から *hwnd*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcdesktopalertwndsetanimationspeed"></a><a name="setanimationspeed"></a> CMFCDesktopAlertWnd:: Setアニメーション速度

新しいアニメーション速度を設定します。

```cpp
void SetAnimationSpeed(UINT nSpeed);
```

### <a name="parameters"></a>パラメーター

*nSpeed*<br/>
から新しいアニメーション速度をミリ秒単位で指定します。

### <a name="remarks"></a>解説

アラートウィンドウのアニメーション速度を設定するには、このメソッドを呼び出します。 既定のアニメーション速度は30ミリ秒です。

## <a name="cmfcdesktopalertwndsetanimationtype"></a><a name="setanimationtype"></a> CMFCDesktopAlertWnd:: Setアニメーションの種類

アニメーションの種類を設定します。

```cpp
void SetAnimationType(CMFCPopupMenu::ANIMATION_TYPE type);
```

### <a name="parameters"></a>パラメーター

*type*<br/>
からアニメーションの種類を指定します。

### <a name="remarks"></a>解説

アニメーションの種類を設定するには、このメソッドを呼び出します。 次のいずれかの値を指定できます。

- NO_ANIMATION

- 折り畳み

- 挿入

- 非

- SYSTEM_DEFAULT_ANIMATION

## <a name="cmfcdesktopalertwndsetautoclosetime"></a><a name="setautoclosetime"></a> CMFCDesktopAlertWnd:: SetAutoCloseTime

自動終了のタイムアウトを設定します。

```cpp
void SetAutoCloseTime(int nTime);
```

### <a name="parameters"></a>パラメーター

*nTime*<br/>
からアラートウィンドウが自動的に閉じられるまでの経過時間 (ミリ秒単位)。

### <a name="remarks"></a>解説

ユーザーがウィンドウと対話しない場合、指定した時間が経過すると、アラートウィンドウは自動的に閉じられます。

## <a name="cmfcdesktopalertwndsetsmallcaption"></a><a name="setsmallcaption"></a> CMFCDesktopAlertWnd:: SetSmallCaption

小さいキャプションと標準サイズのキャプションを切り替えます。

```cpp
void SetSmallCaption(BOOL bSmallCaption = TRUE);
```

### <a name="parameters"></a>パラメーター

*bSmallCaption*<br/>
から[警告] ウィンドウに小さいキャプションを表示するように指定する場合は TRUE。それ以外の場合は、[警告] ウィンドウに通常のサイズのキャプションが表示されるように指定する場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを呼び出して、小さいまたは標準サイズのキャプションを表示します。 既定では、小さいキャプションは7ピクセルの高さです。 Windows API 関数を呼び出すことによって、通常のキャプションのサイズを取得でき `GetSystemMetrics(SM_CYCAPTION)` ます。

## <a name="cmfcdesktopalertwndsettransparency"></a><a name="settransparency"></a> CMFCDesktopAlertWnd:: SetTransparency

ポップアップウィンドウの透明度を設定します。

```cpp
void SetTransparency(BYTE nTransparency);
```

### <a name="parameters"></a>パラメーター

*nTransparency*<br/>
から透明度レベルを指定します。 この値は 0 ~ 255 の範囲で指定する必要があります。 値が大きいほど、ウィンドウが不透明になります。

### <a name="remarks"></a>解説

ポップアップウィンドウの透明度レベルを設定するには、この関数を呼び出します。

## <a name="cmfcdesktopalertwndgetdialogsize"></a><a name="getdialogsize"></a> CMFCDesktopAlertWnd:: Get Size

```
virtual CSize GetDialogSize();
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWndInfo クラス](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)<br/>
[CMFCDesktopAlertDialog クラス](../../mfc/reference/cmfcdesktopalertdialog-class.md)<br/>
[CWnd クラス](../../mfc/reference/cwnd-class.md)
