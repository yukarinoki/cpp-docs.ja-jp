---
title: CMFCRibbonStatusBar クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
ms.openlocfilehash: f76c2014cd3f6ed6e479fb66436224e675c69569
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368818"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar クラス

この`CMFCRibbonStatusBar`クラスは、リボン要素を表示できるステータス バー コントロールを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ステータスバー::ダイナミックエレメントの追加](#adddynamicelement)|リボン ステータス バーに動的要素を追加します。|
|[ステータスバー::要素の追加](#addelement)|リボン ステータス バーに新しいリボン要素を追加します。|
|[状態バー::拡張要素の追加](#addextendedelement)|リボン ステータス バーの拡張領域にリボン要素を追加します。|
|[ステータスバー::セパレータの追加](#addseparator)|リボンステータス バーに区切り記号を追加します。|
|[ステータスバー::作成](#create)|リボン ステータス バーを作成します。|
|[ステータスバー::作成します。](#createex)|拡張スタイルを持つリボン ステータス バーを作成します。|
|[ステータスバーを検索します。](#findbyid)||
|[ステータスバー::要素を検索します。](#findelement)|指定したコマンド ID を持つ要素へのポインターを返します。|
|[ステータスバーを取得します。](#getcount)|リボン ステータス バーのメイン領域にある要素の数を返します。|
|[ステータスバー::取得要素](#getelement)|指定したインデックス位置にある要素へのポインターを返します。|
|[ステータスバー::取得します。](#getexcount)|リボン ステータス バーの拡張領域にある要素の数を返します。|
|[ステータスバー::要素](#getexelement)|リボン ステータス バーの拡張領域内の指定されたインデックスにある要素へのポインターを返します。|
|[状態バー::拡張エリア](#getextendedarea)||
|[ステータスバーを取得します。](#getspace)||
|[ステータスバー::Isボトムフレーム](#isbottomframe)||
|[ステータス バー::拡張要素](#isextendedelement)||
|[ステータス バー::情報モード](#isinformationmode)|リボン ステータス バーの情報モードを有効にするかどうかを指定します。|
|[ステータスバー::再計算レイアウト](#recalclayout)|[(CMFCリボンバーをオーバーライドします::再計算レイアウト](../../mfc/reference/cmfcribbonbar-class.md#recalclayout).)|
|[ステータスバー::すべて削除](#removeall)|リボン ステータス バーからすべての要素を削除します。|
|[ステータスバー::要素の削除](#removeelement)|リボン ステータス バーから、指定したコマンド ID を持つ要素を削除します。|
|[ステータスバー::セット情報](#setinformation)|リボン ステータス バーの情報モードを有効または無効にします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[ステータスバー::オンドロー情報](#ondrawinformation)|情報モードが有効な場合に、リボン ステータス バーに表示される情報文字列を表示します。|

## <a name="remarks"></a>解説

リボン ステータス バーの組み込みコンテキスト メニューを使用して、リボン ステータス バーのリボン要素の表示を変更できます。 要素を動的に追加または削除できます。

リボン ステータス バーには、メイン領域と拡張領域の 2 つの領域があります。 拡張領域は、リボン ステータス バーの右側に表示され、メイン領域とは異なる色で表示されます。

通常、ステータス バーのメイン領域にはステータス通知が表示され、拡張領域にはビュー コントロールが表示されます。 ユーザーがリボン ステータス バーのサイズを変更しても、拡張領域は可能な限り長く表示されます。

## <a name="example"></a>例

`CMFCRibbonStatusBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、リボン ステータス バーに新しいリボン要素を追加し、リボン ステータス バーの拡張領域にリボン要素を追加し、区分線を追加し、リボン ステータス バーの通常モードを有効にする方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxribbon ステータスバー.h

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a>ステータスバー::ダイナミックエレメントの追加

リボン ステータス バーに動的要素を追加します。

```
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
[in]動的要素へのポインター。

### <a name="remarks"></a>解説

通常の要素とは異なり、動的要素はカスタマイズ可能ではなく、ステータス バーのカスタマイズ メニューには表示されません。

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a>ステータスバー::要素の追加

リボン ステータス バーに新しいリボン要素を追加します。

```
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
[in]追加された要素へのポインター。

*ラベル*<br/>
[in]要素のテキスト ラベル。

*ビズブル*<br/>
[in]表示可能な要素を追加する場合は TRUE、非表示として要素を追加する場合は FALSE。

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a>状態バー::拡張要素の追加

リボン ステータス バーの拡張領域にリボン要素を追加します。

```
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
[in]追加された要素へのポインター。

*ラベル*<br/>
[in]要素のテキスト ラベル。

*ビズブル*<br/>
[in]表示可能な要素を追加する場合は TRUE、非表示として要素を追加する場合は FALSE。

### <a name="remarks"></a>解説

拡張領域は、ステータス バー コントロールの右側にあります。

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a>ステータスバー::セパレータの追加

リボンステータス バーに区切り記号を追加します。

```
void AddSeparator();
```

### <a name="remarks"></a>解説

フレームワークは、メソッド[CMFCRibbon ステータスバー::AddElement](#addelement)の後に区切り記号を追加します。 最後の要素を挿入します。

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a>ステータスバー::作成

リボン ステータス バーを作成します。

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
[in]親ウィンドウへのポインター。

*Dwstyle*<br/>
[in]コントロール スタイルの論理 OR の組み合わせ。

*nID*<br/>
[in]ステータス バーのコントロール ID。

### <a name="return-value"></a>戻り値

ステータス バーが正常に作成された場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a>ステータスバー::作成します。

拡張スタイルを持つリボン ステータス バーを作成します。

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle=0,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
親ウィンドウへのポインター。

*スタイル*<br/>
ステータス バー オブジェクトを作成するための追加のスタイルの論理 OR の組み合わせ。

*Dwstyle*<br/>
ステータス バーのコントロール スタイル。

*nID*<br/>
ステータス バーのコントロール ID。

### <a name="return-value"></a>戻り値

ステータス バーが正常に作成された場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a>ステータスバーを検索します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>パラメーター

[in]*UICmdID*<br/>
[in]*ブール*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a>ステータスバー::要素を検索します。

指定したコマンド ID を持つ要素へのポインターを返します。

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]要素の ID。

### <a name="return-value"></a>戻り値

指定したコマンド ID を持つ要素へのポインター。 そのような要素がない場合は NULL。

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a>ステータスバーを取得します。

リボン ステータス バーのメイン領域にある要素の数を返します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

リボン ステータス バーのメイン領域にある要素の数。

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a>ステータスバー::取得要素

指定したインデックス位置にある要素へのポインターを返します。

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]ステータス バー コントロールのメイン領域にある要素の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

指定したインデックス位置にある要素へのポインター。 インデックスが負の場合、またはステータス バーの要素数を超える場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a>ステータスバー::取得します。

リボン ステータス バーの拡張領域にある要素の数を返します。

```
int GetExCount() const;
```

### <a name="return-value"></a>戻り値

リボン ステータス バーの拡張領域にある要素の数。

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a>ステータスバー::要素

リボン ステータス バーの拡張領域内の指定されたインデックスにある要素へのポインターを返します。 拡張領域は、ステータス バー コントロールの右側にあります。

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
[in]ステータス バー コントロールの拡張領域にある要素の 0 から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

リボン ステータス バーの拡張領域内の指定されたインデックスにある要素へのポインター。 *nIndex*が負の値であるか、リボン ステータス バーの拡張領域内の要素数を超える場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a>状態バー::拡張エリア

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

[in]*レクト*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a>ステータスバーを取得します。

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
int GetSpace() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a>ステータスバー::Isボトムフレーム

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a>ステータス バー::拡張要素

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>パラメーター

[in]*要素*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a>ステータス バー::情報モード

リボン ステータス バーの情報モードを有効にするかどうかを指定します。

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>戻り値

ステータス バーが情報モードで動作する場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

情報モードでは、ステータス バーはすべての通常のペインを非表示にし、メッセージ文字列を表示します。

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a>ステータスバー::オンドロー情報

情報モードが有効な場合にリボン ステータス バーに表示される文字列を表示します。

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*の情報*<br/>
[in]情報文字列。

*レクト情報*<br/>
[in]外接する四角形。

### <a name="remarks"></a>解説

ステータス バーの情報文字列の外観をカスタマイズする場合は、派生クラスでこのメソッドをオーバーライドします。 ステータス バーを情報モードにするには[、CMFCRibbonStatusBar::SetInformation](#setinformation)メソッドを使用します。 このモードでは、ステータス バーはすべてのペインを非表示にし *、strInfo*で指定された情報文字列を表示します。

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a>ステータスバー::再計算レイアウト

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a>ステータスバー::すべて削除

リボン ステータス バーからすべての要素を削除します。

```
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a>ステータスバー::要素の削除

リボン ステータス バーから、指定したコマンド ID を持つ要素を削除します。

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>パラメーター

*Uiid*<br/>
[in]ステータス バーから削除する要素の ID。

### <a name="return-value"></a>戻り値

指定された*uiID*を持つ要素が削除された場合は TRUE。 それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a>ステータスバー::セット情報

リボン ステータス バーの情報モードを有効または無効にします。

```
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>パラメーター

*情報を提供します。*<br/>
[in]情報文字列。

### <a name="remarks"></a>解説

このメソッドは、ステータス バーを情報モードにする場合に使用します。 このモードでは、ステータス バーはすべてのペインを非表示にし、 *lpszInfo*で指定された情報文字列を表示します。

lpszInfo が NULL の場合、ステータス バーは通常モードに戻ります。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[クラス](../../mfc/reference/cmfcribbonbar-class.md)
