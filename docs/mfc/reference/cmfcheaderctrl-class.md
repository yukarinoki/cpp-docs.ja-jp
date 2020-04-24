---
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
ms.openlocfilehash: 5140d02c5acbbc430c3b4d175da1933c79c702b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752349"
---
# <a name="cmfcheaderctrl-class"></a>CMFCHeaderCtrl Class

この`CMFCHeaderCtrl`クラスは、ヘッダー コントロール内の複数の列の並べ替えをサポートしています。

## <a name="syntax"></a>構文

```
class CMFCHeaderCtrl : public CHeaderCtrl
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[次の文字列を表示します。](#cmfcheaderctrl)|`CMFCHeaderCtrl` オブジェクトを構築します。|
|`CMFCHeaderCtrl::~CMFCHeaderCtrl`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[複数の並べ替えを有効にします。](#enablemultiplesort)|現在のヘッダー コントロールの*複数列の並べ替え*モードを有効または無効にします。|
|[状態を取得します。](#getcolumnstate)|列が並べ替えられていないか、昇順または降順で並べ替えられているかを示します。|
|[次の項目を並べ替えます。](#getsortcolumn)|ヘッダー コントロール内の最初の並べ替えられた列の 0 から始まるインデックスを取得します。|
|`CMFCHeaderCtrl::GetThisClass`|このクラス型に関連付けられている[CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md)オブジェクトへのポインターを取得するために、フレームワークによって使用されます。|
|[次の値を指定します。](#isascending)|ヘッダー コントロール内の列が昇順で並べ替えられているかどうかを示します。|
|[コントロール](#isdialogcontrol)|現在のヘッダー コントロールの親ウィンドウがダイアログ ボックスかどうかを示します。|
|[を並べ替える](#ismultiplesort)|現在のヘッダー コントロールが*複数列の並べ替え*モードかどうかを示します。|
|[列を並べ替える](#removesortcolumn)|並べ替え列の一覧から指定した列を削除します。|
|[次の項目を選択します。](#setsortcolumn)|ヘッダー コントロール内の指定した列の並べ替え順序を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[次の項目を表示します。](#ondrawitem)|ヘッダー コントロール列を描画するために、フレームワークによって呼び出されます。|
|[次の矢印をクリックします。](#ondrawsortarrow)|並べ替え矢印を描画するためにフレームワークによって呼び出されます。|
|[次の文字列を使用します。](#onfillbackground)|ヘッダー コントロール列の背景を埋めるために、フレームワークによって呼び出されます。|

## <a name="example"></a>例

`CMFCHeaderCtrl`クラスのオブジェクトを構築する方法と、現在のヘッダー コントロールに*対して複数列の並べ替え*モードを有効にする方法を次の例に示します。

[!code-cpp[NVC_MFC_RibbonApp#24](../../mfc/reference/codesnippet/cpp/cmfcheaderctrl-class_1.cpp)]

## <a name="remarks"></a>解説

この`CMFCHeaderCtrl`クラスは、ヘッダー コントロール列に並べ替え矢印を描画し、列が並べ替えられていることを示します。 親リスト コントロール ( [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)) 内の列のセットを同時に並べ替えることができる場合は、*複数列の並べ替*えモードを使用します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CHeaderCtrl](../../mfc/reference/cheaderctrl-class.md)

[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxheaderctrl.h

## <a name="cmfcheaderctrlcmfcheaderctrl"></a><a name="cmfcheaderctrl"></a>次の文字列を表示します。

`CMFCHeaderCtrl` オブジェクトを構築します。

```
CMFCHeaderCtrl::CMFCHeaderCtrl()
```

### <a name="remarks"></a>解説

このコンストラクターは、次のメンバー変数を指定した値に初期化します。

|メンバー変数|値|
|---------------------|-----------|
|`m_bIsMousePressed`|FALSE|
|`m_bMultipleSort`|FALSE|
|`m_bAscending`|TRUE|
|`m_nHighlightedItem`|-1|
|`m_bTracked`|FALSE|
|`m_bIsDlgControl`|FALSE|
|`m_hFont`|NULL|

## <a name="cmfcheaderctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>複数の並べ替えを有効にします。

現在のヘッダー コントロールの*複数列の並べ替え*モードを有効または無効にします。

```cpp
void EnableMultipleSort(BOOL bEnable=TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]複数列の並べ替えモードを有効にする場合は TRUE。複数列の並べ替えモードを無効にし、並べ替えられた列のリストから列を削除するには FALSE。 既定値は TRUE です。

### <a name="remarks"></a>解説

このメソッドは、複数列の並べ替えモードを有効または無効にするために使います。 ヘッダー コントロールが複数列の並べ替えモードの場合、2 つ以上の列が並べ替えに参加できます。

## <a name="cmfcheaderctrlgetcolumnstate"></a><a name="getcolumnstate"></a>状態を取得します。

列が並べ替えられていないか、昇順または降順で並べ替えられているかを示します。

```
int GetColumnState(int iColumn) const;
```

### <a name="parameters"></a>パラメーター

*i列*<br/>
[in]列の 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定した列の並べ替え状態を示す値。 可能な値を次の表に示します。

|値|説明|
|-----------|-----------------|
|-1|降順で並べ替え。|
|0|並べ替えられていません。|
|1|昇順で並べ替え。|

### <a name="remarks"></a>解説

## <a name="cmfcheaderctrlgetsortcolumn"></a><a name="getsortcolumn"></a>次の項目を並べ替えます。

ヘッダー コントロール内の最初の並べ替えられた列の 0 から始まるインデックスを取得します。

```
int GetSortColumn() const;
```

### <a name="return-value"></a>戻り値

並べ替えられた列のインデックス。

### <a name="remarks"></a>解説

ヘッダー コントロールが*複数列の並べ替え*モードで、アプリケーションをデバッグ モードでコンパイルした場合、このメソッドは、代わりに[CMFCHeaderCtrl::GetColumnState](#getcolumnstate)メソッドを使用することをアサートし、助言します。 ヘッダー コントロールが複数列の並べ替えモードで、アプリケーションをリテール モードでコンパイルした場合、このメソッドは -1 を返します。

## <a name="cmfcheaderctrlisascending"></a><a name="isascending"></a>次の値を指定します。

ヘッダー コントロール内の列が昇順で並べ替えられているかどうかを示します。

```
BOOL IsAscending() const;
```

### <a name="return-value"></a>戻り値

ヘッダー コントロール内の列が昇順で並べ替えられている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドが返す値は、ヘッダー コントロール項目に適切な並べ替え矢印を表示するために使用されます。 並べ替え順序を設定するには、メソッドを使用[します](#setsortcolumn)。

## <a name="cmfcheaderctrlisdialogcontrol"></a><a name="isdialogcontrol"></a>コントロール

現在のヘッダー コントロールの親ウィンドウがダイアログ ボックスかどうかを示します。

```
BOOL IsDialogControl() const;
```

### <a name="return-value"></a>戻り値

現在のヘッダー コントロールの親ウィンドウがダイアログ ボックスの場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcheaderctrlismultiplesort"></a><a name="ismultiplesort"></a>を並べ替える

現在のヘッダー コントロールが*複数列の並べ替え*モードかどうかを示します。

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>戻り値

複数列の並べ替えモードが有効になっている場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

複数列の並べ替えモードを有効または無効にするには[、CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)メソッドを使用します。 ヘッダー コントロールが複数列の並べ替えモードの場合、2 つ以上の列が並べ替えに参加できます。

## <a name="cmfcheaderctrlondrawitem"></a><a name="ondrawitem"></a>次の項目を表示します。

ヘッダー コントロール列を描画するために、フレームワークによって呼び出されます。

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
[in]デバイス コンテキストへのポインター。

*iItem*<br/>
[in]描画する項目の 0 から始まるインデックス。

*Rect*<br/>
[in]描画する項目の外接する四角形。

*バイスプレス*<br/>
[in]押された状態で項目を描画する場合は TRUE。それ以外の場合は FALSE。

*bIs強調表示*<br/>
[in]強調表示された状態で項目を描画する場合は TRUE。それ以外の場合は FALSE。

## <a name="cmfcheaderctrlondrawsortarrow"></a><a name="ondrawsortarrow"></a>次の矢印をクリックします。

並べ替え矢印を描画するためにフレームワークによって呼び出されます。

```
virtual void OnDrawSortArrow(
    CDC* pDC,
    CRect rectArrow);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

*直腸矢印*<br/>
[in]並べ替え矢印の外接する四角形。

## <a name="cmfcheaderctrlonfillbackground"></a><a name="onfillbackground"></a>次の文字列を使用します。

ヘッダー コントロール列の背景を埋めるために、フレームワークによって呼び出されます。

```
virtual void OnFillBackground(CDC* pDC);
```

### <a name="parameters"></a>パラメーター

*pDC*<br/>
[in]デバイス コンテキストへのポインター。

### <a name="remarks"></a>解説

## <a name="cmfcheaderctrlremovesortcolumn"></a><a name="removesortcolumn"></a>列を並べ替える

並べ替え列の一覧から指定した列を削除します。

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>パラメーター

*i列*<br/>
[in]削除する列の 0 から始まるインデックス。

## <a name="cmfcheaderctrlsetsortcolumn"></a><a name="setsortcolumn"></a>次の項目を選択します。

ヘッダー コントロール内の指定した列の並べ替え順序を設定します。

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending=TRUE,
    BOOL bAdd=FALSE);
```

### <a name="parameters"></a>パラメーター

*i列*<br/>
[in]ヘッダー コントロール列の 0 から始まるインデックス。 このパラメーターが 0 未満の場合、このメソッドは並べ替え列のリストからすべての列を削除します。

*b昇順*<br/>
[in]*iColumn*パラメーターで指定される列の並べ替え順序を指定します。 昇順を設定する場合は TRUE。降順を設定する場合は FALSE。 既定値は TRUE です。

*b追加*<br/>
[in]true を指定する列の並べ替え順序を設定する場合は*true。*

現在のヘッダー コントロールが*複数列の並べ替え*モードの場合、このメソッドは、指定された列を並べ替え列のリストに追加します。 複数列の並べ替えモードを設定するには[、CMFCHeaderCtrl::EnableMultipleSort](#enablemultiplesort)を使用します。

複数列の並べ替えモードが設定されていない場合、このメソッドはデバッグ モードでコンパイルされ、このメソッドはアサートします。 複数列の並べ替えモードが設定されていない場合、このメソッドは、小売モードでコンパイルされている場合、まず並べ替え列の一覧からすべての列を削除し、指定した列をリストに追加します。

FALSE を指定すると、まず並べ替え列の一覧からすべての列を削除し、次に指定した列をリストに追加します。 既定値は FALSE です。

### <a name="remarks"></a>解説

このメソッドは、列の並べ替え順序を設定するために使います。 必要に応じて、このメソッドは、並べ替え列のリストに列を追加します。 ヘッダー コントロールは、並べ替え順序を使用して、上または下を向く並べ替え矢印を描画します。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfclistctrl-class.md)
