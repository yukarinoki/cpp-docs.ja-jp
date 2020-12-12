---
description: '詳細情報: CMFCRibbonLinkCtrl クラス'
title: CMFCRibbonLinkCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::CopyFrom
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetCompactSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetRegularSize
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::GetToolTipText
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::IsDrawTooltipImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDraw
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnDrawMenuImage
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnMouseMove
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OnSetIcon
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::OpenLink
- AFXRIBBONLINKCTRL/CMFCRibbonLinkCtrl::SetLink
helpviewer_keywords:
- CMFCRibbonLinkCtrl [MFC], CMFCRibbonLinkCtrl
- CMFCRibbonLinkCtrl [MFC], CopyFrom
- CMFCRibbonLinkCtrl [MFC], GetCompactSize
- CMFCRibbonLinkCtrl [MFC], GetLink
- CMFCRibbonLinkCtrl [MFC], GetRegularSize
- CMFCRibbonLinkCtrl [MFC], GetToolTipText
- CMFCRibbonLinkCtrl [MFC], IsDrawTooltipImage
- CMFCRibbonLinkCtrl [MFC], OnDraw
- CMFCRibbonLinkCtrl [MFC], OnDrawMenuImage
- CMFCRibbonLinkCtrl [MFC], OnMouseMove
- CMFCRibbonLinkCtrl [MFC], OnSetIcon
- CMFCRibbonLinkCtrl [MFC], OpenLink
- CMFCRibbonLinkCtrl [MFC], SetLink
ms.assetid: 77ae1941-e0ab-4a9d-911e-1752d34c079b
ms.openlocfilehash: 19b10643fa1af25dae4a5dc888f61d1c9ecaaee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321788"
---
# <a name="cmfcribbonlinkctrl-class"></a>CMFCRibbonLinkCtrl クラス

リボン上に配置するハイパーリンクを実装します。 ハイパーリンクをクリックすると、Web ページが表示されます。
詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

## <a name="syntax"></a>構文

```
class CMFCRibbonLinkCtrl : public CMFCRibbonButton
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl](#cmfcribbonlinkctrl)|`CMFCRibbonLinkCtrl` オブジェクトを構築して初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonLinkCtrl::CopyFrom](#copyfrom)|( `CMFCRibbonButton::CopyFrom`をオーバーライドします)。|
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|( [CMFCRibbonButton:: GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize)をオーバーライドします。)|
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|ハイパーリンクの値を返します。|
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|( [CMFCRibbonButton:: GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize)をオーバーライドします。)|
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|( [CMFCRibbonButton:: GetToolTipText](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext)をオーバーライドします。)|
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`をオーバーライドします)。|
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|( [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)をオーバーライドします)。|
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|( [CMFCRibbonBaseElement:: OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)をオーバーライドします。)|
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|( `CMFCRibbonButton::OnMouseMove`をオーバーライドします)。|
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|ハイパーリンクで指定されている Web ページを開きます。|
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|ハイパーリンクの値を設定します。|

## <a name="remarks"></a>解説

ハイパーリンクを作成したら、 [CMFCRibbonPanel:: add](../../mfc/reference/cmfcribbonpanel-class.md#add)を呼び出してパネルに追加します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)\
└ &nbsp; [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxRibbonLinkCtrl

## <a name="cmfcribbonlinkctrlcmfcribbonlinkctrl"></a><a name="cmfcribbonlinkctrl"></a> CMFCRibbonLinkCtrl::CMFCRibbonLinkCtrl

[CMFCRibbonLinkCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)オブジェクトを構築し、初期化します。

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
からリンクコントロールがクリックされたときに実行されるコマンドのコマンド ID を指定します。

*lpszText*<br/>
からリンクコントロールに表示するラベルを指定します。

*lpszLink*<br/>
からリンクコントロールに関連付けられているハイパーリンクを指定します。

### <a name="example"></a>例

クラスのコンストラクターを使用する方法を次の例に示し `CMFCRibbonLinkCtrl` ます。 このコードスニペットは、リボンの [ガジェットサンプル](../../overview/visual-cpp-samples.md)に含まれています。

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

## <a name="cmfcribbonlinkctrlcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonLinkCtrl:: CopyFrom

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

から *src*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgetcompactsize"></a><a name="getcompactsize"></a> CMFCRibbonLinkCtrl:: GetCompactSize

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgetlink"></a><a name="getlink"></a> CMFCRibbonLinkCtrl:: GetLink

ハイパーリンクの値を返します。

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>戻り値

ハイパーリンクの現在の値。

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonLinkCtrl:: GetRegularSize

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgettooltiptext"></a><a name="gettooltiptext"></a> CMFCRibbonLinkCtrl:: GetToolTipText

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlondrawmenuimage"></a><a name="ondrawmenuimage"></a> CMFCRibbonLinkCtrl:: OnDrawMenuImage

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>パラメーター

から *CDC&#42;*<br/>
から *CRect*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a> CMFCRibbonLinkCtrl::IsDrawTooltipImage

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlondraw"></a><a name="ondraw"></a> CMFCRibbonLinkCtrl:: OnDraw

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

から *pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlonmousemove"></a><a name="onmousemove"></a> CMFCRibbonLinkCtrl:: OnMouseMove

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>パラメーター

から *ポイント*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlonseticon"></a><a name="onseticon"></a> CMFCRibbonLinkCtrl::OnSetIcon

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlopenlink"></a><a name="openlink"></a> CMFCRibbonLinkCtrl:: OpenLink

ハイパーリンクで指定されている Web ページを開きます。

```
BOOL OpenLink();
```

### <a name="return-value"></a>戻り値

関連付けられた web ページが正常に開かれた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトに関連付けられているハイパーリンクを使用して、web ページを開き `CMFCRibbonLinkCtrl` ます。

## <a name="cmfcribbonlinkctrlsetlink"></a><a name="setlink"></a> CMFCRibbonLinkCtrl:: SetLink

ハイパーリンクの値を設定します。

```cpp
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>パラメーター

*lpszLink*<br/>
からハイパーリンクのテキストを指定します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)
