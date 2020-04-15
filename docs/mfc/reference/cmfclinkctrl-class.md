---
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
ms.openlocfilehash: 1ef4e390d88f81d738d2ee18be6ba02843633011
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374401"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl クラス

この`CMFCLinkCtrl`クラスは、ボタンをハイパーリンクとして表示し、ボタンがクリックされたときにリンクのターゲットを呼び出します。

## <a name="syntax"></a>構文

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[をクリックします。](#seturl)|指定した URL をボタン テキストとして表示します。|
|[をクリックします。](#seturlprefix)|URL の暗黙的なプロトコル ("http:"など) を設定します。|
|[コンテンツのサイズ](#sizetocontent)|ボタンのテキストまたはビットマップを含むボタンのサイズを変更します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[次の点に関する情報が表示されます。](#ondrawfocusrect)|ボタンのフォーカス四角形が描画される前に、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

クラスから派生したボタンを`CMFCLinkCtrl`クリックすると、フレームワークはボタンの URL をパラメーターとしてメソッドに`ShellExecute`渡します。 その後`ShellExecute`、メソッドは URL のターゲットを開きます。

## <a name="example"></a>例

次の例は、`CMFCLinkCtrl`オブジェクトのサイズを設定する方法と、オブジェクト内の url とツールヒントを設定`CMFCLinkCtrl`する方法を示しています。 この例は、[新しいコントロールのサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxlinkctrl.h

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a>次の点に関する情報が表示されます。

ボタンのフォーカス四角形が描画される前に、フレームワークによって呼び出されます。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*レクトクライアント*<br/>
[in]リンク コントロールに境界を持つ四角形。

### <a name="remarks"></a>解説

独自のコードを使用してボタンのフォーカス四角形を描画する場合は、このメソッドをオーバーライドします。

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a>をクリックします。

指定した URL をボタン テキストとして表示します。

```
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>パラメーター

*を指定します。*<br/>
[in]表示するボタン テキスト。

### <a name="remarks"></a>解説

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a>をクリックします。

URL の暗黙的なプロトコル ("http:"など) を設定します。

```
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>パラメーター

*プレフィックス*<br/>
[in]URL プロトコルのプレフィックス。

### <a name="remarks"></a>解説

このメソッドは、URL プレフィックスを設定するために使います。 ボタンの顔にはプレフィックスは表示されませんが、URL のターゲットを参照するために使用できます。

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a>コンテンツのサイズ

ボタンのテキストまたはビットマップを含むボタンのサイズを変更します。

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>パラメーター

*bVセンター*<br/>
[in]リンク コントロールの上端と下端の間にボタン テキストとビットマップを垂直方向に中央揃えする場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

*bHセンター*<br/>
[in]リンク コントロールの左右の左右の間にボタン テキストとビットマップを水平方向に中央揃えする場合は TRUE。それ以外の場合は FALSE。 既定値は FALSE です。

### <a name="return-value"></a>戻り値

リンク コントロールの新しいサイズを格納する[CSize](../../atl-mfc-shared/reference/csize-class.md)オブジェクト。

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl クラス](../../mfc/reference/clinkctrl-class.md)<br/>
[クラス](../../mfc/reference/cmfcbutton-class.md)
