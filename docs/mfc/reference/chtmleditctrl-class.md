---
description: '詳細情報: CHtmlEditCtrl クラス'
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
ms.openlocfilehash: d395f0f9f3e8b5ae10ad0ce35b2b1e410633e8d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183998"
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
|[CHtmlEditCtrl::CHtmlEditCtrl](#chtmleditctrl)|`CHtmlEditCtrl` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHtmlEditCtrl:: Create](#create)|WebBrowser ActiveX コントロールを作成し、オブジェクトにアタッチし `CHtmlEditCtrl` ます。 この関数は、WebBrowser ActiveX コントロールを自動的に編集モードにします。|
|[CHtmlEditCtrl::GetDHtmlDocument](#getdhtmldocument)|含まれている WebBrowser コントロールに現在読み込まれているドキュメントの [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) インターフェイスを取得します。|
|[CHtmlEditCtrl:: GetStartDocument](#getstartdocument)|含まれている WebBrowser コントロールに読み込む既定のドキュメントの URL を取得します。|

## <a name="remarks"></a>解説

ホストされた WebBrowser コントロールは、作成後に自動的に編集モードになります。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CHtmlEditCtrl`

## <a name="requirements"></a>要件

**ヘッダー:** afxhtml.h

## <a name="chtmleditctrlchtmleditctrl"></a><a name="chtmleditctrl"></a> CHtmlEditCtrl::CHtmlEditCtrl

`CHtmlEditCtrl` オブジェクトを構築します。

```
CHtmlEditCtrl();
```

## <a name="chtmleditctrlcreate"></a><a name="create"></a> CHtmlEditCtrl:: Create

WebBrowser ActiveX コントロールを作成し、オブジェクトにアタッチし `CHtmlEditCtrl` ます。 WebBrowser ActiveX コントロールは自動的に既定のドキュメントに移動し、この関数によって編集モードになります。

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

*lpszWindowName*<br/>
このパラメーターは使用されません。

*dwStyle*<br/>
このパラメーターは使用されません。

*rect*<br/>
コントロールのサイズと位置を指定します。

*pParentWnd*<br/>
コントロールの親ウィンドウを指定します。 NULL にすることはできません。

*nID*<br/>
コントロールの ID を指定します。

*pContext*<br/>
このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="chtmleditctrlgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditCtrl::GetDHtmlDocument

含まれている WebBrowser コントロールに現在読み込まれているドキュメントの [IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\)) インターフェイスを取得します。

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>パラメーター

*ppDocument*<br/>
ドキュメントインターフェイス。

## <a name="chtmleditctrlgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditCtrl:: GetStartDocument

含まれている WebBrowser コントロールに読み込む既定のドキュメントの URL を取得します。

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)
