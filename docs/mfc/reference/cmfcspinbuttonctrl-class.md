---
description: '詳細情報: CMFCSpinButtonCtrl クラス'
title: CMFCSpinButtonCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl
- AFXSPINBUTTONCTRL/CMFCSpinButtonCtrl::OnDraw
helpviewer_keywords:
- CMFCSpinButtonCtrl [MFC], OnDraw
ms.assetid: 8773f259-4d3f-4bca-a71c-09e0c71bc843
ms.openlocfilehash: 87e9abc94247416704ab801beeaa1953c4cceb46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339637"
---
# <a name="cmfcspinbuttonctrl-class"></a>CMFCSpinButtonCtrl クラス

クラスは、 `CMFCSpinButtonCtrl` スピンボタンコントロールを描画するビジュアルマネージャーをサポートしています。

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
|[CMFCSpinButtonCtrl:: OnDraw](#ondraw)|現在のスピンボタンコントロールを再描画します。|

## <a name="remarks"></a>解説

ビジュアルマネージャーを使用して、アプリケーションにスピンボタンコントロールを描画するには、クラスのすべてのインスタンスを `CSpinButtonCtrl` クラスに置き換え `CMFCSpinButtonCtrl` ます。

## <a name="example"></a>例

次の例は、クラスのオブジェクトを作成し、そのメソッドを使用する方法を示して `CMFCSpinButtonCtrl` `Create` います。

[!code-cpp[NVC_MFC_RibbonApp#25](../../mfc/reference/codesnippet/cpp/cmfcspinbuttonctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CSpinButtonCtrl](../../mfc/reference/cspinbuttonctrl-class.md)

[CMFCSpinButtonCtrl](../../mfc/reference/cmfcspinbuttonctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxspinbuttonctrl

## <a name="cmfcspinbuttonctrlondraw"></a><a name="ondraw"></a> CMFCSpinButtonCtrl:: OnDraw

現在のスピンボタンコントロールを再描画します。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

### <a name="remarks"></a>解説

フレームワークは、 `CMFCSpinButtonCtrl::OnPaint` [CWnd:: OnPaint](../../mfc/reference/cwnd-class.md#onpaint) メッセージを処理するメソッドを呼び出し、そのメソッドがこのメソッドを呼び出し `CMFCSpinButtonCtrl::OnDraw` ます。 このメソッドをオーバーライドして、フレームワークがスピンボタンコントロールを描画する方法をカスタマイズします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCVisualManager クラス](../../mfc/reference/cmfcvisualmanager-class.md)
