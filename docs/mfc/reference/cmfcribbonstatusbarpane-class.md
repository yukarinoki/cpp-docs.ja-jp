---
description: '詳細情報: CMFCRibbonStatusBarPane クラス'
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
ms.openlocfilehash: 4ddbee5a6c44411ef2ac34bff3e07b47c3d950a0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264987"
---
# <a name="cmfcribbonstatusbarpane-class"></a>CMFCRibbonStatusBarPane クラス

クラスは、リボン `CMFCRibbonStatusBarPane` のステータスバーに追加できるリボン要素を実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonStatusBarPane : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonStatusBarPane:: CMFCRibbonStatusBarPane](#cmfcribbonstatusbarpane)|`CMFCRibbonStatusBarPane` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonStatusBarPane:: GetAlmostLargeText](#getalmostlargetext)|切り捨てずにペインに表示できる最長のテキスト文字列を定義する文字列を返します。|
|[CMFCRibbonStatusBarPane:: GetTextAlign](#gettextalign)|テキストの配置の現在の設定を返します。|
|[CMFCRibbonStatusBarPane:: IsAnimation](#isanimation)|アニメーションが進行中かどうかを判断します。|
|[CMFCRibbonStatusBarPane:: IsExtended](#isextended)|リボンステータスバーの拡張領域にペインが配置されているかどうかを判断します。|
|[CMFCRibbonStatusBarPane:: OnDrawBorder](#ondrawborder)|( [CMFCRibbonButton:: OnDrawBorder](../../mfc/reference/cmfcribbonbutton-class.md#ondrawborder)をオーバーライドします。)|
|[CMFCRibbonStatusBarPane:: OnFillBackground](#onfillbackground)|( [CMFCRibbonButton:: OnFillBackground](../../mfc/reference/cmfcribbonbutton-class.md#onfillbackground)をオーバーライドします)。|
|[CMFCRibbonStatusBarPane:: SetAlmostLargeText](#setalmostlargetext)|切り捨てずにペインに表示できる最長のテキスト文字列を定義します。|
|[CMFCRibbonStatusBarPane:: Setアニメーションリスト](#setanimationlist)|アニメーションに使用できるイメージリストをペインに割り当てます。|
|[CMFCRibbonStatusBarPane:: SetTextAlign](#settextalign)|テキストの配置を設定します。|
|[CMFCRibbonStatusBarPane:: StartAnimation](#startanimation)|ペインに割り当てられているアニメーションを開始します。|
|[CMFCRibbonStatusBarPane:: StopAnimation](#stopanimation)|ペインに割り当てられているアニメーションを停止します。 .|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonStatusBarPane:: Onfinish アニメーション](#onfinishanimation)|ペインに割り当てられたアニメーションが停止したときに、フレームワークによって呼び出されます。|

## <a name="example"></a>例

次の例は、`CMFCRibbonStatusBarPane` クラスのさまざまなメソッドの使用方法を説明しています。 この例では、オブジェクトを構築する方法、 `CMFCRibbonStatusBarPane` ステータスバーペインのラベルのテキストの配置を設定する方法、ステータスバーペインに切り捨てずに表示できる最長のテキストを定義する方法、ステータスバーペインにアニメーションで使用できるイメージリストをアタッチする方法、およびアニメーションを開始する方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbarpane-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonstatusbarpane

## <a name="cmfcribbonstatusbarpanecmfcribbonstatusbarpane"></a><a name="cmfcribbonstatusbarpane"></a> CMFCRibbonStatusBarPane:: CMFCRibbonStatusBarPane

ステータスバーに pane オブジェクトを構築します。

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

*nCmdID*<br/>
からペインのコマンド ID を指定します。

*lpszText*<br/>
からウィンドウに表示するテキスト文字列を指定します。

*bIsStatic*<br/>
からTRUE の場合、ステータスウィンドウをクリックして強調表示または選択を行うことはできません。

*hIcon*<br/>
からペインに表示されるアイコンへのハンドルを指定します。

*lpszAlmostLargeText*<br/>
からペインで表示できる最長のテキスト文字列を指定します。

*hBmpAnimationList*<br/>
からアニメーションに使用するイメージリストのハンドルを指定します。

*cxAnimation*<br/>
からアニメーションに使用するイメージリストのアイコンの幅 (ピクセル単位) を指定します。

*clrTrnsp*<br/>
からアニメーションに使用されるイメージリスト内のイメージの透明色を指定します。

*Ui' Listresid '*<br/>
からアニメーションに使用するイメージリストのリソース ID を指定します。

## <a name="cmfcribbonstatusbarpanegetalmostlargetext"></a><a name="getalmostlargetext"></a> CMFCRibbonStatusBarPane:: GetAlmostLargeText

ステータスバーペインに表示できる最長のテキスト文字列を取得します。

```
LPCTSTR GetAlmostLargeText() const;
```

### <a name="return-value"></a>戻り値

ステータスバーペインに表示できる最長のテキスト文字列。

## <a name="cmfcribbonstatusbarpanegettextalign"></a><a name="gettextalign"></a> CMFCRibbonStatusBarPane:: GetTextAlign

ステータスバーペインのラベルのテキストの配置の現在の設定を取得します。

```
int GetTextAlign() const;
```

### <a name="return-value"></a>戻り値

現在のテキストの配置で、次のいずれかを指定できます。

- TA_LEFT

- TA_CENTER

- TA_RIGHT。

## <a name="cmfcribbonstatusbarpaneisanimation"></a><a name="isanimation"></a> CMFCRibbonStatusBarPane:: IsAnimation

アニメーションが進行中かどうかを判断します。

```
BOOL IsAnimation() const;
```

### <a name="return-value"></a>戻り値

アニメーションが進行中の場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarpaneisextended"></a><a name="isextended"></a> CMFCRibbonStatusBarPane:: IsExtended

リボンステータスバーの拡張領域にペインが配置されているかどうかを確認します。

```
BOOL IsExtended() const;
```

### <a name="return-value"></a>戻り値

ペインがステータスバーの拡張領域にある場合は TRUE。 それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarpaneondrawborder"></a><a name="ondrawborder"></a> CMFCRibbonStatusBarPane:: OnDrawBorder

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual void OnDrawBorder(CDC*);
```

### <a name="parameters"></a>パラメーター

から *CDC&#42;*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarpaneonfillbackground"></a><a name="onfillbackground"></a> CMFCRibbonStatusBarPane:: OnFillBackground

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual COLORREF OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarpaneonfinishanimation"></a><a name="onfinishanimation"></a> CMFCRibbonStatusBarPane:: Onfinish アニメーション

フレームワークは、ペインに割り当てられているアニメーションが終了したときに、このメソッドを呼び出します。

```
virtual void OnFinishAnimation();
```

### <a name="remarks"></a>解説

`StopAnimation` メソッドは `OnFinishAnimation` メソッドを呼び出します。このメソッドは、アニメーションが終了したときにデータをクリーンアップするために使用できます。

## <a name="cmfcribbonstatusbarpanesetalmostlargetext"></a><a name="setalmostlargetext"></a> CMFCRibbonStatusBarPane:: SetAlmostLargeText

[ステータスバー] ウィンドウに切り捨てずに表示できる最長のテキストを定義します。

```cpp
void SetAlmostLargeText(LPCTSTR lpszAlmostLargeText);
```

### <a name="parameters"></a>パラメーター

*lpszAlmostLargeText*<br/>
からステータスバーペインに切り捨てずに表示できる最長の文字列を指定します。

### <a name="remarks"></a>解説

ライブラリは、 *lpszAlmostLargeText* が指定するテキストのサイズを計算し、それに応じてペインのサイズを変更します。 テキストは、ウィンドウに表示されない場合は切り捨てられます。

## <a name="cmfcribbonstatusbarpanesetanimationlist"></a><a name="setanimationlist"></a> CMFCRibbonStatusBarPane:: Setアニメーションリスト

アニメーションに使用できるイメージリストをステータスバーペインにアタッチします。

```cpp
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

*hBmpAnimationList*<br/>
からイメージリストのハンドルを指定します。

*cxAnimation*<br/>
からイメージリスト内のフレームの幅をピクセル単位で指定します。

*clrTransp*<br/>
からイメージリストの透明色を指定します。

*Ui' Listresid '*<br/>
からイメージリストのリソース ID を指定します。

### <a name="return-value"></a>戻り値

イメージリストがステータスバーペインに正常にアタッチされている場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarpanesettextalign"></a><a name="settextalign"></a> CMFCRibbonStatusBarPane:: SetTextAlign

ステータスバーペインのラベルのテキストの配置を設定します。

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>パラメーター

*n Align*<br/>
からテキストの配置を指定します。

### <a name="remarks"></a>解説

*Nalign* には、次のいずれかの値を指定できます。

- TA_LEFT: 左揃え

- TA_CENTER: 中央揃え

- TA_RIGHT: 右揃え

## <a name="cmfcribbonstatusbarpanestartanimation"></a><a name="startanimation"></a> CMFCRibbonStatusBarPane:: StartAnimation

ペインに割り当てたアニメーションを開始します。

```cpp
void StartAnimation(
    UINT nFrameDelay=500,
    UINT nDuration=-1);
```

### <a name="parameters"></a>パラメーター

*Nフレーム遅延*<br/>
からアニメーションフレームレートをミリ秒単位で指定します。

*nDuration*<br/>
からアニメーションの再生時間をミリ秒単位で指定します。 無限ループの場合は-1 を使用します。

### <a name="remarks"></a>解説

を使用してを呼び出す前に、イメージリストへのハンドルを指定する必要があり `StartAnimation` `SetAnimationList` ます。

## <a name="cmfcribbonstatusbarpanestopanimation"></a><a name="stopanimation"></a> CMFCRibbonStatusBarPane:: StopAnimation

ステータスバーペインに割り当てたアニメーションを停止します。

```cpp
void StopAnimation();
```

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonStatusBar クラス](../../mfc/reference/cmfcribbonstatusbar-class.md)
