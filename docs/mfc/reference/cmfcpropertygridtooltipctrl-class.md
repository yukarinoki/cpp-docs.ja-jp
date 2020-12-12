---
description: '詳細情報: CMFCPropertyGridToolTipCtrl クラス'
title: CMFCPropertyGridToolTipCtrl クラス
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
ms.openlocfilehash: 5e560d09756be99c00257c351b58223b37a6b5da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289882"
---
# <a name="cmfcpropertygridtooltipctrl-class"></a>CMFCPropertyGridToolTipCtrl クラス

[Cmfcpropertygridctrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)がツールヒントを表示するために使用するツールヒントコントロールを実装します。

## <a name="syntax"></a>構文

```
class CMFCPropertyGridToolTipCtrl : public CWnd
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|-|-|
|[CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl](#cmfcpropertygridtooltipctrl)|`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。|
|`CMFCPropertyGridToolTipCtrl::~CMFCPropertyGridToolTipCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|-|-|
|[CMFCPropertyGridToolTipCtrl:: Create](#create)|ツールヒントコントロールのウィンドウを作成します。|
|[CMFCPropertyGridToolTipCtrl::D eactivate](#deactivate)|ツールヒントコントロールを非アクティブにして非表示にします。|
|[CMFCPropertyGridToolTipCtrl:: GetLastRect](#getlastrect)|ツールヒントコントロールの最後の位置の座標を返します。|
|[CMFCPropertyGridToolTipCtrl:: Hide](#hide)|ツールヒントコントロールを非表示にします。|
|`CMFCPropertyGridToolTipCtrl::PreTranslateMessage`|[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)および[DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 関数にディスパッチされる前に、ウィンドウメッセージを変換するためにクラス[CWinApp](../../mfc/reference/cwinapp-class.md)によって使用されます。 ( [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)をオーバーライドします)。|
|[CMFCPropertyGridToolTipCtrl:: SetTextMargin](#settextmargin)|ツールヒントのテキストと、ツールヒントウィンドウの境界線との間隔を設定します。|
|[CMFCPropertyGridToolTipCtrl:: Track](#track)|ツールヒントコントロールを表示します。|

## <a name="remarks"></a>解説

ポインターをプロパティ名の上に置くと、ツールヒントが表示されます。 [CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)クラスは、ユーザーが簡単に読めるようにツールヒントを表示します。 通常、ツールヒントの位置は、ポインターの位置によって決まります。 このクラスを使用すると、プロパティ名の上にツールヒントが表示され、プロパティ名が完全に表示されます。

MFC は、このコントロールを自動的に作成し、 [Cmfcpropertygridctrl クラス](../../mfc/reference/cmfcpropertygridctrl-class.md)で使用します。

## <a name="example"></a>例

クラスのオブジェクトを構築する方法 `CMFCPropertyGridToolTipCtrl` と、ツールヒントコントロールを表示する方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#23](../../mfc/reference/codesnippet/cpp/cmfcpropertygridtooltipctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CMFCPropertyGridToolTipCtrl](../../mfc/reference/cmfcpropertygridtooltipctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxpropertygridtooltipctrl

## <a name="cmfcpropertygridtooltipctrlcmfcpropertygridtooltipctrl"></a><a name="cmfcpropertygridtooltipctrl"></a> CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl

`CMFCPropertyGridToolTipCtrl` オブジェクトを構築します。

```
CMFCPropertyGridToolTipCtrl::CMFCPropertyGridToolTipCtrl();
```

## <a name="cmfcpropertygridtooltipctrlcreate"></a><a name="create"></a> CMFCPropertyGridToolTipCtrl:: Create

ツールヒントコントロールのウィンドウを作成します。

```
BOOL Create(CWnd* pWndParent);
```

### <a name="parameters"></a>パラメーター

*pWndParent*<br/>
から親ウィンドウへのポインター。

### <a name="return-value"></a>戻り値

ウィンドウが正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcpropertygridtooltipctrldeactivate"></a><a name="deactivate"></a> CMFCPropertyGridToolTipCtrl::D eactivate

ツールヒントコントロールを非アクティブにして非表示にします。

```cpp
void Deactivate();
```

### <a name="remarks"></a>解説

このメソッドは、最後の位置とテキストを空の値に設定します。これにより、 [CMFCPropertyGridToolTipCtrl:: Track](#track) の後続の呼び出しでツールヒントが表示されます。

## <a name="cmfcpropertygridtooltipctrlgetlastrect"></a><a name="getlastrect"></a> CMFCPropertyGridToolTipCtrl:: GetLastRect

ツールヒントコントロールの最後の位置の座標を返します。

```cpp
void GetLastRect(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
入出力ツールヒントコントロールの最後の位置を格納します。

## <a name="cmfcpropertygridtooltipctrlhide"></a><a name="hide"></a> CMFCPropertyGridToolTipCtrl:: Hide

ツールヒントコントロールを非表示にします。

```cpp
void Hide();
```

## <a name="cmfcpropertygridtooltipctrlsettextmargin"></a><a name="settextmargin"></a> CMFCPropertyGridToolTipCtrl:: SetTextMargin

ツールヒントのテキストと、ツールヒントウィンドウの境界線との間隔を設定します。

```cpp
void SetTextMargin(int nTextMargin);
```

### <a name="parameters"></a>パラメーター

*nTextMargin*<br/>
からツールヒントコントロールのテキストと、ツールヒントウィンドウの境界線との間隔を指定します。 既定値は10ピクセルです。

## <a name="cmfcpropertygridtooltipctrltrack"></a><a name="track"></a> CMFCPropertyGridToolTipCtrl:: Track

ツールヒントコントロールを表示します。

```cpp
void Track(
    CRect rect,
    const CString& strText);
```

### <a name="parameters"></a>パラメーター

*rect*<br/>
からツールヒントコントロールの位置とサイズを指定します。

*strText*<br/>
からツールヒントに表示されるテキストを指定します。

### <a name="remarks"></a>解説

このメソッドは、 *rect* によって指定された位置とサイズにツールヒントコントロールを表示します。 このメソッドが最後に呼び出されてから位置、サイズ、およびテキストが変更されていない場合、このメソッドは無効です。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
