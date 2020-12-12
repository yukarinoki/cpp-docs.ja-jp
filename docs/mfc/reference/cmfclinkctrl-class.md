---
description: '詳細情報: CMFCLinkCtrl クラス'
title: CMFCLinkCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 6951f086ac99c4b8a8260a79ee08d54476694350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265221"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl クラス

クラスは、ボタン `CMFCLinkCtrl` をハイパーリンクとして表示し、ボタンがクリックされたときにリンクのターゲットを呼び出します。

## <a name="syntax"></a>構文

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCLinkCtrl:: SetURL](#seturl)|指定された URL をボタンテキストとして表示します。|
|[CMFCLinkCtrl:: SetURLPrefix](#seturlprefix)|URL の暗黙のプロトコル (たとえば、"http:") を設定します。|
|[CMFCLinkCtrl:: SizeToContent](#sizetocontent)|ボタンのテキストまたはビットマップを格納するようにボタンのサイズを変更します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|ボタンのフォーカスを示す四角形が描画される前に、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

クラスから派生したボタンをクリックすると、フレームワークによっ `CMFCLinkCtrl` て、ボタンの URL がパラメーターとしてメソッドに渡され `ShellExecute` ます。 次に、メソッドによって `ShellExecute` URL のターゲットが開かれます。

## <a name="example"></a>例

次の例は、オブジェクトのサイズを設定する方法と、オブジェクトの url とツールヒントを設定する方法を示して `CMFCLinkCtrl` `CMFCLinkCtrl` います。 この例は、「 [新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxlinkctrl

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a> CMFCLinkCtrl::OnDrawFocusRect

ボタンのフォーカスを示す四角形が描画される前に、フレームワークによって呼び出されます。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rectClient*<br/>
からリンクコントロールの境界となる四角形。

### <a name="remarks"></a>解説

独自のコードを使用してボタンのフォーカスを示す四角形を描画する場合は、このメソッドをオーバーライドします。

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a> CMFCLinkCtrl:: SetURL

指定された URL をボタンテキストとして表示します。

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>パラメーター

*lpszURL*<br/>
から表示するボタンテキスト。

### <a name="remarks"></a>解説

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a> CMFCLinkCtrl:: SetURLPrefix

URL の暗黙のプロトコル (たとえば、"http:") を設定します。

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>パラメーター

*lpszPrefix*<br/>
からURL プロトコルのプレフィックス。

### <a name="remarks"></a>解説

このメソッドを使用して、URL プレフィックスを設定します。 このプレフィックスはボタンの表面には表示されませんが、URL のターゲットを参照するために使用できます。

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a> CMFCLinkCtrl:: SizeToContent

ボタンのテキストまたはビットマップを格納するようにボタンのサイズを変更します。

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>パラメーター

*bVCenter*<br/>
からボタンのテキストとビットマップをリンクコントロールの上と下の中央に配置する場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

*bHCenter*<br/>
からボタンのテキストとビットマップをリンクコントロールの左右左右に中央揃えにする場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

### <a name="return-value"></a>戻り値

リンクコントロールの新しいサイズを格納している [CSize](../../atl-mfc-shared/reference/csize-class.md) オブジェクト。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl クラス](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton クラス](../../mfc/reference/cmfcbutton-class.md)
