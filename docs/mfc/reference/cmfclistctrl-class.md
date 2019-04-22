---
title: CMFCListCtrl クラス
ms.date: 11/04/2016
f1_keywords:
- CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl
- AFXLISTCTRL/CMFCListCtrl::EnableMarkSortedColumn
- AFXLISTCTRL/CMFCListCtrl::EnableMultipleSort
- AFXLISTCTRL/CMFCListCtrl::GetHeaderCtrl
- AFXLISTCTRL/CMFCListCtrl::IsMultipleSort
- AFXLISTCTRL/CMFCListCtrl::OnCompareItems
- AFXLISTCTRL/CMFCListCtrl::OnGetCellBkColor
- AFXLISTCTRL/CMFCListCtrl::OnGetCellFont
- AFXLISTCTRL/CMFCListCtrl::OnGetCellTextColor
- AFXLISTCTRL/CMFCListCtrl::RemoveSortColumn
- AFXLISTCTRL/CMFCListCtrl::SetSortColumn
- AFXLISTCTRL/CMFCListCtrl::Sort
helpviewer_keywords:
- CMFCListCtrl [MFC], EnableMarkSortedColumn
- CMFCListCtrl [MFC], EnableMultipleSort
- CMFCListCtrl [MFC], GetHeaderCtrl
- CMFCListCtrl [MFC], IsMultipleSort
- CMFCListCtrl [MFC], OnCompareItems
- CMFCListCtrl [MFC], OnGetCellBkColor
- CMFCListCtrl [MFC], OnGetCellFont
- CMFCListCtrl [MFC], OnGetCellTextColor
- CMFCListCtrl [MFC], RemoveSortColumn
- CMFCListCtrl [MFC], SetSortColumn
- CMFCListCtrl [MFC], Sort
ms.assetid: 50d16aee-138c-4f34-8690-cb75d544ef2e
ms.openlocfilehash: 4cd1bb7787f8797984bdce5f9a5b3080d69ea5f2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58767939"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl クラス

`CMFCListCtrl`クラスの機能を拡張する[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)クラスの高度なヘッダー コントロール機能をサポートすることによって、 [CMFCHeaderCtrl クラス](../../mfc/reference/cmfcheaderctrl-class.md)します。

## <a name="syntax"></a>構文

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|別の背景色で並べ替えられた列を設定する機能を有効にします。|
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|複数の並べ替えモードを有効にします。|
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|下線付きのヘッダー コントロールへの参照を返します。|
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|リスト コントロールの複数の並べ替えモードを確認します。|
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|2 つのリスト コントロール項目を比較する必要があるときに、フレームワークによって呼び出されます。|
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|個々 のセルの背景色を決定する必要があるときに、フレームワークによって呼び出されます。|
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|描画されるセルのフォントを取得する必要があるときに、フレームワークによって呼び出されます。|
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|個々 のセルのテキストの色を決定する必要があるときに、フレームワークによって呼び出されます。|
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|並べ替えられた列の一覧から、並べ替え列を削除します。|
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|現在の並べ替えられた列と並べ替え順序を設定します。|
|[CMFCListCtrl::Sort](#sort)|リスト コントロールを並べ替えます。|

## <a name="remarks"></a>Remarks

`CMFCListCtrl` 2 つの機能強化を提供しています。 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)クラス。 最初に、自動的にヘッダーの並べ替え矢印を描画することで、利用可能なオプションは、列の並べ替えことを示します。 次に、データの同時に複数の列で並べ替えをサポートします。

## <a name="example"></a>例

`CMFCListCtrl` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、リスト コントロールを作成、列を挿入する、項目を挿入、アイテムのテキストを設定およびリスト コントロールのフォントを設定する方法を示します。 このコード スニペットの一部、 [Visual Studio のデモ サンプル](../../overview/visual-cpp-samples.md)します。

[!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListCtrl](../../mfc/reference/clistctrl-class.md)

[CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxlistctrl.h

##  <a name="enablemarksortedcolumn"></a>  CMFCListCtrl::EnableMarkSortedColumn

別の背景色で並べ替えられた列をマークします。

```
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*bMark*<br/>
[in]別の背景色を有効にするかどうかを決定するブール型パラメーター。

*bRedraw*<br/>
[in]コントロールをすぐに再描画するかどうかを決定するブール型パラメーター。

### <a name="remarks"></a>Remarks

`EnableMarkSortedColumn` メソッドを使用して`CDrawingManager::PixelAlpha`並べ替えられた列に使用する色を計算します。 色の選択は、標準の背景色に基づいています。

##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort

リスト コントロール内のデータの行を複数の列による並べ替えを有効にします。

```
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*bEnable*<br/>
[in]複数の列の並べ替えモードを有効にするかどうかを指定するブール値。

### <a name="remarks"></a>Remarks

複数の列に基づいて並べ替えを有効にすると、列は、階層がある操作を行います。 データの行は、まずプライマリの列で並べ替えられます。 対応する値は、優先順位に基づく各後続の列で並べ替えられます。

##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl

ヘッダー コントロールへの参照を返します。

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>戻り値

基になるへの参照を[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)オブジェクト。

### <a name="remarks"></a>Remarks

リスト コントロールのヘッダー コントロールは、列のタイトルを含むウィンドウです。 これは通常、列のすぐ上にあります。

##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort

リスト コントロール現在がサポートするか複数の列で並べ替えを確認します。

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>戻り値

リスト コントロールは、複数の並べ替えをサポートしている場合は TRUE。FALSE それ以外の場合。

### <a name="remarks"></a>Remarks

ときに、 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)、複数の並べ替えをサポートしているユーザーは、複数の列で、リスト コントロール内のデータを並べ替えることができます。 複数の並べ替えを有効にする[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)します。

##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems

フレームワークは、2 つの項目を比較する際に、このメソッドを呼び出します。

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>パラメーター

*lParam1*<br/>
[in]比較する最初の項目。

*lParam2*<br/>
[in]比較する 2 番目の項目。

*iColumn*<br/>
[in]このメソッドを並べ替え列のインデックス。

### <a name="return-value"></a>戻り値

2 つの項目の相対位置を示す整数。 負の値は、こと、2 つ目の前に指定する必要があります最初の項目、正の値を示すことの最初の項目は、2 番目に従う必要がある 0 では、2 つの項目が同等であることを意味を示します。

### <a name="remarks"></a>Remarks

既定の実装を常に 0 を返します。 並べ替えアルゴリズムを提供するには、この関数をオーバーライドする必要があります。

##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor

フレームワークは、個々 のセルの背景色を決定する必要があるときに、このメソッドを呼び出します。

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>パラメーター

*nRow*<br/>
[in]問題のセルの行。

*nColumn*<br/>
[in]問題のセルの列です。

### <a name="return-value"></a>戻り値

セルの背景色を示す COLOREF 値。

### <a name="remarks"></a>Remarks

既定の実装`OnGetCellBkColor`指定された入力パラメーターを使用しないと、代わりに単に呼び出します`GetBkColor`します。 そのため、既定では、リスト コントロール全体は、同じ背景色があります。 オーバーライドできます`OnGetCellBkColor`別の背景色で個々 のセルをマークする派生クラスでします。

##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont

フレームワークは、個々 のセルのフォントを取得する場合、このメソッドを呼び出します。

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>パラメーター

*nRow*<br/>
[in]問題のセルの行。

*nColumn*<br/>
[in]問題のセルの列です。

*dwData*<br/>
[in]ユーザー定義データ。 既定の実装では、このパラメーターを使用しません。

### <a name="return-value"></a>戻り値

現在のセルで使用されるフォントへのハンドル。

### <a name="remarks"></a>Remarks

既定では、このメソッドは、NULL を返します。 リスト コントロール内のセルのすべてで同じフォントがあります。 別のセルのフォントの種類を提供するために、このメソッドをオーバーライドします。

##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor

フレームワークは、個々 のセルのテキストの色を決定する必要があるときに、このメソッドを呼び出します。

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>パラメーター

*nRow*<br/>
[in]問題のセルの行。

*nColumn*<br/>
[in]問題のセルの列です。

### <a name="return-value"></a>戻り値

セルのテキストの色を示す COLOREF 値。

### <a name="remarks"></a>Remarks

既定では、このメソッドを呼び出す`GetTextColor`入力パラメーターに関係なく。 リスト コントロール全体では、同じテキストの色があります。 オーバーライドできます`OnGetCellTextColor`別のテキストの色で個々 のセルをマークする派生クラスでします。

##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn

並べ替えられた列の一覧から、並べ替え列を削除します。

```
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>パラメーター

*iColumn*<br/>
[in]削除する列。

### <a name="remarks"></a>Remarks

このメソッドは、ヘッダー コントロールの並べ替え列を削除します。 呼び出す[CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)します。

##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn

現在の並べ替えられた列と並べ替え順序を設定します。

```
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>パラメーター

*iColumn*<br/>
[in]並べ替える列。

*bAscending*<br/>
[in]並べ替え順序を指定するブール値。

*bAdd*<br/>
[in]メソッドによって示される列かどうかを指定するブール値を*iColumn*並べ替え列の一覧にします。

### <a name="remarks"></a>Remarks

このメソッドは、メソッドを使用して、ヘッダー コントロールに入力パラメーターを渡します[CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)します。

##  <a name="sort"></a>  CMFCListCtrl::Sort

リスト コントロールを並べ替えます。

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>パラメーター

*iColumn*<br/>
[in]並べ替える列。

*bAscending*<br/>
[in]並べ替え順序を指定するブール値。

*bAdd*<br/>
[in]このメソッドによって示される列かどうかを指定するブール値を*iColumn*並べ替え列の一覧にします。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
