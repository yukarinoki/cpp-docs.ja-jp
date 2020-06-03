---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Create
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Deactivate
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::GetLastRect
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Hide
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::SetTextMargin
- AFXPROPERTYGRIDTOOLTIPCTRL/CMFCPropertyGridToolTipCtrl::Track
helpviewer_keywords:
- CMFCPropertyGridToolTipCtrl [MFC], CMFCPropertyGridToolTipCtrl
- CMFCPropertyGridToolTipCtrl [MFC], Create
- CMFCPropertyGridToolTipCtrl [MFC], Deactivate
- CMFCPropertyGridToolTipCtrl [MFC], GetLastRect
- CMFCPropertyGridToolTipCtrl [MFC], Hide
- CMFCPropertyGridToolTipCtrl [MFC], SetTextMargin
- CMFCPropertyGridToolTipCtrl [MFC], Track
ms.assetid: 84b436e5-6695-4da0-9569-1a875e087711
ms.openlocfilehash: fc5d6d99c326fba7020e8c5040c3bf28d09f8f0a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754120"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>クラス

クラスがツール[ヒントを表示](../../mfc/reference/cmfcpropertygridctrl-class.md)するために使用するツールヒント コントロールを実装します。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|||
|-|-|
|名前|説明|
|[ツールヒントCtrl:::プロパティグリッドツールチップ](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|||
|-|-|
|名前|説明|
|[ツールヒントCtrl::作成](#create)|ツールヒント コントロールのウィンドウを作成します。|
|[ツールヒントCtrl::Dアクティブ化](#deactivate)|ツールヒント コントロールを非アクティブにして非表示にします。|
|[ツールヒントCtrl::ラストレック](#getlastrect)|ツールヒント コントロールの最後の位置の座標を返します。|
|[ツールヒントCtrl::非表示](#hide)|ツールヒント コントロールを非表示にします。|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|クラス[CWinApp](../../mfc/reference/cwinapp-class.md)がウィンドウ メッセージを変換するために使用し、[変換メッセージ](/windows/win32/api/winuser/nf-winuser-translatemessage)および[ディスパッチ メッセージ](/windows/win32/api/winuser/nf-winuser-dispatchmessage)Windows 関数にディスパッチします。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[ツールヒントCtrl::テキストマージンを設定します。](#settextmargin)|ツールヒントテキストとツールチップウィンドウの境界線との間隔を設定します。|
|[ツールヒントCtrl::トラック](#track)|ツールヒント コントロールを表示します。|

## <a name="remarks"></a>解説

ツールチップは、ポインタがプロパティ名の上に置かれているときに表示されます。 クラス[は](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)、ユーザーが簡単に読み取ることができるようにツールヒントを表示します。 通常、ツールチップの位置はポインタの位置によって決まります。 このクラスを使用すると、ツールヒントがプロパティ名の上に表示され、プロパティ名が完全に表示されるように、自然プロパティの拡張機能に似ています。

MFC は、このコントロールを自動的に作成し、クラスで使用[します](../../mfc/reference/cmfcpropertygridctrl-class.md)。

## <a name="example"></a>例

クラスのオブジェクトを構築する方法と、ツールヒント`CMFCPropertyGridToolTipCtrl`コントロールを表示する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[ツールヒント](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx プロパティ グリッドツールヒントctrl.h

## <a name="cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a>ツールヒントCtrl:::プロパティグリッドツールチップ

`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

## <a name="cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a>ツールヒントCtrl::作成

ツールヒント コントロールのウィンドウを作成します。

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*親の子*<br/>
[in]親ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

ウィンドウが正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a>ツールヒントCtrl::Dアクティブ化

ツールヒント コントロールを非アクティブにして非表示にします。

```cpp
void Deactivate();
```

### <a name="remarks"></a>解説

このメソッドは、最後の位置とテキストを空の値に設定し、今後の呼び出し[で CMFCPropertyGrid ツールヒントCtrl::トラックが](#track)ツールヒントを表示するようにします。

## <a name="cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a>ツールヒントCtrl::ラストレック

ツールヒント コントロールの最後の位置の座標を返します。

```cpp
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[アウト]ツールヒント コントロールの最後の位置を格納します。

## <a name="cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a>ツールヒントCtrl::非表示

ツールヒント コントロールを非表示にします。

```cpp
void Hide();
```

## <a name="cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a>ツールヒントCtrl::テキストマージンを設定します。

ツールヒントテキストとツールチップウィンドウの境界線との間隔を設定します。

```cpp
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>パラメーター

*テキストマージン*<br/>
[in]ツールヒント コントロール テキストとツールヒント ウィンドウの境界線との間隔を指定します。 既定値は 10 ピクセルです。

## <a name="cmfcpropertygridtooltipctrltrack"></a><a name="track"></a>ツールヒントCtrl::トラック

ツールヒント コントロールを表示します。

```cpp
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>パラメーター

*Rect*<br/>
[in]ツールヒント コントロールの位置とサイズを指定します。

*str テキスト*<br/>
[in]ツールヒントに表示するテキストを指定します。

### <a name="remarks"></a>解説

このメソッドは *、rect*で指定された位置とサイズでツールヒント コントロールを表示します。 このメソッドが最後に呼び出されてから位置、サイズ、およびテキストが変更されていない場合、このメソッドは無効です。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
