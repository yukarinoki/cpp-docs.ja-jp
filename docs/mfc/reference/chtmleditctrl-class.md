---
title: CHtmlEditCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::CHtmlEditCtrl
- AFXHTML/CHtmlEditCtrl::Create
- AFXHTML/CHtmlEditCtrl::GetDHtmlDocument
- AFXHTML/CHtmlEditCtrl::GetStartDocument
helpviewer_keywords:
- CHtmlEditCtrl [MFC], CHtmlEditCtrl
- CHtmlEditCtrl [MFC], Create
- CHtmlEditCtrl [MFC], GetDHtmlDocument
- CHtmlEditCtrl [MFC], GetStartDocument
ms.assetid: 0fc4a238-b05f-4874-9edc-6a6701f064d9
ms.openlocfilehash: 05063c62e9f7a5d88d3fecde842f979725200f98
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366842"
---
# <a name="chtmleditctrl-class"></a>CHtmlEditCtrl クラス

MFC ウィンドウ内の WebBrowser ActiveX コントロールの機能が用意されています。

## <a name="syntax"></a>構文

```
class CHtmlEditCtrl: public CWnd,
    public CHtmlEditCtrlBase<CHtmlEditCtrl>
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の行](#chtmleditctrl)|`CHtmlEditCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[作成](#create)|ActiveX コントロールを作成し、オブジェクトに`CHtmlEditCtrl`アタッチします。 この関数は、自動的に WebBrowser ActiveX コントロールを編集モードにします。|
|[ドキュメントを編集します。](#getdhtmldocument)|現在含まれている WebBrowser コントロールに読み込まれているドキュメントの[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))インターフェイスを取得します。|
|[ドキュメントを取得します。](#getstartdocument)|含まれている WebBrowser コントロールに読み込む既定のドキュメントの URL を取得します。|

## <a name="remarks"></a>解説

ホストされた WebBrowser コントロールは、作成後に自動的に編集モードに移行します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxhtml.h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a>次の行

`CHtmlEditCtrl` オブジェクトを構築します。

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a>作成

ActiveX コントロールを作成し、オブジェクトに`CHtmlEditCtrl`アタッチします。 WebBrowser ActiveX コントロールは、既定のドキュメントに自動的に移動し、この関数によって編集モードに設定されます。

```
virtual BOOL Create(
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    int nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*名前をクリックします。*<br/>
このパラメーターは使用されません。

*Dwstyle*<br/>
このパラメーターは使用されません。

*Rect*<br/>
コントロールのサイズと位置を指定します。

*pParentWnd*<br/>
コントロールの親ウィンドウを指定します。 NULL にすることはできません。

*nID*<br/>
コントロールの ID を指定します。

*pContext*<br/>
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a>ドキュメントを編集します。

現在含まれている WebBrowser コントロールに読み込まれているドキュメントの[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))インターフェイスを取得します。

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>パラメーター

*ppDocument*<br/>
ドキュメント インターフェイス。

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a>ドキュメントを取得します。

含まれている WebBrowser コントロールに読み込む既定のドキュメントの URL を取得します。

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)
