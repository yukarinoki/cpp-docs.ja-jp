---
description: '詳細情報: CHtmlEditView クラス'
title: CHtmlEditView クラス
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditView
- AFXHTML/CHtmlEditView
- AFXHTML/CHtmlEditView::CHtmlEditView
- AFXHTML/CHtmlEditView::Create
- AFXHTML/CHtmlEditView::GetDHtmlDocument
- AFXHTML/CHtmlEditView::GetStartDocument
helpviewer_keywords:
- CHtmlEditView [MFC], CHtmlEditView
- CHtmlEditView [MFC], Create
- CHtmlEditView [MFC], GetDHtmlDocument
- CHtmlEditView [MFC], GetStartDocument
ms.assetid: 166c8ba8-3fb5-4dd7-a9ea-5bca662d00f6
ms.openlocfilehash: 9ab998ca16a26fd4ef7a23e4dc58c6542ec330b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261321"
---
# <a name="chtmleditview-class"></a>CHtmlEditView クラス

MFC のドキュメント/ビュー アーキテクチャのコンテキストで WebBrowser 編集プラットフォームの機能を提供します。

## <a name="syntax"></a>構文

```
class CHtmlEditView : public CHtmlView, public CHtmlEditCtrlBase<CHtmlEditView>
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CHtmlEditView:: CHtmlEditView](#chtmleditview)|`CHtmlEditView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CHtmlEditView:: Create](#create)|新しいウィンドウオブジェクトを作成します。|
|[CHtmlEditView:: GetDHtmlDocument](#getdhtmldocument)|現在の `IHTMLDocument2` ドキュメントのインターフェイスを返します。|
|[CHtmlEditView:: GetStartDocument](#getstartdocument)|このビューの既定のドキュメントの名前を取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[CHtmlView](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>要件

**ヘッダー:** afxhtml.h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a> CHtmlEditView:: CHtmlEditView

`CHtmlEditView` オブジェクトを構築します。

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a> CHtmlEditView:: Create

新しいウィンドウオブジェクトを作成します。

```
virtual BOOL Create(
    LPCTSTR lpszClassName,
    LPCTSTR lpszWindowName,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID,
    CCreateContext* pContext = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszClassName*<br/>
Windows クラスに名前を指定する null で終わる文字列を指します。 クラス名には、 [AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass) グローバル関数または Windows 関数に登録されている任意の名前を指定でき `RegisterClass` ます。 NULL の場合は、定義済みの既定の [CFrameWnd](../../mfc/reference/cframewnd-class.md) 属性が使用されます。

*lpszWindowName*<br/>
ウィンドウ名を表す null で終わる文字列を指します。

*dwStyle*<br/>
ウィンドウスタイル属性を指定します。 既定では、WS_VISIBLE と WS_CHILD の Windows スタイルが設定されています。

*rect*<br/>
ウィンドウのサイズと位置を指定する [RECT](/windows/win32/api/windef/ns-windef-rect) 構造体への参照。 *RectDefault* 値を使用すると、ウィンドウで新しいウィンドウのサイズと位置を指定できます。

*pParentWnd*<br/>
コントロールの親ウィンドウへのポインター。

*nID*<br/>
ビューの ID 番号。 既定では、を AFX_IDW_PANE_FIRST に設定します。

*pContext*<br/>
[CCreateContext](../../mfc/reference/ccreatecontext-structure.md)へのポインター。 既定では NULL です。

### <a name="remarks"></a>解説

また、このメソッドは、含まれている WebBrowser のメソッドを呼び出して、 `Navigate` 既定のドキュメントを読み込みます (「 [CHtmlEditView:: GetStartDocument](#getstartdocument)」を参照してください)。

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a> CHtmlEditView:: GetDHtmlDocument

現在の `IHTMLDocument2` ドキュメントのインターフェイスを返します。

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>パラメーター

*ppDocument*<br/>
[IHTMLDocument2](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))インターフェイス。

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a> CHtmlEditView:: GetStartDocument

このビューの既定のドキュメントの名前を取得します。

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>関連項目

[HTMLEdit サンプル](../../overview/visual-cpp-samples.md)<br/>
[階層図](../../mfc/hierarchy-chart.md)
