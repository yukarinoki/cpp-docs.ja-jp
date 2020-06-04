---
title: クラス
ms.date: 07/30/2019
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
ms.openlocfilehash: 099ec086bd95a1180af4cf5a8f6a9fa7f1d099ea
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754230"
---
# <a name="cmfclistctrl-class"></a>クラス

クラス`CMFCListCtrl`は[、CMFCHeaderCtrl クラス](../../mfc/reference/clistctrl-class.md)の高度なヘッダーコントロール機能をサポートすることにより[、CListCtrl クラス](../../mfc/reference/cmfcheaderctrl-class.md)クラスの機能を拡張します。

## <a name="syntax"></a>構文

```
class CMFCListCtrl : public CListCtrl
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[列を並べ替え](#enablemarksortedcolumn)|並べ替えられた列に別の背景色でマークを付ける機能を有効にします。|
|[複数の並べ替えを有効にする](#enablemultiplesort)|複数の並べ替えモードを有効にします。|
|[次の項目を取得します。](#getheaderctrl)|下線付きヘッダー コントロールへの参照を返します。|
|[を選択します。](#ismultiplesort)|リスト コントロールが複数の並べ替えモードかどうかを確認します。|
|[アイテムを比較します。](#oncompareitems)|2 つのリスト コントロール項目を比較する必要があるときに、フレームワークによって呼び出されます。|
|[をクリックします。](#ongetcellbkcolor)|個々のセルの背景色を決定する必要があるときに、フレームワークによって呼び出されます。|
|[をクリックします。](#ongetcellfont)|描画されるセルのフォントを取得する必要があるときに、フレームワークによって呼び出されます。|
|[次の文字列を取得します。](#ongetcelltextcolor)|個々のセルのテキストの色を決定する必要があるときに、フレームワークによって呼び出されます。|
|[列を並べ替える](#removesortcolumn)|並べ替え列のリストから並べ替え列を削除します。|
|[列を並べ替える](#setsortcolumn)|現在の並べ替えられた列と並べ替え順序を設定します。|
|[並べ替え](#sort)|リスト コントロールを並べ替えます。|

## <a name="remarks"></a>解説

`CMFCListCtrl`[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)に 2 つの拡張機能を提供します。 まず、列の並べ替えが、ヘッダーに自動的に並べ替え矢印を描画することで、使用可能なオプションであることを示します。 次に、複数の列で同時にデータを並べ替えることができます。

## <a name="example"></a>例

`CMFCListCtrl` クラスのさまざまなメソッドの使用方法を次の例に示します。 この例では、リスト コントロールの作成、列の挿入、項目の挿入、項目のテキストの設定、およびリスト コントロールのフォントの設定方法を示します。 このコード スニペットは[、Visual Studio のデモ のサンプル](../../overview/visual-cpp-samples.md)の一部です。

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

## <a name="cmfclistctrlenablemarksortedcolumn"></a><a name="enablemarksortedcolumn"></a>列を並べ替え

並べ替えられた列に別の背景色を設定します。

```cpp
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>パラメーター

*bマーク*<br/>
[in]別の背景色を有効にするかどうかを決定するブール値パラメーター。

*引き出し*<br/>
[in]コントロールを直ちに再描画するかどうかを決定するブール値パラメーター。

### <a name="remarks"></a>解説

`EnableMarkSortedColumn`は、ソート`CDrawingManager::PixelAlpha`された列に使用する色を計算するためにメソッドを使用します。 選択される色は、通常の背景色に基づいています。

## <a name="cmfclistctrlenablemultiplesort"></a><a name="enablemultiplesort"></a>複数の並べ替えを有効にする

リスト コントロール内のデータ行を複数の列で並べ替えることができます。

```cpp
void EnableMultipleSort(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
[in]複数列の並べ替えモードを有効にするかどうかを指定するブール値。

### <a name="remarks"></a>解説

複数の列に基づいて並べ替えを有効にすると、列には階層が含まれます。 データ行は、最初にプライマリ列で並べ替えられます。 それに相当する値は、優先順位に基づいて後続の各列で並べ替えられます。

## <a name="cmfclistctrlgetheaderctrl"></a><a name="getheaderctrl"></a>次の項目を取得します。

ヘッダー コントロールへの参照を返します。

```
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```

### <a name="return-value"></a>戻り値

基になる[CMFC ヘッダーCtrl](../../mfc/reference/cmfcheaderctrl-class.md)オブジェクトへの参照。

### <a name="remarks"></a>解説

リスト コントロールのヘッダー コントロールは、列のタイトルを含むウィンドウです。 通常は、列の真上に配置されます。

## <a name="cmfclistctrlismultiplesort"></a><a name="ismultiplesort"></a>を選択します。

リスト コントロールが現在複数の列で並べ替えをサポートしているかどうかを確認します。

```
BOOL IsMultipleSort() const;
```

### <a name="return-value"></a>戻り値

リスト コントロールが複数の並べ替えをサポートする場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

[CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)が複数の並べ替えをサポートしている場合、ユーザーはリスト コントロール内のデータを複数の列で並べ替えることができます。 複数の並べ替えを有効にするには[、CMFCListCtrl::複数の並べ替えを呼び出します](#enablemultiplesort)。

## <a name="cmfclistctrloncompareitems"></a><a name="oncompareitems"></a>アイテムを比較します。

フレームワークは、2 つの項目を比較するときにこのメソッドを呼び出します。

```
virtual int OnCompareItems(
    LPARAM lParam1,
    LPARAM lParam2,
    int iColumn);
```

### <a name="parameters"></a>パラメーター

*lパラム1*<br/>
[in]比較する最初の項目。

*lパラム2*<br/>
[in]比較する 2 番目の項目。

*i列*<br/>
[in]このメソッドが並べ替える列のインデックス。

### <a name="return-value"></a>戻り値

2 つの項目の相対位置を示す整数。 負の値は、最初の項目が 2 番目の項目の前に、正の値が 2 番目の項目の後に 1 つ目の項目を続け、0 が 2 つの項目が等価であることを示します。

### <a name="remarks"></a>解説

既定の実装では、常に 0 が返されます。 独自の並べ替えアルゴリズムを提供するには、この関数をオーバーライドします。

## <a name="cmfclistctrlongetcellbkcolor"></a><a name="ongetcellbkcolor"></a>をクリックします。

フレームワークは、個々のセルの背景色を決定する必要がある場合に、このメソッドを呼び出します。

```
virtual COLORREF OnGetCellBkColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>パラメーター

*n行*<br/>
[in]対象のセルの行。

*n列*<br/>
[in]対象のセルの列。

### <a name="return-value"></a>戻り値

セルの背景色を指定する COLOREF 値。

### <a name="remarks"></a>解説

の既定の`OnGetCellBkColor`実装では、指定された入力パラメータを使用せず、代`GetBkColor`わりに単に を呼び出します。 したがって、既定では、リスト コントロール全体の背景色は同じです。 派生クラスで`OnGetCellBkColor`オーバーライドして、個々のセルを個別の背景色でマークできます。

## <a name="cmfclistctrlongetcellfont"></a><a name="ongetcellfont"></a>をクリックします。

フレームワークは、個々のセルのフォントを取得するときに、このメソッドを呼び出します。

```
virtual HFONT OnGetCellFont(
    int nRow,
    int nColumn,
    DWORD dwData = 0);
```

### <a name="parameters"></a>パラメーター

*n行*<br/>
[in]対象のセルの行。

*n列*<br/>
[in]対象のセルの列。

*dw データ*<br/>
[in]ユーザー定義データ。 既定の実装では、このパラメーターは使用されません。

### <a name="return-value"></a>戻り値

現在のセルに使用されるフォントへのハンドル。

### <a name="remarks"></a>解説

既定では、このメソッドは NULL を返します。 リスト コントロール内のすべてのセルのフォントが同じである。 セルごとに異なるフォントを提供するには、このメソッドをオーバーライドします。

## <a name="cmfclistctrlongetcelltextcolor"></a><a name="ongetcelltextcolor"></a>次の文字列を取得します。

フレームワークは、個々のセルのテキストの色を決定する必要がある場合に、このメソッドを呼び出します。

```
virtual COLORREF OnGetCellTextColor(
    int nRow,
    int nColumn);
```

### <a name="parameters"></a>パラメーター

*n行*<br/>
[in]対象のセルの行。

*n列*<br/>
[in]対象のセルの列。

### <a name="return-value"></a>戻り値

セルのテキストの色を指定する COLOREF 値。

### <a name="remarks"></a>解説

既定では、このメソッドは`GetTextColor`入力パラメーターに関係なく呼び出します。 リスト コントロール全体が同じテキスト色になります。 派生クラスで`OnGetCellTextColor`オーバーライドして、個々のセルを個別のテキスト色でマークできます。

## <a name="cmfclistctrlremovesortcolumn"></a><a name="removesortcolumn"></a>列を並べ替える

並べ替え列のリストから並べ替え列を削除します。

```cpp
void RemoveSortColumn(int iColumn);
```

### <a name="parameters"></a>パラメーター

*i列*<br/>
[in]削除する列。

### <a name="remarks"></a>解説

このメソッドは、ヘッダー コントロールから並べ替え列を削除します。 を呼[び](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)出します。

## <a name="cmfclistctrlsetsortcolumn"></a><a name="setsortcolumn"></a>列を並べ替える

現在の並べ替えられた列と並べ替え順序を設定します。

```cpp
void SetSortColumn(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>パラメーター

*i列*<br/>
[in]並べ替える列。

*b昇順*<br/>
[in]並べ替え順序を指定するブール値。

*b追加*<br/>
[in]メソッドが *、iColumn*で示す列を並べ替え列のリストに追加するかどうかを指定するブール値。

### <a name="remarks"></a>解説

このメソッドは、メソッド[CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)を使用して、入力パラメーターをヘッダー コントロールに渡します。

## <a name="cmfclistctrlsort"></a><a name="sort"></a>並べ替え

リスト コントロールを並べ替えます。

```
virtual void Sort(
    int iColumn,
    BOOL bAscending = TRUE,
    BOOL bAdd = FALSE);
```

### <a name="parameters"></a>パラメーター

*i列*<br/>
[in]並べ替える列。

*b昇順*<br/>
[in]並べ替え順序を指定するブール値。

*b追加*<br/>
[in]このメソッドが *、iColumn*で示す列を並べ替え列のリストに追加するかどうかを指定するブール値。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
