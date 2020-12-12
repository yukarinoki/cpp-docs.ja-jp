---
description: '詳細情報: CMFCHeaderCtrl クラス'
title: CMFCHeaderCtrl Class
ms.date: 11/04/2016
f1_keywords:
- CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::CMFCHeaderCtrl
- AFXHEADERCTRL/CMFCHeaderCtrl::EnableMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::GetColumnState
- AFXHEADERCTRL/CMFCHeaderCtrl::GetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::IsAscending
- AFXHEADERCTRL/CMFCHeaderCtrl::IsDialogControl
- AFXHEADERCTRL/CMFCHeaderCtrl::IsMultipleSort
- AFXHEADERCTRL/CMFCHeaderCtrl::RemoveSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::SetSortColumn
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawItem
- AFXHEADERCTRL/CMFCHeaderCtrl::OnDrawSortArrow
- AFXHEADERCTRL/CMFCHeaderCtrl::OnFillBackground
helpviewer_keywords:
- CMFCHeaderCtrl [MFC], CMFCHeaderCtrl
- CMFCHeaderCtrl [MFC], EnableMultipleSort
- CMFCHeaderCtrl [MFC], GetColumnState
- CMFCHeaderCtrl [MFC], GetSortColumn
- CMFCHeaderCtrl [MFC], IsAscending
- CMFCHeaderCtrl [MFC], IsDialogControl
- CMFCHeaderCtrl [MFC], IsMultipleSort
- CMFCHeaderCtrl [MFC], RemoveSortColumn
- CMFCHeaderCtrl [MFC], SetSortColumn
- CMFCHeaderCtrl [MFC], OnDrawItem
- CMFCHeaderCtrl [MFC], OnDrawSortArrow
- CMFCHeaderCtrl [MFC], OnFillBackground
ms.assetid: 2f5fbf7b-5c75-42db-9216-640b1628f777
ms.openlocfilehash: a6be476e095dc4a013705657e259a90d7cafe0d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265377"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class

クラスは、 `CMFCHeaderCtrl` ヘッダーコントロール内の複数の列の並べ替えをサポートしています。

## <a name="syntax"></a>構文

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCHeaderCtrl:: CMFCHeaderCtrl](#cmfcheaderctrl)|`CMFCHeaderCtrl` オブジェクトを構築します。|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort)|現在のヘッダーコントロールに対して *複数の列の並べ替え* モードを有効または無効にします。|
|[CMFCHeaderCtrl:: GetColumnState](#getcolumnstate)|列が並べ替えられていないか、昇順または降順で並べ替えられているかを示します。|
|[CMFCHeaderCtrl:: GetSortColumn](#getsortcolumn)|ヘッダーコントロール内の最初に並べ替えられた列の0から始まるインデックスを取得します。|
|`CMFCHeaderCtrl::GetThisClass`|このクラス型に関連付けられている [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[CMFCHeaderCtrl:: IsAscending](#isascending)|ヘッダーコントロールの任意の列を昇順に並べ替えるかどうかを示します。|
|[CMFCHeaderCtrl:: IsDialogControl](#isdialogcontrol)|現在のヘッダーコントロールの親ウィンドウがダイアログボックスかどうかを示します。|
|[CMFCHeaderCtrl:: Is乗数 Esort](#ismultiplesort)|現在のヘッダーコントロールが *複数の列の並べ替え* モードであるかどうかを示します。|
|[CMFCHeaderCtrl:: RemoveSortColumn](#removesortcolumn)|並べ替え列の一覧から指定された列を削除します。|
|[CMFCHeaderCtrl:: SetSortColumn](#setsortcolumn)|ヘッダーコントロール内の指定した列の並べ替え順序を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CMFCHeaderCtrl:: OnDrawItem](#ondrawitem)|ヘッダーコントロール列を描画するためにフレームワークによって呼び出されます。|
|[CMFCHeaderCtrl:: OnDrawSortArrow](#ondrawsortarrow)|並べ替え矢印を描画するためにフレームワークによって呼び出されます。|
|[CMFCHeaderCtrl:: OnFillBackground](#onfillbackground)|ヘッダーコントロール列の背景を埋めるためにフレームワークによって呼び出されます。|

## <a name="example"></a>例

次の例では、クラスのオブジェクトを構築する方法 `CMFCHeaderCtrl` と、現在のヘッダーコントロールに対して *複数の列の並べ替え* モードを有効にする方法を示します。

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>解説

クラスは、 `CMFCHeaderCtrl` 列が並べ替えられていることを示すために、ヘッダーコントロール列に並べ替え矢印を描画します。 親リストコントロール ( [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)) の列のセットを同時に並べ替えることができる場合は、*複数の列の並べ替え* モードを使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxheaderctrl

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a> CMFCHeaderCtrl:: CMFCHeaderCtrl

`CMFCHeaderCtrl` オブジェクトを構築します。

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>解説

このコンストラクターは、指定された値に次のメンバー変数を初期化します。

|メンバー変数|値|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a> CMFCHeaderCtrl:: EnableMultipleSort

現在のヘッダーコントロールに対して *複数の列の並べ替え* モードを有効または無効にします。

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
から複数の列の並べ替えモードを有効にする場合は TRUE。複数の列の並べ替えモードを無効にして、並べ替えられた列の一覧から列を削除する場合は FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

複数の列の並べ替えモードを有効または無効にするには、このメソッドを使用します。 ヘッダーコントロールが複数の列の並べ替えモードになっている場合は、2つ以上の列が並べ替えに参加することができます。

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a> CMFCHeaderCtrl:: GetColumnState

列が並べ替えられていないか、昇順または降順で並べ替えられているかを示します。

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>パラメーター

*iColumn*<br/>
から列の0から始まるインデックス。

### <a name="return-value"></a>戻り値

指定された列の並べ替えの状態を示す値です。 可能な値を次の表に示します。

|値|説明|
|-----------|-----------------|
|-1|降順で並べ替えられます。|
|0|並べ替えられません。|
|1|昇順で並べ替えられます。|

### <a name="remarks"></a>解説

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a> CMFCHeaderCtrl:: GetSortColumn

ヘッダーコントロール内の最初に並べ替えられた列の0から始まるインデックスを取得します。

```
int GetSortColumn() const;
```

### <a name="return-value"></a>戻り値

並べ替えられた列のインデックス。並べ替えられた列が見つからない場合は-1。

### <a name="remarks"></a>解説

ヘッダーコントロールが *複数の列の並べ替え* モードで、デバッグモードでアプリケーションをコンパイルした場合、このメソッドは、代わりに [CMFCHeaderCtrl:: getcolumnstate](#getcolumnstate) メソッドを使用することをアサートしてアドバイスします。 ヘッダーコントロールが複数の列の並べ替えモードで、アプリケーションをリテールモードでコンパイルした場合、このメソッドは-1 を返します。

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a> CMFCHeaderCtrl:: IsAscending

ヘッダーコントロールの任意の列を昇順に並べ替えるかどうかを示します。

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>戻り値

ヘッダーコントロールの任意の列を昇順に並べ替える場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドが返す値は、ヘッダーコントロール項目に適切な並べ替え矢印を表示するために使用されます。 [CMFCHeaderCtrl:: SetSortColumn](#setsortcolumn)メソッドを使用して、並べ替え順序を設定します。

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a> CMFCHeaderCtrl:: IsDialogControl

現在のヘッダーコントロールの親ウィンドウがダイアログボックスかどうかを示します。

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>戻り値

現在のヘッダーコントロールの親ウィンドウがダイアログボックスである場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a> CMFCHeaderCtrl:: Is乗数 Esort

現在のヘッダーコントロールが *複数の列の並べ替え* モードであるかどうかを示します。

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>戻り値

複数の列の並べ替えモードが有効な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

複数の列の並べ替えモードを有効または無効にするには、 [CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort) メソッドを使用します。 ヘッダーコントロールが複数の列の並べ替えモードになっている場合は、2つ以上の列が並べ替えに参加することができます。

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a> CMFCHeaderCtrl:: OnDrawItem

ヘッダーコントロール列を描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawItem(
    CDC* pDC,
    int iItem,
    CRect rect,
    BOOL bIsPressed,
    BOOL bIsHighlighted);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*iItem*<br/>
から描画する項目の0から始まるインデックス。

*rect*<br/>
から描画する項目の外接する四角形。

*bIsPressed*<br/>
から押された状態の項目を描画する場合は TRUE。それ以外の場合は FALSE。

*bIsHighlighted*<br/>
から強調表示された状態で項目を描画する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a> CMFCHeaderCtrl:: OnDrawSortArrow

並べ替え矢印を描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

*rectArrow*<br/>
から並べ替え矢印の外接する四角形。

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a> CMFCHeaderCtrl:: OnFillBackground

ヘッダーコントロール列の背景を埋めるためにフレームワークによって呼び出されます。

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
からデバイスコンテキストへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a> CMFCHeaderCtrl:: RemoveSortColumn

並べ替え列の一覧から指定された列を削除します。

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>パラメーター

*iColumn*<br/>
から削除する列の0から始まるインデックス。

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a> CMFCHeaderCtrl:: SetSortColumn

ヘッダーコントロール内の指定した列の並べ替え順序を設定します。

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>パラメーター

*iColumn*<br/>
からヘッダーコントロール列の0から始まるインデックス。 このパラメーターが0未満の場合、このメソッドは並べ替え列の一覧からすべての列を削除します。

*bAscending*<br/>
から *IColumn* パラメーターで指定する列の並べ替え順序を指定します。 昇順を設定する場合は TRUE。降順の順序を設定する場合は FALSE。 既定値は TRUE です。

*bAdd*<br/>
から *IColumn* パラメーターで指定する列の並べ替え順序を設定する場合は TRUE。

現在のヘッダーコントロールが複数の *列の並べ替え* モードである場合、このメソッドは、指定された列を並べ替え列のリストに追加します。 複数の列の並べ替えモードを設定するには、 [CMFCHeaderCtrl:: EnableMultipleSort](#enablemultiplesort) を使用します。

複数の列の並べ替えモードが設定されておらず、このメソッドがデバッグモードでコンパイルされている場合、このメソッドはアサートします。 複数の列の並べ替えモードが設定されておらず、このメソッドがリテールモードでコンパイルされている場合、このメソッドは最初に並べ替え列のリストからすべての列を削除してから、指定された列をリストに追加します。

FALSE の場合は、最初に並べ替え列の一覧からすべての列を削除してから、指定した列をリストに追加します。 既定値は FALSE です。

### <a name="remarks"></a>解説

列の並べ替え順序を設定するには、このメソッドを使用します。 必要に応じて、このメソッドは列を並べ替え列のリストに追加します。 ヘッダーコントロールは、並べ替え順序を使用して、上下を示す並べ替え矢印を描画します。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)
