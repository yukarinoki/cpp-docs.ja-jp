---
description: '詳細情報: CMFCCaptionButton クラス'
title: CMFCCaptionButton クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 6c3c1cbeea4a548f2951276b3ad43cb598cf22a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327754"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton クラス

クラスは、 `CMFCCaptionButton` ドッキングペインまたはミニフレームウィンドウのキャプションバーに表示されるボタンを実装します。 通常は、フレームワークがキャプション ボタンを自動的に作成します。

## <a name="syntax"></a>構文

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|ボタンによって表されるコマンドを返します。|
|[CMFCCaptionButton:: Geの Onid](#geticonid)|ボタンに関連付けられているイメージ ID を返します。|
|[CMFCCaptionButton:: GetRect](#getrect)|ボタンによって占有されている四角形を返します。|
|[CMFCCaptionButton:: GetSize](#getsize)|ボタンの幅と高さを返します。|
|[CMFCCaptionButton:: Isminiフレームボタン](#isminiframebutton)|タイトルバーの高さがミニサイズに設定されているかどうかを示します。|
|[CMFCCaptionButton:: Move](#move)|ボタンの描画位置とウィンドウの表示状態を設定します。|
|[CMFCCaptionButton:: OnDraw](#ondraw)|キャプションボタンを描画します。|
|[CMFCCaptionButton:: Setminiフレームボタン](#setminiframebutton)|タイトルバーのミニサイズを設定します。|

## <a name="remarks"></a>解説

[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)からクラスを派生させ、protected メソッドを使用して、 `AddButton` ミニフレームウィンドウにキャプションボタンを追加することができます。

CPaneFrameWnd は、次の2種類のキャプションボタンのコマンド Id を定義します。

- AFX_CAPTION_BTN_PIN。ドッキングペインが自動非表示モードをサポートしているときにピンボタンを表示します。

- AFX_CAPTION_BTN_CLOSE。ペインを閉じたり非表示にしたりするときに [ **閉じる** ] ボタンを表示します。

## <a name="example"></a>例

次の例では、オブジェクトを構築 `CMFCCaptionButton` し、タイトルバーのミニサイズを設定する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxcaptionbutton

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a> CMFCCaptionButton::CMFCCaptionButton

`CMFCCaptionButton` オブジェクトを構築します。

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>パラメーター

*nHit*<br/>
からボタンに関連付けられているコマンド。

*bLeftAlign*<br/>
からボタンを左揃えにするかどうかを指定します。

次の表に、 *Nhit* パラメーターに使用できる値を示します。

|値|コマンド|
|-----------|-------------|
|AFX_HTCLOSE|[閉じる] ボタン。|
|HTMINBUTTON|[最小化] ボタン。|
|HTMAXBUTTON|[最大化] ボタン。|
|AFX_HTLEFTBUTTON|左矢印ボタン。|
|AFX_HTRIGHTBUTTON|右矢印ボタン。|
|AFX_HTMENU|下矢印メニューボタン。|
|HTNOWHERE|既定値。コマンドを表しません。|

### <a name="remarks"></a>解説

既定では、キャプションボタンはコマンドに関連付けられていません。

キャプションボタンは、右または左に揃えられます。

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a> CMFCCaptionButton::GetHit

ボタンによって表されるコマンドを返します。

```
UINT GetHit() const;
```

### <a name="return-value"></a>戻り値

ボタンによって表されるコマンドです。

次の表に、使用可能な戻り値の一覧を示します。

|値|コマンド|
|-----------|-------------|
|AFX_HTCLOSE|[閉じる] ボタン。|
|HTMINBUTTON|[最小化] ボタン。|
|HTMAXBUTTON|[最大化] ボタン。|
|AFX_HTLEFTBUTTON|左矢印ボタン。|
|AFX_HTRIGHTBUTTON|右矢印ボタン。|
|AFX_HTMENU|下矢印メニューボタン。|
|HTNOWHERE|既定値。コマンドを表しません。|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a> CMFCCaptionButton:: Geの Onid

ボタンに関連付けられているイメージ ID を返します。

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>パラメーター

*bHorz*<br/>
から左または右方向のイメージ Id の場合は TRUE。上矢印または下矢印のイメージ Id の場合は FALSE。

*bMaximized*<br/>
からイメージ ID を最大化する場合は TRUE です。イメージ ID を最小化する場合は FALSE。

### <a name="return-value"></a>戻り値

イメージ ID。

### <a name="remarks"></a>解説

これらのパラメーターは、キャプションボタンを最小化または最大化するためのイメージ Id を指定します。

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a> CMFCCaptionButton:: GetRect

ボタンによって占有されている四角形を返します。

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>戻り値

ボタンの位置を表す四角形。

### <a name="remarks"></a>解説

ボタンが表示されない場合は、返されるサイズは0です。

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a> CMFCCaptionButton:: GetSize

ボタンの幅と高さを返します。

```
static CSize GetSize();
```

### <a name="return-value"></a>戻り値

ボタンの外側の次元。

### <a name="remarks"></a>解説

返されるサイズには、ボタンの余白と境界線が含まれます。

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a> CMFCCaptionButton:: Isminiフレームボタン

タイトルバーの高さがミニサイズに設定されているかどうかを示します。

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>戻り値

キャプションがミニサイズに設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a> CMFCCaptionButton:: Move

ボタンの描画位置とウィンドウの表示状態を設定します。

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

*ptTo*<br/>
から新しい場所。

*bHide*<br/>
からボタンを表示するかどうかを指定します。

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a> CMFCCaptionButton:: OnDraw

キャプションボタンを描画します。

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からボタンのデバイスコンテキストへのポインター。

*bActive*<br/>
からアクティブなボタンイメージを描画するかどうかを指定します。

*bHorz*<br/>
から派生クラスで使用するために予約されています。

*bMaximized*<br/>
から最大化されたボタンイメージを描画するかどうかを指定します。

*bDisabled*<br/>
から有効なボタンイメージを描画するかどうかを指定します。

### <a name="remarks"></a>解説

ボタンが最大化ボタンまたは最小化ボタンの場合、 *bmaximized* パラメーターが使用されます。

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a> CMFCCaptionButton:: Setminiフレームボタン

タイトルバーのミニサイズを設定します。

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

*bSet*<br/>
からミニタイトルバーの高さの場合は TRUE。既定のタイトルバーの高さの場合は FALSE。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
