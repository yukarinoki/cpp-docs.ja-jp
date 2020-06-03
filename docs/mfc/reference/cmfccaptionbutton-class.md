---
title: クラス
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
ms.openlocfilehash: 1b0a999f1fd1e3df1b0a971220454397cead02a9
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752599"
---
# <a name="cmfccaptionbutton-class"></a>クラス

この`CMFCCaptionButton`クラスは、ドッキング ペインまたはミニフレーム ウィンドウのキャプション バーに表示されるボタンを実装します。 通常は、フレームワークがキャプション ボタンを自動的に作成します。

## <a name="syntax"></a>構文

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|----------|-----------------|
|[ボタン::CMFCキャプションボタン](#cmfccaptionbutton)|オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ボタン::ゲットヒット](#gethit)|ボタンによって表されるコマンドを返します。|
|[ボタン::ゲットアイコンID](#geticonid)|ボタンに関連付けられたイメージ ID を返します。|
|[ボタン::ゲットレック](#getrect)|ボタンが占める四角形を返します。|
|[ボタン::ゲットサイズ](#getsize)|ボタンの幅と高さを返します。|
|[ボタン::イズミニフレームボタン](#isminiframebutton)|タイトル バーの高さがミニ サイズに設定されているかどうかを示します。|
|[ボタン::移動](#move)|ボタンの描画位置とウィンドウの表示状態を設定します。|
|[ウィンドウスキャプションボタン::オンドロー](#ondraw)|キャプション ボタンを描画します。|
|[ボタン::セットミニフレームボタン](#setminiframebutton)|タイトル バーのミニ サイズを設定します。|

## <a name="remarks"></a>解説

[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)からクラスを派生させ、`AddButton`保護されたメソッド を使用して、ミニフレーム ウィンドウにキャプション ボタンを追加できます。

CPaneFrameWnd.h は、2 種類のキャプション ボタンのコマンド ID を定義します。

- AFX_CAPTION_BTN_PIN、 ドッキング ペインが自動非表示モードをサポートしている場合にピン ボタンを表示します。

- AFX_CAPTION_BTN_CLOSE: ウィンドウを閉じたり非表示にしたりできる場合に**閉じる**ボタンを表示します。

## <a name="example"></a>例

次の例は、`CMFCCaptionButton`オブジェクトを構築し、タイトル バーのミニ サイズを設定する方法を示しています。

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxキャプションボタン.h

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a>ボタン::CMFCキャプションボタン

`CMFCCaptionButton` オブジェクトを構築します。

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>パラメーター

*nヒット*<br/>
[in]ボタンに関連付けられているコマンド。

*左揃え*<br/>
[in]ボタンを左揃えにするかどうかを指定します。

次の表は *、nHit*パラメーターの値を示しています。

|値|command|
|-----------|-------------|
|AFX_HTCLOSE|閉じるボタン。|
|HTMINBUTTON|最小化ボタン。|
|HTマックスボタン|最大化ボタン。|
|AFX_HTLEFTBUTTON|左矢印ボタン|
|AFX_HTRIGHTBUTTON|右矢印ボタン。|
|AFX_HTMENU|下矢印メニューボタン|
|HTNOWHERE|既定値。はコマンドを表しません。|

### <a name="remarks"></a>解説

既定では、キャプション ボタンはコマンドに関連付けされません。

キャプション ボタンは、右または左に配置されます。

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a>ボタン::ゲットヒット

ボタンによって表されるコマンドを返します。

```
UINT GetHit() const;
```

### <a name="return-value"></a>戻り値

ボタンで表されるコマンド。

次の表に、返される可能性のある値を示します。

|値|command|
|-----------|-------------|
|AFX_HTCLOSE|閉じるボタン。|
|HTMINBUTTON|最小化ボタン。|
|HTマックスボタン|最大化ボタン。|
|AFX_HTLEFTBUTTON|左矢印ボタン|
|AFX_HTRIGHTBUTTON|右矢印ボタン。|
|AFX_HTMENU|下矢印メニューボタン|
|HTNOWHERE|既定値。はコマンドを表しません。|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a>ボタン::ゲットアイコンID

ボタンに関連付けられたイメージ ID を返します。

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>パラメーター

*bHorz*<br/>
[in]左矢印または右矢印のイメージ ID の場合は TRUE。上向きまたは下向き矢印のイメージ ID の場合は FALSE。

*b最大化*<br/>
[in]最大化イメージ ID の場合は TRUE。最小化イメージ ID の場合は FALSE。

### <a name="return-value"></a>戻り値

イメージ ID。

### <a name="remarks"></a>解説

パラメーターは、キャプション ボタンを最小化または最大化するためのイメージ ID を指定します。

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a>ボタン::ゲットレック

ボタンが占める四角形を返します。

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>戻り値

ボタンの位置を表す四角形。

### <a name="remarks"></a>解説

ボタンが表示されない場合、返されるサイズは 0 です。

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a>ボタン::ゲットサイズ

ボタンの幅と高さを返します。

```
static CSize GetSize();
```

### <a name="return-value"></a>戻り値

ボタンの外側のサイズ。

### <a name="remarks"></a>解説

返されるサイズには、ボタンの余白と境界線が含まれます。

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a>ボタン::イズミニフレームボタン

タイトル バーの高さがミニ サイズに設定されているかどうかを示します。

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>戻り値

キャプションがミニ サイズに設定されている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a>ボタン::移動

ボタンの描画位置とウィンドウの表示状態を設定します。

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>パラメーター

*ptTo*<br/>
[in]新しい場所。

*bHide*<br/>
[in]ボタンを表示するかどうか。

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a>ウィンドウスキャプションボタン::オンドロー

キャプション ボタンを描画します。

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
[in]ボタンのデバイス コンテキストへのポインター。

*bアクティブ*<br/>
[in]アクティブなボタン イメージを描画するかどうか。

*bHorz*<br/>
[in]派生クラスで使用するために予約されています。

*b最大化*<br/>
[in]最大化されたボタン イメージを描画するかどうか。

*b無効*<br/>
[in]有効なボタン イメージを描画するかどうか。

### <a name="remarks"></a>解説

*bMaximized*パラメーターは、ボタンが最大化ボタンまたは最小化ボタンの場合に使用されます。

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a>ボタン::セットミニフレームボタン

タイトル バーのミニ サイズを設定します。

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>パラメーター

*bセット*<br/>
[in]ミニ タイトル バーの高さについては TRUE。既定のタイトル バーの高さについては、FALSE を指定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd クラス](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane クラス](../../mfc/reference/cdockablepane-class.md)
