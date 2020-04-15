---
title: CMFCRibbonStatusBarPane クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::GetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::IsExtended
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnDrawBorder
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFillBackground
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAlmostLargeText
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetAnimationList
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::SetTextAlign
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StartAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::StopAnimation
- AFXRIBBONSTATUSBARPANE/CMFCRibbonStatusBarPane::OnFinishAnimation
helpviewer_keywords:
- CMFCRibbonStatusBarPane [MFC], CMFCRibbonStatusBarPane
- CMFCRibbonStatusBarPane [MFC], GetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], GetTextAlign
- CMFCRibbonStatusBarPane [MFC], IsAnimation
- CMFCRibbonStatusBarPane [MFC], IsExtended
- CMFCRibbonStatusBarPane [MFC], OnDrawBorder
- CMFCRibbonStatusBarPane [MFC], OnFillBackground
- CMFCRibbonStatusBarPane [MFC], SetAlmostLargeText
- CMFCRibbonStatusBarPane [MFC], SetAnimationList
- CMFCRibbonStatusBarPane [MFC], SetTextAlign
- CMFCRibbonStatusBarPane [MFC], StartAnimation
- CMFCRibbonStatusBarPane [MFC], StopAnimation
- CMFCRibbonStatusBarPane [MFC], OnFinishAnimation
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
ms.openlocfilehash: 554b9fe364c6a213e038416a605c17cdd4f8e7d9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368795"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane クラス

この`CMFCRibbonStatusBarPane`クラスは、リボン ステータス バーに追加できるリボン要素を実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[バー ペイン::CMFCリボンステータスバーペイン](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[バーペイン::ほとんど大きいテキストを取得します。](#getalmostlargetext)|ウィンドウに切り捨てなしで表示できる最長のテキスト文字列を定義する文字列を返します。|
|[バーペイン::テキスト整列](#gettextalign)|テキストの配置の現在の設定を返します。|
|[バー ペイン::アニメーション](#isanimation)|アニメーションが進行中かどうかを判断します。|
|[バー ペイン::拡張](#isextended)|ペインがリボン ステータス バーの拡張領域にあるかどうかを判断します。|
|[バーペイン::オンドローボーダー](#ondrawborder)|(オーバーライド[CMFCリボンボタン::オンドローボーダー](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder).)|
|[バーペイン::オンフィルバックグラウンド](#onfillbackground)|(オーバーライド[CMFCリボンボタン::オンフィルバックグラウンド](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground).)|
|[バー ペイン::ほぼ大きいテキスト](#setalmostlargetext)|切り捨てなしでペインに表示できる最長のテキスト文字列を定義します。|
|[バーペイン::アニメーションリスト](#setanimationlist)|アニメーションに使用できるイメージ リストをペインに割り当てます。|
|[コントロール バー ペイン::テキスト整列](#settextalign)|テキストの配置を設定します。|
|[バー ペイン::開始アニメーション](#startanimation)|ペインに割り当てられているアニメーションを開始します。|
|[バーペイン::ストップアニメーション](#stopanimation)|ペインに割り当てられているアニメーションを停止します。 .|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[バーペイン::オンフィニッシュアニメーション](#onfinishanimation)|ペインに割り当てられたアニメーションが停止したときに、フレームワークによって呼び出されます。|

## <a name="example"></a>例

次の例は、`CMFCRibbonStatusBarPane` クラスのさまざまなメソッドの使用方法を説明しています。 この例では、`CMFCRibbonStatusBarPane`オブジェクトの作成方法、ステータス バー ペインのラベルのテキスト配置の設定、切り捨てなしでステータス バー ペインに表示できる最長のテキストの定義、ステータス バー ペインにアニメーションに使用できるイメージ リストの追加、アニメーションの開始方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbon ステータスバーペイン.h

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a>バー ペイン::CMFCリボンステータスバーペイン

ステータス バーにペイン オブジェクトを作成します。

```
CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    BOOL bIsStatic=FALSE,
    HICON hIcon=NULL,
    LPCTSTR lpszAlmostLargeText=NULL);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192,192 1,192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);

CMFCRibbonStatusBarPane(
    UINT nCmdID,
    LPCTSTR lpszText,
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTrnsp=RGB(192, 192 1, 192) 1,
    HICON hIcon=NULL,
    BOOL bIsStatic=FALSE);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
[in]ペインのコマンド ID を指定します。

*lpszText*<br/>
[in]ペインに表示するテキスト文字列を指定します。

*ビスタニブル*<br/>
[in]TRUE の場合、ステータス ペインをクリックしても強調表示または選択できません。

*Hicon*<br/>
[in]ペインに表示するアイコンへのハンドルを指定します。

*テキストをほぼ大きくします。*<br/>
[in]ペインで表示できる最長のテキスト文字列を指定します。

*一覧*<br/>
[in]アニメーションに使用するイメージ リストへのハンドルを指定します。

*アニメーション*<br/>
[in]アニメーションに使用するイメージ リスト内のアイコンの幅をピクセル単位で指定します。

*を使用します。*<br/>
[in]アニメーションに使用するイメージ リスト内のイメージの透明色を指定します。

*を返します。*<br/>
[in]アニメーションに使用するイメージ リストのリソース ID を指定します。

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a>バーペイン::ほとんど大きいテキストを取得します。

ステータス バー ペインに表示できる最長のテキスト文字列を取得します。

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>戻り値

ステータス バー ペインに表示できる最長のテキスト文字列。

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a>バーペイン::テキスト整列

ステータス バー ペインのラベルのテキスト配置の現在の設定を取得します。

```
int GetTextAlign() const;
```

### <a name="return-value"></a>戻り値

現在のテキストの配置は、次のいずれかになります。

- TA_LEFT

- TA_CENTER

- TA_RIGHT。

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a>バー ペイン::アニメーション

アニメーションが進行中かどうかを判断します。

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>戻り値

アニメーションが進行中の場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a>バー ペイン::拡張

ペインがリボン ステータス バーの拡張領域にあるかどうかを確認します。

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>戻り値

ウィンドウがステータス バーの拡張領域にある場合は TRUE。 それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a>バーペイン::オンドローボーダー

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>パラメーター

[in]*CDC&#42;*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a>バーペイン::オンフィルバックグラウンド

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a>バーペイン::オンフィニッシュアニメーション

フレームワークは、ペインに割り当てられているアニメーションが終了したときにこのメソッドを呼び出します。

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>解説

`StopAnimation`メソッドはメソッド`OnFinishAnimation`を呼び出し、アニメーション終了時にデータをクリーンアップするために使用できます。

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a>バー ペイン::ほぼ大きいテキスト

切り捨てなしでステータス バー ペインに表示できる最長のテキストを定義します。

```
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>パラメーター

*テキストをほぼ大きくします。*<br/>
[in]切り捨てなしでステータス バー ペインに表示できる最長の文字列を指定します。

### <a name="remarks"></a>解説

ライブラリは *、lpszほぼLargeText*が指定し、それに応じてペインのサイズを変更するテキストのサイズを計算します。 テキストがウィンドウに収まらない場合、テキストは切り捨てられます。

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a>バーペイン::アニメーションリスト

ステータス バー ペインに、アニメーションに使用できるイメージ リストをアタッチします。

```
void SetAnimationList(
    HBITMAP hBmpAnimationList,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);

BOOL SetAnimationList(
    UINT uiAnimationListResID,
    int cxAnimation=16,
    COLORREF clrTransp=RGB(192, 192 1, 192) 1);
```

### <a name="parameters"></a>パラメーター

*一覧*<br/>
[in]イメージ リストへのハンドルを指定します。

*アニメーション*<br/>
[in]イメージ リスト内のフレームの幅をピクセル単位で指定します。

*clrトランスプ*<br/>
[in]イメージ リストの透明色を指定します。

*を返します。*<br/>
[in]イメージ リストのリソース ID を指定します。

### <a name="return-value"></a>戻り値

イメージ リストがステータス バー ペインに正常にアタッチされた場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a>コントロール バー ペイン::テキスト整列

ステータス バー ペインのラベルのテキストの配置を設定します。

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>パラメーター

*nAlign*<br/>
[in]テキストの配置を指定します。

### <a name="remarks"></a>解説

*nAlign*には、次のいずれかの値を指定できます。

- TA_LEFT: 左揃え

- TA_CENTER: 中央揃え

- TA_RIGHT: 右揃え

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a>バー ペイン::開始アニメーション

ペインに割り当てるアニメーションを開始します。

```
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>パラメーター

*フレームディレイ*<br/>
[in]アニメーションのフレーム レートをミリ秒単位で指定します。

*n期間*<br/>
[in]アニメーションの再生時間をミリ秒単位で指定します。 無限ループの場合は-1 を使用します。

### <a name="remarks"></a>解説

を使用`StartAnimation``SetAnimationList`して呼び出す前に、イメージ リストへのハンドルを指定する必要があります。

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a>バーペイン::ストップアニメーション

ステータス バー ペインに割り当てたアニメーションを停止します。

```
void StopAnimation();
```

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar クラス](../../mfc/reference/cmfcribbonstatusbar-class.md)
