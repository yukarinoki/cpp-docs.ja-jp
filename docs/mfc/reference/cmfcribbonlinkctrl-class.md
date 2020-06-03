---
title: クラス
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
ms.openlocfilehash: 3c0cbe843aac172464683288d61e2aec2af60b68
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753558"
---
# <a name="cmfcribbonlinkctrl-class"></a>クラス

リボン上に配置するハイパーリンクを実装します。 ハイパーリンクをクリックすると、Web ページが表示されます。
詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

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
|[CMFCRibbonLinkCtrl::GetCompactSize](#getcompactsize)|(オーバーライド[CMFCリボンボタン::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonLinkCtrl::GetLink](#getlink)|ハイパーリンクの値を返します。|
|[CMFCRibbonLinkCtrl::GetRegularSize](#getregularsize)|(オーバーライド[CMFCリボンボタン::取得レギュラーサイズ](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonLinkCtrl::GetToolTipText](#gettooltiptext)|([オーバーライドします。](../../mfc/reference/cmfcribbonbutton-class.md#gettooltiptext)|
|[CMFCRibbonLinkCtrl::IsDrawTooltipImage](#isdrawtooltipimage)|( `CMFCRibbonButton::IsDrawTooltipImage`をオーバーライドします)。|
|[CMFCRibbonLinkCtrl::OnDraw](#ondraw)|(オーバーライド[CMFCリボンボタン::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonLinkCtrl::OnDrawMenuImage](#ondrawmenuimage)|(オーバーライドします[。](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)|
|[CMFCRibbonLinkCtrl::OnMouseMove](#onmousemove)|( `CMFCRibbonButton::OnMouseMove`をオーバーライドします)。|
|[CMFCRibbonLinkCtrl::OnSetIcon](#onseticon)||
|[CMFCRibbonLinkCtrl::OpenLink](#openlink)|ハイパーリンクで指定されている Web ページを開きます。|
|[CMFCRibbonLinkCtrl::SetLink](#setlink)|ハイパーリンクの値を設定します。|

## <a name="remarks"></a>解説

ハイパーリンクを作成したら[、CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add)を呼び出してパネルに追加します。

## <a name="inheritance-hierarchy"></a>継承階層

[Cobject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CMFCリボンベース要素](../../mfc/reference/cmfcribbonbaseelement-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCリボンボタン](../../mfc/reference/cmfcribbonbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[CMFCリボンリンクCtrl](../../mfc/reference/cmfcribbonlinkctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxリボンリンクCtrl.h

## <a name="cmfcribbonlinkctrlcmfcribbonlinkctrl"></a><a name="cmfcribbonlinkctrl"></a>次の点に関する説明を行います。

[オブジェクトを](../../mfc/reference/cmfcribbonlinkctrl-class.md)構築して初期化します。

```
CMFCRibbonLinkCtrl(
    UINT nID,
    LPCTSTR lpszText,
    LPCTSTR lpszLink);
```

### <a name="parameters"></a>パラメーター

*nID*<br/>
[in]リンク コントロールがクリックされたときに実行されるコマンドのコマンド ID を指定します。

*lpszText*<br/>
[in]リンク コントロールに表示するラベルを指定します。

*リンクをクリックします。*<br/>
[in]リンク コントロールに関連付けられているハイパーリンクを指定します。

### <a name="example"></a>例

クラスのコンストラクターを使用する方法を次の例に`CMFCRibbonLinkCtrl`示します。 このコード スニペットは、[リボン ガジェットのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_RibbonGadgets#1](../../mfc/reference/codesnippet/cpp/cmfcribbonlinkctrl-class_1.cpp)]

## <a name="cmfcribbonlinkctrlcopyfrom"></a><a name="copyfrom"></a>次の点から

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>パラメーター

[in]*src*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgetcompactsize"></a><a name="getcompactsize"></a>次の値を取得します。

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgetlink"></a><a name="getlink"></a>次のリンクをクリックします。

ハイパーリンクの値を返します。

```
LPCTSTR GetLink() const;
```

### <a name="return-value"></a>戻り値

ハイパーリンクの現在の値。

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgetregularsize"></a><a name="getregularsize"></a>一連の値を取得します。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlgettooltiptext"></a><a name="gettooltiptext"></a>テキストを取得します。

```
virtual CString GetToolTipText() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlondrawmenuimage"></a><a name="ondrawmenuimage"></a>次の項目を選択します。

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>パラメーター

[in]*CDC&#42;*<br/>
[in]*クレスト*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>イメージを引き起します。

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlondraw"></a><a name="ondraw"></a>次の点に関する説明を行います。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

[in]*pDC*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlonmousemove"></a><a name="onmousemove"></a>マウスの移動

```
virtual void OnMouseMove(CPoint point);
```

### <a name="parameters"></a>パラメーター

[in]*ポイント*<br/>

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlonseticon"></a><a name="onseticon"></a>次の説明を行います。

```
virtual void OnSetIcon();
```

### <a name="remarks"></a>解説

## <a name="cmfcribbonlinkctrlopenlink"></a><a name="openlink"></a>次のリンクをクリックします。

ハイパーリンクで指定されている Web ページを開きます。

```
BOOL OpenLink();
```

### <a name="return-value"></a>戻り値

関連付けられた Web ページが正常に開かれた場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

オブジェクトに関連付けられたハイパーリンクを使用して`CMFCRibbonLinkCtrl`Web ページを開きます。

## <a name="cmfcribbonlinkctrlsetlink"></a><a name="setlink"></a>次のリンクをクリックします。

ハイパーリンクの値を設定します。

```cpp
void SetLink(LPCTSTR lpszLink);
```

### <a name="parameters"></a>パラメーター

*リンクをクリックします。*<br/>
[in]ハイパーリンク テキストを指定します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)
