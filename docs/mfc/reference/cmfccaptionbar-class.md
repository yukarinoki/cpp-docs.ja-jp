---
title: CMFCCaptionBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar
- AFXCAPTIONBAR/CMFCCaptionBar::Create
- AFXCAPTIONBAR/CMFCCaptionBar::DoesAllowDynInsertBefore
- AFXCAPTIONBAR/CMFCCaptionBar::EnableButton
- AFXCAPTIONBAR/CMFCCaptionBar::GetAlignment
- AFXCAPTIONBAR/CMFCCaptionBar::GetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::GetButtonRect
- AFXCAPTIONBAR/CMFCCaptionBar::GetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::IsMessageBarMode
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveButton
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveIcon
- AFXCAPTIONBAR/CMFCCaptionBar::RemoveText
- AFXCAPTIONBAR/CMFCCaptionBar::SetBitmap
- AFXCAPTIONBAR/CMFCCaptionBar::SetBorderSize
- AFXCAPTIONBAR/CMFCCaptionBar::SetButton
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonPressed
- AFXCAPTIONBAR/CMFCCaptionBar::SetButtonToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetFlatBorder
- AFXCAPTIONBAR/CMFCCaptionBar::SetIcon
- AFXCAPTIONBAR/CMFCCaptionBar::SetImageToolTip
- AFXCAPTIONBAR/CMFCCaptionBar::SetMargin
- AFXCAPTIONBAR/CMFCCaptionBar::SetText
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBackground
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawBorder
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawButton
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawImage
- AFXCAPTIONBAR/CMFCCaptionBar::OnDrawText
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBackground
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarBorder
- AFXCAPTIONBAR/CMFCCaptionBar::m_clrBarText
helpviewer_keywords:
- CMFCCaptionBar [MFC], Create
- CMFCCaptionBar [MFC], DoesAllowDynInsertBefore
- CMFCCaptionBar [MFC], EnableButton
- CMFCCaptionBar [MFC], GetAlignment
- CMFCCaptionBar [MFC], GetBorderSize
- CMFCCaptionBar [MFC], GetButtonRect
- CMFCCaptionBar [MFC], GetMargin
- CMFCCaptionBar [MFC], IsMessageBarMode
- CMFCCaptionBar [MFC], RemoveBitmap
- CMFCCaptionBar [MFC], RemoveButton
- CMFCCaptionBar [MFC], RemoveIcon
- CMFCCaptionBar [MFC], RemoveText
- CMFCCaptionBar [MFC], SetBitmap
- CMFCCaptionBar [MFC], SetBorderSize
- CMFCCaptionBar [MFC], SetButton
- CMFCCaptionBar [MFC], SetButtonPressed
- CMFCCaptionBar [MFC], SetButtonToolTip
- CMFCCaptionBar [MFC], SetFlatBorder
- CMFCCaptionBar [MFC], SetIcon
- CMFCCaptionBar [MFC], SetImageToolTip
- CMFCCaptionBar [MFC], SetMargin
- CMFCCaptionBar [MFC], SetText
- CMFCCaptionBar [MFC], OnDrawBackground
- CMFCCaptionBar [MFC], OnDrawBorder
- CMFCCaptionBar [MFC], OnDrawButton
- CMFCCaptionBar [MFC], OnDrawImage
- CMFCCaptionBar [MFC], OnDrawText
- CMFCCaptionBar [MFC], m_clrBarBackground
- CMFCCaptionBar [MFC], m_clrBarBorder
- CMFCCaptionBar [MFC], m_clrBarText
ms.assetid: acb54d5f-14ff-4c96-aeb3-7717cf566d9a
ms.openlocfilehash: c42b1ccb51a3c290e0887717d900543b8d5b277a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752620"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar クラス

オブジェクト`CMFCCaptionBar`は、ボタン、テキスト ラベル、およびビットマップの 3 つの要素を表示できるコントロール バーです。 表示できる各要素の数は 1 つずつです。 各要素は、コントロールの左端、右端、または中央に揃えて配置できます。 また、キャプション バーの上部または下部の境界線にフラット スタイルまたは 3D スタイルを適用することもできます。

## <a name="syntax"></a>構文

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCキャプションバー::作成](#create)|キャプション バー コントロールを作成し、オブジェクトに`CMFCCaptionBar`アタッチします。|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|キャプション バーとその親フレームの間に別のペインを動的に挿入できるかどうかを示します。 [(CBase ペインをオーバーライドします::DoesAllowDynInsert前に](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore).)|
|[ボタンを有効にします。](#enablebutton)|キャプション バーのボタンを有効または無効にします。|
|[コントロールバー::取得アライメント](#getalignment)|指定した要素の配置を返します。|
|[ウィンドウバー::ゲットボーダーサイズ](#getbordersize)|キャプション バーの境界線のサイズを返します。|
|[コントロールバーを取得します。](#getbuttonrect)|キャプション バーのボタンの外接する四角形を取得します。|
|[バー::ゲットマージン](#getmargin)|キャプション バー要素の端とキャプション バー コントロールの端との間の距離を返します。|
|[メッセージバーモード](#ismessagebarmode)|キャプション バーがメッセージ バー モードかどうかを指定します。|
|[をクリックします。](#removebitmap)|キャプション バーからビットマップ イメージを削除します。|
|[ボタンの削除](#removebutton)|キャプション バーからボタンを削除します。|
|[アイコンを削除します。](#removeicon)|キャプション バーからアイコンを削除します。|
|[テキストを削除します。](#removetext)|キャプション バーからテキスト ラベルを削除します。|
|[をクリックします。](#setbitmap)|キャプション バーのビットマップ イメージを設定します。|
|[ウィンドウセットキャプション バー::境界線サイズ](#setbordersize)|キャプション バーの境界線のサイズを設定します。|
|[コントロール バー::セットボタン](#setbutton)|キャプション バーのボタンを設定します。|
|[コントロールバー::ボタンを押す](#setbuttonpressed)|ボタンを押したままにするかどうかを指定します。|
|[ヒントを設定します。](#setbuttontooltip)|ボタンのツールチップを設定します。|
|[ウィンドウバー::セットフラットボーダー](#setflatborder)|キャプション バーの境界線のスタイルを設定します。|
|[バー::セットアイコン](#seticon)|キャプション バーのアイコンを設定します。|
|[ヒントを表示します。](#setimagetooltip)|キャプション バーのイメージのツールヒントを設定します。|
|[セットマージン](#setmargin)|キャプション バー要素の端とキャプション バー コントロールの端との間の距離を設定します。|
|[セットテキスト](#settext)|キャプション バーのテキスト ラベルを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[次の値を指定します。](#ondrawbackground)|キャプション バーの背景を塗りつぶすために、フレームワークによって呼び出されます。|
|[ウィンドウの境界線](#ondrawborder)|キャプション バーの境界線を描画するために、フレームワークによって呼び出されます。|
|[コントロール バー::オンドローボタン](#ondrawbutton)|キャプション バー ボタンを描画するために、フレームワークによって呼び出されます。|
|[をクリックします。](#ondrawimage)|キャプション バーのイメージを描画するために、フレームワークによって呼び出されます。|
|[をクリックします。](#ondrawtext)|キャプション バーのテキストを描画するために、フレームワークによって呼び出されます。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[バー:m_clrBarBackground](#m_clrbarbackground)|キャプション バーの背景色。|
|[バー:m_clrBarBorder](#m_clrbarborder)|キャプション バーの境界線の色。|
|[バー:m_clrBarText](#m_clrbartext)|キャプション バーのテキストの色。|

## <a name="remarks"></a>解説

キャプション バーを作成するには、次の手順を実行します。

1. オブジェクトを`CMFCCaptionBar`構築します。 通常は、キャプション バーをフレーム ウィンドウ クラスに追加します。

1. [CMFCキャプションバー::Create](#create)メソッドを呼び出してキャプションバーコントロールを作成し、オブジェクト`CMFCCaptionBar`にアタッチします。

1. 呼び出し[CMFC キャプション バー::セットボタン](#setbutton)[、CMFCキャプションバー::セットテキスト](#settext)[、CMFCキャプションバー::セットアイコン](#seticon)、およびキャプションバーの要素を設定する[ビットマップを呼び出します](#setbitmap)。

ボタン要素を設定する場合は、ボタンにコマンド ID を割り当てる必要があります。 ユーザーがボタンをクリックすると、キャプション バーは、この ID を持つWM_COMMAND メッセージを親フレーム ウィンドウにルーティングします。

キャプション バーは、Microsoft Office 2007 アプリケーションに表示されるメッセージ バーをエミュレートするメッセージ バー モードでも機能します。 メッセージ バー モードでは、キャプション バーにはビットマップ、メッセージ、ボタン (通常はダイアログ ボックスが開きます) が表示されます。ビットマップにツールチップを割り当てることができます。

メッセージ バー モードを有効にするには、呼び出し[CMFCCaptionBar::作成](#create)し、4 番目のパラメーター (bIsMessageBarMode) を TRUE に設定します。

## <a name="example"></a>例

`CMFCCaptionBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、キャプション バー コントロールの作成方法、キャプション バーの 3D 境界線の設定、キャプション バー要素の端とキャプション バー コントロールの端の間の距離のピクセル単位の設定、キャプション バーのボタンの設定、ボタンのツールヒントの設定、キャプション バーのテキスト ラベルの設定、キャプション バーのビットマップ イメージの設定方法を示します。をクリックし、キャプション バーに画像のツールチップを設定します。 このコード スニペットは、 [MS Office 2007 デモ サンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxキャプションバー.h

## <a name="cmfccaptionbarcreate"></a><a name="create"></a>CMFCキャプションバー::作成

キャプション バー コントロールを作成し、オブジェクトに`CMFCCaptionBar`アタッチします。

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>パラメーター

*Dwstyle*<br/>
キャプション バースタイルの論理 OR の組み合わせ。

*pParentWnd*<br/>
キャプション バー コントロールの親ウィンドウ。

*Uid*<br/>
キャプション バー コントロールの ID。

*nHeight*<br/>
キャプション バー コントロールの高さ (ピクセル単位)。 1 の場合、高さは、アイコンの高さ、テキスト、およびキャプション バー コントロールに表示されるボタンに従って計算されます。

*メッセージバーモード*<br/>
キャプション バーがメッセージ バー モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

キャプション バー コントロールが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトは`CMFCCaptionBar`2 つの手順で作成します。 まず、コンストラクターを呼び出し、メソッドを`Create`呼び出します。 `CMFCCaptionBar`

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a>前に挿入 :Dする

キャプション バーとその親フレームの間に別のペインを動的に挿入できるかどうかを示します。

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

オーバーライドされない限り、FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a>ボタンを有効にします。

キャプション バーのボタンを有効または無効にします。

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]TRUE ボタンを有効にする場合は FALSE、ボタンを無効にする場合は FALSE。

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a>コントロールバー::取得アライメント

指定した要素の配置を返します。

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>パラメーター

*Elem*<br/>
[in]配置を取得する対象のキャプション バー要素。

### <a name="return-value"></a>戻り値

ボタン、ビットマップ、テキスト、アイコンなどの要素の配置。

### <a name="remarks"></a>解説

要素の配置は、次のいずれかの値になります。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a>ウィンドウバー::ゲットボーダーサイズ

キャプション バーの境界線のサイズを返します。

```
int GetBorderSize() const;
```

### <a name="return-value"></a>戻り値

境界線のサイズ (ピクセル単位)。

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a>コントロールバーを取得します。

キャプション バーのボタンの外接する四角形を取得します。

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>戻り値

キャプション`CRect`バーのボタンの外接する四角形の座標を格納するオブジェクト。

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a>バー::ゲットマージン

キャプション バー要素の端とキャプション バー コントロールの端との間の距離を返します。

```
int GetMargin() const;
```

### <a name="return-value"></a>戻り値

キャプション バー要素の端とキャプション バー コントロールの端との間の距離 (ピクセル単位)。

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a>メッセージバーモード

キャプション バーがメッセージ バー モードかどうかを指定します。

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>戻り値

キャプション バーがメッセージ バー モードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

メッセージ バー モードでは、キャプション バーに、ヒント、メッセージ テキスト、およびボタンを含むイメージが表示されます。

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a>バー:m_clrBarBackground

キャプション バーの背景色。

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a>バー:m_clrBarBorder

キャプション バーの境界線の色。

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a>バー:m_clrBarText

キャプション バーのテキストの色。

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a>次の値を指定します。

キャプション バーの背景を塗りつぶすために、フレームワークによって呼び出されます。

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]キャプション バーのデバイス コンテキストへのポインター。

*Rect*<br/>
[in]塗りつぶす外接する四角形。

### <a name="remarks"></a>解説

キャプション`OnDrawBackground`バーの背景が埋め込まれるときにメソッドが呼び出されます。 既定の実装では、色を使用して背景[を塗りつぶし m_clrBarBackgroundします](#m_clrbarbackground)。

キャプション バーの外観`CMFCCaptionBar`をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a>ウィンドウの境界線

キャプション バーの境界線を描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]境界線の表示に使用されるデバイス コンテキスト。

*Rect*<br/>
[in]外接する四角形。

### <a name="remarks"></a>解説

既定では、境界線はフラット スタイルになっています。

キャプション バーの境界線`CMFCCaptionBar`の外観をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a>コントロール バー::オンドローボタン

キャプション バー ボタンを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンの表示に使用されるデバイス コンテキストへのポインター。

*Rect*<br/>
[in]ボタンの外接する四角形。

*ストラーボタン*<br/>
[in]ボタンのテキスト ラベル。

*b有効*<br/>
[in]ボタンが有効になっている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

キャプション バーのボタン`CMFCCaptionBar`の外観をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a>をクリックします。

キャプション バーのイメージを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]イメージの表示に使用されるデバイス コンテキストへのポインター。

*Rect*<br/>
[in]イメージの外接する四角形を指定します。

### <a name="remarks"></a>解説

イメージの外観をカスタマイズ`CMFCCaptionBar`するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a>をクリックします。

キャプション バーのテキストを描画するために、フレームワークによって呼び出されます。

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]ボタンの表示に使用されるデバイス コンテキストへのポインター。

*Rect*<br/>
[in]テキストの外接する四角形。

*str テキスト*<br/>
[in]表示するテキスト文字列。

### <a name="remarks"></a>解説

既定の実装では、テキストを表示`CDC::DrawText`するには[、CMFCCaptionBar::m_clrBarText](#m_clrbartext)色を使用します。

キャプション バーのテキスト`CMFCCaptionBar`の外観をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a>をクリックします。

キャプション バーからビットマップ イメージを削除します。

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a>ボタンの削除

キャプション バーからボタンを削除します。

```cpp
void RemoveButton();
```

### <a name="remarks"></a>解説

キャプションバー要素のレイアウトは自動的に調整されます。

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a>アイコンを削除します。

キャプション バーからアイコンを削除します。

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a>テキストを削除します。

キャプション バーからテキスト ラベルを削除します。

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a>をクリックします。

キャプション バーのビットマップ イメージを設定します。

```cpp
void SetBitmap(
    HBITMAP hBitmap,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);

void SetBitmap(
    UINT uiBmpResID,
    COLORREF clrTransparent,
    BOOL bStretch=FALSE,
    BarElementAlignment bmpAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>パラメーター

*hビットマップ*<br/>
[in]設定するビットマップへのハンドル。

*clr透明*<br/>
[in]ビットマップの透明色を指定する RGB 値。

*bストレッチ*<br/>
[in]TRUE の場合、ビットマップは、境界領域のイメージに収まらない場合に拡大されます。 それ以外の場合、ビットマップは拡大されません。

*配置*<br/>
[in]ビットマップの配置。

### <a name="remarks"></a>解説

このメソッドは、キャプション バーにビットマップを設定するために使います。

前のビットマップは自動的に破棄されます。 [CMFCキャプションバー::SetIcon](#seticon)メソッドを呼び出したためにキャプションバーにアイコンが表示される場合[、CMFCキャプションバー::RemoveIcon](#removeicon)を呼び出してアイコンを削除しない限り、ビットマップは表示されません。

ビットマップは *、bmpAlignment*パラメーターで指定されたとおりに配置されます。  このパラメーターには、次の `BarElementAlignment` 値のいずれかを指定できます。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a>ウィンドウセットキャプション バー::境界線サイズ

キャプション バーの境界線のサイズを設定します。

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>パラメーター

*Nsize*<br/>
[in]キャプション バーの境界線の新しいサイズ (ピクセル単位)。

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a>コントロール バー::セットボタン

キャプション バーのボタンを設定します。

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>パラメーター

*ラベル*<br/>
ボタンのコマンド ラベル。

*UIUiUI*<br/>
ボタンのコマンド ID。

*btnAlignmnet*<br/>
ボタンの配置。

*アロー*<br/>
ボタンにドロップダウン矢印が表示される場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a>コントロールバー::ボタンを押す

ボタンを押したままにするかどうかを指定します。

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>パラメーター

*b減価償却*<br/>
ボタンが押された状態を維持する場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a>ヒントを設定します。

ボタンのツールチップを設定します。

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszToolTip*<br/>
[in]ツールヒントのキャプション。

*説明をします。*<br/>
[in]ツールヒントの説明。

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a>ウィンドウバー::セットフラットボーダー

キャプション バーの境界線のスタイルを設定します。

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>パラメーター

*bフラット*<br/>
[in]TRUE の場合、キャプション バーの境界線がフラットです。 境界が 3D の場合は FALSE。

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a>バー::セットアイコン

キャプション バーのアイコンを設定します。

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>パラメーター

*Hicon*<br/>
[in]設定するアイコンのハンドル。

*アイコン配置*<br/>
[in]アイコンの配置。

### <a name="remarks"></a>解説

キャプション バーには、アイコンまたはビットマップのいずれかを表示できます。 ビットマップを表示する方法については[、「CMFCキャプションバー::SetBitmap」](#setbitmap)を参照してください。 アイコンとビットマップの両方を設定すると、アイコンは常に表示されます。 キャプション バーからアイコンを削除するには[、CMFCキャプションバー::RemoveIcon](#removeicon)を呼び出します。

アイコンは *、iconAlignment*パラメータに従って整列されます。 次`BarElementAlignment`のいずれかの値を指定できます。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a>ヒントを表示します。

キャプション バーのイメージのツールチップを設定します。

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszToolTip*<br/>
[in]ツールヒントのテキスト。

*説明をします。*<br/>
[in]ツールヒントの説明。

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a>セットマージン

キャプション バー要素の端とキャプション バー コントロールの端との間の距離を設定します。

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>パラメーター

*nマージン*<br/>
[in]キャプション バー要素の端とキャプション バー コントロールの端との間の距離 (ピクセル単位)。

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a>セットテキスト

キャプション バーのテキスト ラベルを設定します。

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>パラメーター

*str テキスト*<br/>
[in]設定するテキスト文字列。

*テキスト配置*<br/>
[in]テキストの配置。

### <a name="remarks"></a>解説

テキスト ラベルは *、textAlignment*パラメータで指定された位置に合わせて配置されます。 次`BarElementAlignment`のいずれかの値を指定できます。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
