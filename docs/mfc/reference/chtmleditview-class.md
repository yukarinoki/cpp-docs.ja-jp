---
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
ms.openlocfilehash: 20d4586c1ae45e5f3f56c0adbb1ecb1757084fd7
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752324"
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
|[ビュー::CHtml編集ビュー](#chtmleditview)|`CHtmlEditView` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ビュー::作成](#create)|新しいウィンドウ オブジェクトを作成します。|
|[ドキュメントを表示します。](#getdhtmldocument)|現在の`IHTMLDocument2`ドキュメントのインターフェイスを返します。|
|[ビュー::取得ドキュメント](#getstartdocument)|このビューの既定のドキュメントの名前を取得します。|

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CView](../../mfc/reference/cview-class.md)

[CScrollView](../../mfc/reference/cscrollview-class.md)

[CFormView](../../mfc/reference/cformview-class.md)

[CHtmlEditCtrlBase](../../mfc/reference/chtmleditctrlbase-class.md)

[ビュー](../../mfc/reference/chtmlview-class.md)

`CHtmlEditView`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxhtml.h

## <a name="chtmleditviewchtmleditview"></a><a name="chtmleditview"></a>ビュー::CHtml編集ビュー

`CHtmlEditView` オブジェクトを構築します。

```
CHtmlEditView();
```

## <a name="chtmleditviewcreate"></a><a name="create"></a>ビュー::作成

新しいウィンドウ オブジェクトを作成します。

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

*クラス名*<br/>
Windows クラスの名前を示す null で終わる文字列を指します。 クラス名は[、AfxRegisterWndClass](application-information-and-management.md#afxregisterwndclass)グローバル関数または Windows 関数に登録`RegisterClass`された任意の名前にすることができます。 NULL の場合、定義済みの既定[の CFrameWnd](../../mfc/reference/cframewnd-class.md)属性が使用されます。

*名前をクリックします。*<br/>
ウィンドウ名を表す null で終わる文字列を指します。

*Dwstyle*<br/>
ウィンドウ スタイルの属性を指定します。 既定では、WS_VISIBLEとWS_CHILD Windows スタイルが設定されます。

*Rect*<br/>
ウィンドウのサイズと位置を指定する[RECT](/windows/win32/api/windef/ns-windef-rect)構造体への参照。 *rectDefault*値を使用すると、ウィンドウは新しいウィンドウのサイズと位置を指定できます。

*pParentWnd*<br/>
コントロールの親ウィンドウへのポインター。

*nID*<br/>
ビューの ID 番号。 既定では、AFX_IDW_PANE_FIRSTに設定します。

*pContext*<br/>
へのポインターを[CCreate コンテキスト](../../mfc/reference/ccreatecontext-structure.md)にします。 既定では NULL です。

### <a name="remarks"></a>解説

このメソッドは、含まれている WebBrowser の`Navigate`メソッドを呼び出して既定のドキュメントを読み込みます[(CHtmlEditView::GetStartDocument](#getstartdocument)を参照)。

## <a name="chtmleditviewgetdhtmldocument"></a><a name="getdhtmldocument"></a>ドキュメントを表示します。

現在の`IHTMLDocument2`ドキュメントのインターフェイスを返します。

```
BOOL GetDHtmlDocument(IHTMLDocument2** ppDocument) const;
```

### <a name="parameters"></a>パラメーター

*ppDocument*<br/>
[インターフェイス。](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/aa752574\(v=vs.85\))

## <a name="chtmleditviewgetstartdocument"></a><a name="getstartdocument"></a>ビュー::取得ドキュメント

このビューの既定のドキュメントの名前を取得します。

```
virtual LPCTSTR GetStartDocument();
```

## <a name="see-also"></a>関連項目

[HTML 編集のサンプル](../../overview/visual-cpp-samples.md)<br/>
[階層グラフ](../../mfc/hierarchy-chart.md)
