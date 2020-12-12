---
description: '詳細情報: CMFCCaptionBar クラス'
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
ms.openlocfilehash: a5dd5f968c52268935b6176115e8723a9d82e8a1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327739"
---
# <a name="cmfccaptionbar-class"></a>CMFCCaptionBar クラス

`CMFCCaptionBar`オブジェクトは、ボタン、テキストラベル、ビットマップという3つの要素を表示できるコントロールバーです。 表示できる各要素の数は 1 つずつです。 各要素は、コントロールの左端、右端、または中央に揃えて配置できます。 また、キャプション バーの上部または下部の境界線にフラット スタイルまたは 3D スタイルを適用することもできます。

## <a name="syntax"></a>構文

```
class CMFCCaptionBar : public CPane
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCCaptionBar:: Create](#create)|キャプションバーコントロールを作成し、オブジェクトにアタッチし `CMFCCaptionBar` ます。|
|[CMFCCaptionBar::DoesAllowDynInsertBefore](#doesallowdyninsertbefore)|キャプションバーとその親フレームの間に別のペインを動的に挿入できるかどうかを示します。 ( [Cbasepane::D oesallowdyninsertbefore](../../mfc/reference/cbasepane-class.md#doesallowdyninsertbefore)をオーバーライドします)。|
|[CMFCCaptionBar:: EnableButton](#enablebutton)|キャプションバーのボタンを有効または無効にします。|
|[CMFCCaptionBar:: GetAlignment](#getalignment)|指定された要素の配置を返します。|
|[CMFCCaptionBar:: GetBorderSize](#getbordersize)|キャプションバーの境界線のサイズを返します。|
|[CMFCCaptionBar:: GetButtonRect](#getbuttonrect)|キャプションバーのボタンの外接する四角形を取得します。|
|[CMFCCaptionBar:: GetMargin](#getmargin)|キャプションバー要素の端とキャプションバーコントロールの端との間の距離を返します。|
|[CMFCCaptionBar:: IsMessageBarMode](#ismessagebarmode)|キャプションバーがメッセージバーモードであるかどうかを指定します。|
|[CMFCCaptionBar:: RemoveBitmap](#removebitmap)|キャプションバーからビットマップイメージを削除します。|
|[CMFCCaptionBar:: RemoveButton](#removebutton)|キャプションバーからボタンを削除します。|
|[CMFCCaptionBar:: RemoveIcon](#removeicon)|キャプションバーからアイコンを削除します。|
|[CMFCCaptionBar:: RemoveText](#removetext)|キャプションバーからテキストラベルを削除します。|
|[CMFCCaptionBar:: SetBitmap](#setbitmap)|キャプションバーのビットマップイメージを設定します。|
|[CMFCCaptionBar:: SetBorderSize](#setbordersize)|キャプションバーの境界線のサイズを設定します。|
|[CMFCCaptionBar:: SetButton](#setbutton)|キャプションバーのボタンを設定します。|
|[CMFCCaptionBar:: SetButtonPressed](#setbuttonpressed)|ボタンが押されたままになるかどうかを指定します。|
|[CMFCCaptionBar:: SetButtonToolTip](#setbuttontooltip)|ボタンのツールヒントを設定します。|
|[CMFCCaptionBar:: SetFlatBorder](#setflatborder)|キャプションバーの境界線スタイルを設定します。|
|[CMFCCaptionBar:: SetIcon](#seticon)|キャプションバーのアイコンを設定します。|
|[CMFCCaptionBar:: SetImageToolTip](#setimagetooltip)|キャプションバーのイメージのツールヒントを設定します。|
|[CMFCCaptionBar:: SetMargin](#setmargin)|キャプションバー要素の端とキャプションバーコントロールの端との距離を設定します。|
|[CMFCCaptionBar:: SetText](#settext)|キャプションバーのテキストラベルを設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCCaptionBar:: OnDrawBackground](#ondrawbackground)|キャプションバーの背景を塗りつぶすためにフレームワークによって呼び出されます。|
|[CMFCCaptionBar:: OnDrawBorder](#ondrawborder)|キャプションバーの境界線を描画するためにフレームワークによって呼び出されます。|
|[CMFCCaptionBar:: OnDrawButton](#ondrawbutton)|キャプションバーボタンを描画するためにフレームワークによって呼び出されます。|
|[CMFCCaptionBar:: OnDrawImage](#ondrawimage)|キャプションバーイメージを描画するためにフレームワークによって呼び出されます。|
|[CMFCCaptionBar:: OnDrawText](#ondrawtext)|キャプションバーのテキストを描画するためにフレームワークによって呼び出されます。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCCaptionBar:: m_clrBarBackground](#m_clrbarbackground)|キャプションバーの背景色。|
|[CMFCCaptionBar:: m_clrBarBorder](#m_clrbarborder)|キャプションバーの境界線の色。|
|[CMFCCaptionBar:: m_clrBarText](#m_clrbartext)|キャプションバーのテキストの色。|

## <a name="remarks"></a>解説

キャプションバーを作成するには、次の手順を実行します。

1. オブジェクトを構築 `CMFCCaptionBar` します。 通常は、フレームウィンドウクラスにキャプションバーを追加します。

1. [CMFCCaptionBar:: Create](#create)メソッドを呼び出してキャプションバーコントロールを作成し、オブジェクトにアタッチし `CMFCCaptionBar` ます。

1. [CMFCCaptionBar:: SetButton](#setbutton)、 [CMFCCaptionBar:: SetText](#settext)、 [CMFCCaptionBar:: SetIcon](#seticon)、および[CMFCCaptionBar:: SetBitmap](#setbitmap)を呼び出して、キャプションバーの要素を設定します。

Button 要素を設定するときは、ボタンにコマンド ID を割り当てる必要があります。 ユーザーがボタンをクリックすると、キャプションバーはこの ID を持つ WM_COMMAND メッセージを親フレームウィンドウにルーティングします。

キャプションバーは、Microsoft Office 2007 アプリケーションに表示されるメッセージバーをエミュレートするメッセージバーモードでも機能します。 メッセージバーモードでは、キャプションバーにビットマップ、メッセージ、ボタンが表示されます (通常はダイアログボックスが開きます)。ビットマップにツールヒントを割り当てることができます。

メッセージバーモードを有効にするには、 [CMFCCaptionBar:: Create](#create) を呼び出し、4番目のパラメーター (bIsMessageBarMode) を TRUE に設定します。

## <a name="example"></a>例

`CMFCCaptionBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、キャプションバーコントロールを作成する方法、キャプションバーの3D 境界線を設定する方法、キャプションバー要素の端とキャプションバーコントロールの端の間の距離をピクセル単位で設定する方法、キャプションバーのボタンを設定する方法、キャプションバーのテキストラベルを設定する方法、キャプションバーのビットマップイメージを設定する方法を示します。] を使用し、キャプションバーに画像のツールヒントを設定します。 このコードスニペットは、 [MS Office 2007 Demo サンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_MSOffice2007Demo#1](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_1.h)]
[!code-cpp[NVC_MFC_MSOffice2007Demo#2](../../mfc/reference/codesnippet/cpp/cmfccaptionbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCCaptionBar](../../mfc/reference/cmfccaptionbar-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxcaptionbar

## <a name="cmfccaptionbarcreate"></a><a name="create"></a> CMFCCaptionBar:: Create

キャプションバーコントロールを作成し、オブジェクトにアタッチし `CMFCCaptionBar` ます。

```
BOOL Create(
    DWORD dwStyle,
    CWnd* pParentWnd,
    UINT uID,
    int nHeight=-1,
    BOOL bIsMessageBarMode=FALSE);
```

### <a name="parameters"></a>パラメーター

*dwStyle*<br/>
キャプションバーのスタイルの論理的または組み合わせ。

*pParentWnd*<br/>
キャプションバーコントロールの親ウィンドウ。

*uID*<br/>
キャプションバーコントロールの ID。

*nHeight*<br/>
キャプションバーコントロールの高さ (ピクセル単位)。 -1 の場合、高さはアイコンの高さ、キャプションバーコントロールによって表示されるテキストとボタンに従って計算されます。

*bIsMessageBarMode*<br/>
キャプションバーがメッセージバーモードの場合は TRUE。それ以外の場合は FALSE。

### <a name="return-value"></a>戻り値

キャプションバーコントロールが正常に作成された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトを構築するには、 `CMFCCaptionBar` 2 つの手順を実行します。 まず、コンストラクターを呼び出してから、メソッドを呼び出します `Create` 。このメソッドは、Windows コントロールを作成し、オブジェクトにアタッチし `CMFCCaptionBar` ます。

## <a name="cmfccaptionbardoesallowdyninsertbefore"></a><a name="doesallowdyninsertbefore"></a> CMFCCaptionBar::D oesAllowDynInsertBefore

キャプションバーとその親フレームの間に別のペインを動的に挿入できるかどうかを示します。

```
virtual BOOL DoesAllowDynInsertBefore() const;
```

### <a name="return-value"></a>戻り値

オーバーライドされない限り、FALSE を返します。

### <a name="remarks"></a>解説

## <a name="cmfccaptionbarenablebutton"></a><a name="enablebutton"></a> CMFCCaptionBar:: EnableButton

キャプションバーのボタンを有効または無効にします。

```cpp
void EnableButton(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
からボタンを有効にする場合は TRUE、ボタンを無効にする場合は FALSE。

## <a name="cmfccaptionbargetalignment"></a><a name="getalignment"></a> CMFCCaptionBar:: GetAlignment

指定された要素の配置を返します。

```
BarElementAlignment GetAlignment(BarElement elem);
```

### <a name="parameters"></a>パラメーター

*elem*<br/>
から配置を取得する対象のキャプションバー要素。

### <a name="return-value"></a>戻り値

要素の配置 (ボタン、ビットマップ、テキスト、アイコンなど) です。

### <a name="remarks"></a>解説

要素のアラインメントは、次のいずれかの値になります。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbargetbordersize"></a><a name="getbordersize"></a> CMFCCaptionBar:: GetBorderSize

キャプションバーの境界線のサイズを返します。

```
int GetBorderSize() const;
```

### <a name="return-value"></a>戻り値

境界線のサイズ (ピクセル単位)。

## <a name="cmfccaptionbargetbuttonrect"></a><a name="getbuttonrect"></a> CMFCCaptionBar:: GetButtonRect

キャプションバーのボタンの外接する四角形を取得します。

```
CRect GetButtonRect() const;
```

### <a name="return-value"></a>戻り値

`CRect`キャプションバーのボタンの外接する四角形の座標を格納しているオブジェクト。

## <a name="cmfccaptionbargetmargin"></a><a name="getmargin"></a> CMFCCaptionBar:: GetMargin

キャプションバー要素の端とキャプションバーコントロールの端との間の距離を返します。

```
int GetMargin() const;
```

### <a name="return-value"></a>戻り値

キャプションバー要素の端とキャプションバーコントロールの端との間の距離 (ピクセル単位)。

## <a name="cmfccaptionbarismessagebarmode"></a><a name="ismessagebarmode"></a> CMFCCaptionBar:: IsMessageBarMode

キャプションバーがメッセージバーモードであるかどうかを指定します。

```
BOOL IsMessageBarMode() const;
```

### <a name="return-value"></a>戻り値

キャプションバーがメッセージバーモードの場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

メッセージバーモードでは、キャプションバーに、ツールヒント、メッセージテキスト、およびボタンを含むイメージが表示されます。

## <a name="cmfccaptionbarm_clrbarbackground"></a><a name="m_clrbarbackground"></a> CMFCCaptionBar:: m_clrBarBackground

キャプションバーの背景色。

```
COLORREF m_clrBarBackground
```

## <a name="cmfccaptionbarm_clrbarborder"></a><a name="m_clrbarborder"></a> CMFCCaptionBar:: m_clrBarBorder

キャプションバーの境界線の色。

```
COLORREF m_clrBarBorder
```

## <a name="cmfccaptionbarm_clrbartext"></a><a name="m_clrbartext"></a> CMFCCaptionBar:: m_clrBarText

キャプションバーのテキストの色。

```
COLORREF m_clrBarText
```

## <a name="cmfccaptionbarondrawbackground"></a><a name="ondrawbackground"></a> CMFCCaptionBar:: OnDrawBackground

キャプションバーの背景を塗りつぶすためにフレームワークによって呼び出されます。

```
virtual void OnDrawBackground(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からキャプションバーのデバイスコンテキストへのポインター。

*rect*<br/>
から塗りつぶす外接する四角形。

### <a name="remarks"></a>解説

`OnDrawBackground`キャプションバーの背景がいっぱいになると、メソッドが呼び出されます。 既定の実装は、 [CMFCCaptionBar:: m_clrBarBackground](#m_clrbarbackground) の色を使用して、背景を塗りつぶします。

このメソッドを派生クラスでオーバーライドして、 `CMFCCaptionBar` キャプションバーの外観をカスタマイズします。

## <a name="cmfccaptionbarondrawborder"></a><a name="ondrawborder"></a> CMFCCaptionBar:: OnDrawBorder

キャプションバーの境界線を描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawBorder(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
から境界線を表示するために使用されるデバイスコンテキスト。

*rect*<br/>
から外接する四角形。

### <a name="remarks"></a>解説

既定では、境界線はフラットスタイルです。

このメソッドを派生クラスでオーバーライドして、 `CMFCCaptionBar` キャプションバーの境界線の外観をカスタマイズします。

## <a name="cmfccaptionbarondrawbutton"></a><a name="ondrawbutton"></a> CMFCCaptionBar:: OnDrawButton

キャプションバーボタンを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawButton(
    CDC* pDC,
    CRect rect,
    const CString& strButton,
    BOOL bEnabled);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からボタンを表示するために使用されるデバイスコンテキストへのポインター。

*rect*<br/>
からボタンの外接する四角形。

*strButton*<br/>
からボタンのテキストラベル。

*bEnabled*<br/>
からボタンが有効な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドを派生クラスでオーバーライドして、 `CMFCCaptionBar` キャプションバーのボタンの外観をカスタマイズします。

## <a name="cmfccaptionbarondrawimage"></a><a name="ondrawimage"></a> CMFCCaptionBar:: OnDrawImage

キャプションバーイメージを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawImage(
    CDC* pDC,
    CRect rect);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からイメージを表示するために使用されるデバイスコンテキストへのポインター。

*rect*<br/>
からイメージの外接する四角形を指定します。

### <a name="remarks"></a>解説

このメソッド `CMFCCaptionBar` を派生クラスでオーバーライドして、イメージの外観をカスタマイズします。

## <a name="cmfccaptionbarondrawtext"></a><a name="ondrawtext"></a> CMFCCaptionBar:: OnDrawText

キャプションバーのテキストを描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawText(
    CDC* pDC,
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からボタンを表示するために使用されるデバイスコンテキストへのポインター。

*rect*<br/>
からテキストの外接する四角形。

*strText*<br/>
から表示するテキスト文字列。

### <a name="remarks"></a>解説

既定の実装では、 `CDC::DrawText` と [CMFCCaptionBar:: m_clrBarText](#m_clrbartext) color を使用してテキストを表示します。

このメソッドを派生クラスでオーバーライドして、 `CMFCCaptionBar` キャプションバーのテキストの外観をカスタマイズします。

## <a name="cmfccaptionbarremovebitmap"></a><a name="removebitmap"></a> CMFCCaptionBar:: RemoveBitmap

キャプションバーからビットマップイメージを削除します。

```cpp
void RemoveBitmap();
```

## <a name="cmfccaptionbarremovebutton"></a><a name="removebutton"></a> CMFCCaptionBar:: RemoveButton

キャプションバーからボタンを削除します。

```cpp
void RemoveButton();
```

### <a name="remarks"></a>解説

キャプションバー要素のレイアウトは自動的に調整されます。

## <a name="cmfccaptionbarremoveicon"></a><a name="removeicon"></a> CMFCCaptionBar:: RemoveIcon

キャプションバーからアイコンを削除します。

```cpp
void RemoveIcon();
```

## <a name="cmfccaptionbarremovetext"></a><a name="removetext"></a> CMFCCaptionBar:: RemoveText

キャプションバーからテキストラベルを削除します。

```cpp
void RemoveText();
```

## <a name="cmfccaptionbarsetbitmap"></a><a name="setbitmap"></a> CMFCCaptionBar:: SetBitmap

キャプションバーのビットマップイメージを設定します。

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

*hBitmap*<br/>
から設定するビットマップへのハンドル。

*clrTransparent*<br/>
からビットマップの透明色を指定する RGB 値。

*bStretch*<br/>
からTRUE の場合、イメージの外接する四角形に適合しない場合はビットマップが拡大されます。 それ以外の場合、ビットマップは拡張されません。

*bmpAlignment*<br/>
からビットマップの配置。

### <a name="remarks"></a>解説

キャプションバーにビットマップを設定するには、このメソッドを使用します。

前のビットマップは自動的に破棄されます。 [CMFCCaptionBar:: SetIcon](#seticon)メソッドを呼び出したためにキャプションバーにアイコンが表示される場合、 [CMFCCaptionBar:: removeicon](#removeicon)を呼び出してアイコンを削除しない限り、ビットマップは表示されません。

ビットマップは、 *Bmpalignment* パラメーターによって指定されたとおりに配置されます。  このパラメーターには、次の `BarElementAlignment` 値のいずれかを指定できます。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetbordersize"></a><a name="setbordersize"></a> CMFCCaptionBar:: SetBorderSize

キャプションバーの境界線のサイズを設定します。

```cpp
void SetBorderSize(int nSize);
```

### <a name="parameters"></a>パラメーター

*nSize*<br/>
からキャプションバーの境界線の新しいサイズ (ピクセル単位)。

## <a name="cmfccaptionbarsetbutton"></a><a name="setbutton"></a> CMFCCaptionBar:: SetButton

キャプションバーのボタンを設定します。

```cpp
void SetButton(
    LPCTSTR lpszLabel,
    UINT uiCmdUI,
    BarElementAlignment btnAlignmnet=ALIGN_LEFT,
    BOOL bHasDropDownArrow=TRUE);
```

### <a name="parameters"></a>パラメーター

*lpszLabel*<br/>
ボタンのコマンドラベル。

*uiCmdUI*<br/>
ボタンのコマンド ID。

*btnAlignmnet*<br/>
ボタンの配置。

*bHasDropDownArrow*<br/>
ボタンにドロップダウン矢印が表示される場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfccaptionbarsetbuttonpressed"></a><a name="setbuttonpressed"></a> CMFCCaptionBar:: SetButtonPressed

ボタンが押されたままになるかどうかを指定します。

```cpp
void SetButtonPressed(BOOL bPresed=TRUE);
```

### <a name="parameters"></a>パラメーター

*bPresed*<br/>
ボタンが押された状態を維持する場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfccaptionbarsetbuttontooltip"></a><a name="setbuttontooltip"></a> CMFCCaptionBar:: SetButtonToolTip

ボタンのツールヒントを設定します。

```cpp
void SetButtonToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszToolTip*<br/>
からツールヒントのキャプション。

*lpszDescription*<br/>
からツールヒントの説明。

## <a name="cmfccaptionbarsetflatborder"></a><a name="setflatborder"></a> CMFCCaptionBar:: SetFlatBorder

キャプションバーの境界線スタイルを設定します。

```cpp
void SetFlatBorder(BOOL bFlat=TRUE);
```

### <a name="parameters"></a>パラメーター

*bFlat*<br/>
からキャプションバーの境界線がフラットである場合は TRUE。 境界線が3D の場合は FALSE。

## <a name="cmfccaptionbarseticon"></a><a name="seticon"></a> CMFCCaptionBar:: SetIcon

キャプションバーのアイコンを設定します。

```cpp
void SetIcon(
    HICON hIcon,
    BarElementAlignment iconAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>パラメーター

*hIcon*<br/>
から設定するアイコンへのハンドル。

*iconAlignment*<br/>
からアイコンの配置。

### <a name="remarks"></a>解説

キャプションバーには、アイコンまたはビットマップを表示できます。 ビットマップを表示する方法については、「 [CMFCCaptionBar:: SetBitmap](#setbitmap) 」を参照してください。 アイコンとビットマップの両方を設定した場合、アイコンは常に表示されます。 [CMFCCaptionBar:: RemoveIcon](#removeicon)を呼び出して、キャプションバーからアイコンを削除します。

アイコンは、 *Iconalignment* パラメーターに従って配置されます。 次のいずれかの値を指定でき `BarElementAlignment` ます。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="cmfccaptionbarsetimagetooltip"></a><a name="setimagetooltip"></a> CMFCCaptionBar:: SetImageToolTip

キャプションバーのイメージのツールヒントを設定します。

```cpp
void SetImageToolTip(
    LPCTSTR lpszToolTip,
    LPCTSTR lpszDescription=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszToolTip*<br/>
からツールヒントのテキスト。

*lpszDescription*<br/>
からツールヒントの説明。

## <a name="cmfccaptionbarsetmargin"></a><a name="setmargin"></a> CMFCCaptionBar:: SetMargin

キャプションバー要素の端とキャプションバーコントロールの端との距離を設定します。

```cpp
void SetMargin(int nMargin);
```

### <a name="parameters"></a>パラメーター

*nMargin*<br/>
からキャプションバー要素の端とキャプションバーコントロールの端との間の距離 (ピクセル単位)。

## <a name="cmfccaptionbarsettext"></a><a name="settext"></a> CMFCCaptionBar:: SetText

キャプションバーのテキストラベルを設定します。

```cpp
void SetText(
    const CString& strText,
    BarElementAlignment textAlignment=ALIGN_RIGHT);
```

### <a name="parameters"></a>パラメーター

*strText*<br/>
から設定する文字列。

*System.windows.media.formattedtext.textalignment*<br/>
からテキストの配置。

### <a name="remarks"></a>解説

テキストラベルは、 *Textalignment* パラメーターによって指定されたとおりに配置されます。 次のいずれかの値を指定でき `BarElementAlignment` ます。

- ALIGN_INVALID

- ALIGN_LEFT

- ALIGN_RIGHT

- ALIGN_CENTER

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
