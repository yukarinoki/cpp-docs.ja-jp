---
title: CMFCSpinButtonCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 445b857400d8c82109ca7220b84bac692a2abf89
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376176"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl クラス

この`CMFCSpinButtonCtrl`クラスは、スピン ボタン コントロールを描画するビジュアル マネージャーをサポートします。

## <a name="syntax"></a>構文

```
class CMFCSpinButtonCtrl : public CSpinButtonCtrl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|`CMFCSpinButtonCtrl::CMFCSpinButtonCtrl`|既定のコンストラクターです。|
|`CMFCSpinButtonCtrl::~CMFCSpinButtonCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCスピンボタンCtrl::オンドロー](#ondraw)|現在のスピン ボタン コントロールを再描画します。|

## <a name="remarks"></a>解説

ビジュアル マネージャーを使用してアプリケーションでスピン ボタン コントロールを描画するには、クラスのすべてのインスタンスを`CSpinButtonCtrl`クラスに`CMFCSpinButtonCtrl`置き換えます。

## <a name="example"></a>例

クラスのオブジェクトを作成し、そのメソッドを使用する`CMFCSpinButtonCtrl`方法を次の`Create`例に示します。

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxspinbuttonctrl.h

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a>CMFCスピンボタンCtrl::オンドロー

現在のスピン ボタン コントロールを再描画します。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

フレームワークは`CMFCSpinButtonCtrl::OnPaint`[、CWnd::OnPaint](../../mfc/reference/cwnd-class.md#onpaint)メッセージを処理するメソッドを呼び出し、そのメソッド`CMFCSpinButtonCtrl::OnDraw`はこのメソッドを呼び出します。 フレームワークがスピン ボタン コントロールを描画する方法をカスタマイズするには、このメソッドをオーバーライドします。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcvisualmanager-class.md)
