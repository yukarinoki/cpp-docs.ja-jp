---
description: '詳細情報: CMFCRibbonStatusBar クラス'
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
ms.openlocfilehash: 01436d535b410fd4a6c70f52760908e3547b7af8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265000"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar クラス

クラスは、 `CMFCRibbonStatusBar` リボン要素を表示できるステータスバーコントロールを実装します。

## <a name="syntax"></a>構文

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonStatusBar:: AddDynamicElement](#adddynamicelement)|リボンステータスバーに動的要素を追加します。|
|[CMFCRibbonStatusBar::AddElement](#addelement)|リボンのステータスバーに新しいリボン要素を追加します。|
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|リボンのステータスバーの拡張領域にリボン要素を追加します。|
|[CMFCRibbonStatusBar:: AddSeparator](#addseparator)|リボンステータスバーに区切り記号を追加します。|
|[CMFCRibbonStatusBar:: Create](#create)|リボンのステータスバーを作成します。|
|[CMFCRibbonStatusBar:: CreateEx](#createex)|拡張スタイルを使用して、リボンのステータスバーを作成します。|
|[CMFCRibbonStatusBar::FindByID](#findbyid)||
|[CMFCRibbonStatusBar::FindElement](#findelement)|指定されたコマンド ID を持つ要素へのポインターを返します。|
|[CMFCRibbonStatusBar:: GetCount](#getcount)|リボンステータスバーのメイン領域に配置されている要素の数を返します。|
|[CMFCRibbonStatusBar:: GetElement](#getelement)|指定したインデックス位置にある要素へのポインターを返します。|
|[CMFCRibbonStatusBar:: GetExCount](#getexcount)|リボンステータスバーの拡張領域に配置されている要素の数を返します。|
|[CMFCRibbonStatusBar:: GetExElement](#getexelement)|リボン ステータス バーの拡張領域内の指定されたインデックスにある要素へのポインターを返します。|
|[CMFCRibbonStatusBar:: GetExtendedArea](#getextendedarea)||
|[CMFCRibbonStatusBar:: GetSpace](#getspace)||
|[CMFCRibbonStatusBar:: Is下端フレーム](#isbottomframe)||
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||
|[CMFCRibbonStatusBar:: IsInformationMode](#isinformationmode)|情報モードをリボンのステータスバーで有効にするかどうかを指定します。|
|[CMFCRibbonStatusBar:: RecalcLayout](#recalclayout)|( [CMFCRibbonBar:: RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout)をオーバーライドします。)|
|[CMFCRibbonStatusBar:: RemoveAll](#removeall)|リボンステータスバーからすべての要素を削除します。|
|[CMFCRibbonStatusBar:: RemoveElement](#removeelement)|リボンステータスバーから、指定したコマンド ID を持つ要素を削除します。|
|[CMFCRibbonStatusBar:: SetInformation](#setinformation)|リボンステータスバーの情報モードを有効または無効にします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|情報モードが有効になっている場合に、リボンステータスバーに表示される情報文字列を表示します。|

## <a name="remarks"></a>解説

リボンステータスバーのリボン要素の表示を変更するには、リボンのステータスバーの組み込みコンテキストメニューを使用します。 要素を動的に追加または削除できます。

リボンステータスバーには、メイン領域と拡張領域という2つの領域があります。 拡張領域は、リボンのステータスバーの右側に表示され、メイン領域とは異なる色で表示されます。

通常、ステータスバーのメイン領域には状態通知が表示され、拡張領域にはビューコントロールが表示されます。 拡張領域は、ユーザーがリボンのステータスバーのサイズを変更したときに、可能な限り長く表示されたままになります。

## <a name="example"></a>例

`CMFCRibbonStatusBar` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、リボンのステータスバーに新しいリボン要素を追加し、リボンのステータスバーの拡張領域にリボン要素を追加し、区切り記号を追加して、リボンステータスバーの通常モードを有効にする方法を示します。

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

## <a name="requirements"></a>要件

**ヘッダー:** afxribbonstatusbar

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a> CMFCRibbonStatusBar:: AddDynamicElement

リボンステータスバーに動的要素を追加します。

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>パラメーター

*pElement*<br/>
から動的要素へのポインター。

### <a name="remarks"></a>解説

通常の要素とは異なり、動的な要素はカスタマイズできません。また、ステータスバーの [カスタマイズ] メニューには表示されません。

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a> CMFCRibbonStatusBar::AddElement

リボンのステータスバーに新しいリボン要素を追加します。

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>パラメーター

*pElement*<br/>
から追加された要素へのポインター。

*lpszLabel*<br/>
から要素のテキストラベル。

*bIsVisible*<br/>
から要素を visible として追加する場合は TRUE、要素を非表示として追加する場合は FALSE。

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a> CMFCRibbonStatusBar::AddExtendedElement

リボンのステータスバーの拡張領域にリボン要素を追加します。

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>パラメーター

*pElement*<br/>
から追加された要素へのポインター。

*lpszLabel*<br/>
から要素のテキストラベル。

*bIsVisible*<br/>
から要素を visible として追加する場合は TRUE、要素を非表示として追加する場合は FALSE。

### <a name="remarks"></a>解説

拡張領域は、ステータス バー コントロールの右側にあります。

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a> CMFCRibbonStatusBar:: AddSeparator

リボンステータスバーに区切り記号を追加します。

```cpp
void AddSeparator();
```

### <a name="remarks"></a>解説

フレームワークは、メソッド [CMFCRibbonStatusBar:: AddElement](#addelement)の後に区切り記号を追加します。 最後の要素を挿入します。

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a> CMFCRibbonStatusBar:: Create

リボンのステータスバーを作成します。

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>パラメーター

*pParentWnd*<br/>
から親ウィンドウへのポインター。

*dwStyle*<br/>
からコントロールスタイルの論理的または組み合わせ。

*nID*<br/>
からステータスバーのコントロール ID。

### <a name="return-value"></a>戻り値

ステータスバーが正常に作成された場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a> CMFCRibbonStatusBar:: CreateEx

拡張スタイルを持つリボンステータスバーを作成します。

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

*dwCtrlStyle*<br/>
ステータスバーオブジェクトを作成するための追加スタイルの論理的または組み合わせ。

*dwStyle*<br/>
ステータスバーのコントロールスタイル。

*nID*<br/>
ステータスバーのコントロール ID。

### <a name="return-value"></a>戻り値

ステータスバーが正常に作成された場合は TRUE、それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a> CMFCRibbonStatusBar::FindByID

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>パラメーター

から *uiCmdID*<br/>
から *BOOL*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a> CMFCRibbonStatusBar::FindElement

指定されたコマンド ID を持つ要素へのポインターを返します。

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>パラメーター

*uiID*<br/>
から要素の ID。

### <a name="return-value"></a>戻り値

指定されたコマンド ID を持つ要素へのポインター。 そのような要素が存在しない場合は NULL です。

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a> CMFCRibbonStatusBar:: GetCount

リボンステータスバーのメイン領域に配置されている要素の数を返します。

```
int GetCount() const;
```

### <a name="return-value"></a>戻り値

リボンステータスバーのメイン領域に配置されている要素の数。

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a> CMFCRibbonStatusBar:: GetElement

指定したインデックス位置にある要素へのポインターを返します。

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からステータスバーコントロールのメイン領域にある要素の0から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

指定したインデックス位置にある要素へのポインター。 インデックスが負の値であるか、ステータスバーの要素の数を超えている場合は NULL です。

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a> CMFCRibbonStatusBar:: GetExCount

リボンステータスバーの拡張領域に配置されている要素の数を返します。

```
int GetExCount() const;
```

### <a name="return-value"></a>戻り値

リボンステータスバーの拡張領域に配置されている要素の数。

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a> CMFCRibbonStatusBar:: GetExElement

リボン ステータス バーの拡張領域内の指定されたインデックスにある要素へのポインターを返します。 拡張領域は、ステータス バー コントロールの右側にあります。

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>パラメーター

*nIndex*<br/>
からステータスバーコントロールの拡張領域内にある要素の0から始まるインデックスを指定します。

### <a name="return-value"></a>戻り値

リボン ステータス バーの拡張領域内の指定されたインデックスにある要素へのポインター。 *NIndex* が負の場合、またはリボンステータスバーの拡張領域内の要素数を超える場合は NULL。

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCRibbonStatusBar:: GetExtendedArea

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>パラメーター

から *rect*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a> CMFCRibbonStatusBar:: GetSpace

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
int GetSpace() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a> CMFCRibbonStatusBar:: Is下端フレーム

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a> CMFCRibbonStatusBar::IsExtendedElement

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>パラメーター

から *Pelement*<br/>

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a> CMFCRibbonStatusBar:: IsInformationMode

情報モードをリボンのステータスバーで有効にするかどうかを指定します。

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>戻り値

ステータスバーを情報モードで使用できる場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

情報モードでは、ステータスバーはすべての標準ペインを非表示にして、メッセージ文字列を表示します。

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a> CMFCRibbonStatusBar::OnDrawInformation

情報モードが有効になっている場合に、リボンステータスバーに表示される文字列を表示します。

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*strInfo*<br/>
から情報文字列。

*rectInfo*<br/>
から外接する四角形。

### <a name="remarks"></a>解説

ステータスバーの情報文字列の外観をカスタマイズする場合は、派生クラスでこのメソッドをオーバーライドします。 [CMFCRibbonStatusBar:: SetInformation](#setinformation)メソッドを使用して、ステータスバーを情報モードにします。 このモードでは、ステータスバーはすべてのウィンドウを非表示にし、 *Strinfo* によって指定された情報文字列を表示します。

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a> CMFCRibbonStatusBar:: RecalcLayout

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>解説

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a> CMFCRibbonStatusBar:: RemoveAll

リボンステータスバーからすべての要素を削除します。

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a> CMFCRibbonStatusBar:: RemoveElement

リボンステータスバーから、指定したコマンド ID を持つ要素を削除します。

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>パラメーター

*uiID*<br/>
からステータスバーから削除する要素の ID。

### <a name="return-value"></a>戻り値

指定された *uiID* を持つ要素が削除された場合は TRUE。 それ以外の場合は FALSE。

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a> CMFCRibbonStatusBar:: SetInformation

リボンステータスバーの情報モードを有効または無効にします。

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>パラメーター

*lpszInfo*<br/>
から情報文字列。

### <a name="remarks"></a>解説

情報モードにステータスバーを配置するには、このメソッドを使用します。 このモードでは、ステータスバーはすべてのウィンドウを非表示にし、 *Lpszinfo* によって指定された情報文字列を表示します。

LpszInfo が NULL の場合、ステータスバーは通常モードに戻ります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[CMFCRibbonBaseElement クラス](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)
