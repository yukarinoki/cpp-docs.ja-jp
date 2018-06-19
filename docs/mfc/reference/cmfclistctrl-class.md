---
title: CMFCListCtrl クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 495bf2a3eab9ceee4ca0bab337d590c1820905e8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369623"
---
# <a name="cmfclistctrl-class"></a>CMFCListCtrl クラス
`CMFCListCtrl`クラスの機能を拡張する[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)クラス、高度なヘッダー コントロールの機能をサポートすることにより、 [CMFCHeaderCtrl クラス](../../mfc/reference/cmfcheaderctrl-class.md)です。  
  
## <a name="syntax"></a>構文  
  
```  
class CMFCListCtrl : public CListCtrl  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMFCListCtrl::EnableMarkSortedColumn](#enablemarksortedcolumn)|並べ替える列を別の背景色を設定する機能を有効にします。|  
|[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)|複数の並べ替えモードを有効にします。|  
|[CMFCListCtrl::GetHeaderCtrl](#getheaderctrl)|下線付きのヘッダー コントロールへの参照を返します。|  
|[CMFCListCtrl::IsMultipleSort](#ismultiplesort)|かどうか、リスト コントロールが複数の並べ替えモードを確認します。|  
|[CMFCListCtrl::OnCompareItems](#oncompareitems)|2 つのリスト コントロール項目を比較する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellBkColor](#ongetcellbkcolor)|個々 のセルの背景色を確認する必要がありますがある場合に、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellFont](#ongetcellfont)|描画されるセルのフォントを取得する必要があるときに、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::OnGetCellTextColor](#ongetcelltextcolor)|個々 のセルのテキストの色を確認する必要がありますがある場合に、フレームワークによって呼び出されます。|  
|[CMFCListCtrl::RemoveSortColumn](#removesortcolumn)|並べ替えられた列の一覧から、並べ替え列を削除します。|  
|[CMFCListCtrl::SetSortColumn](#setsortcolumn)|現在の並べ替え列と並べ替え順序を設定します。|  
|[CMFCListCtrl::Sort](#sort)|リスト コントロールを並べ替えます。|  
  
## <a name="remarks"></a>コメント  
 `CMFCListCtrl` 2 つの拡張を提供[CListCtrl クラス](../../mfc/reference/clistctrl-class.md)クラスです。 最初に、列の並べ替えが利用可能なオプションのヘッダーに並べ替え矢印を自動的に描画することによってを示します。 次に、データの同時に複数の列で並べ替えをサポートします。  
  
## <a name="example"></a>例  
 次の例では、さまざまなメソッドを使用する方法、`CMFCListCtrl`クラスです。 この例では、リスト コントロールを作成、列を挿入する、項目の挿入、アイテムのテキストを設定およびリスト コントロールのフォントを設定する方法を示します。 このコード スニペットの一部である、 [Visual Studio のデモ サンプル](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#25](../../mfc/codesnippet/cpp/cmfclistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_VisualStudioDemo#26](../../mfc/codesnippet/cpp/cmfclistctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxlistctrl.h  
  
##  <a name="enablemarksortedcolumn"></a>  CMFCListCtrl::EnableMarkSortedColumn  
 別の背景色の並べ替えられた列をマークします。  
  
```  
void EnableMarkSortedColumn(
    BOOL bMark = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bMark`  
 別の背景色を有効にするかどうかを決定するブール型のパラメーターです。  
  
 [入力] `bRedraw`  
 コントロールをすぐに再描画するかどうかを決定するブール型のパラメーターです。  
  
### <a name="remarks"></a>コメント  
 `EnableMarkSortedColumn` メソッドを使用して`CDrawingManager::PixelAlpha`用に使用する色を計算する列を並べ替えられます。 選択される色は、標準の背景色に基づいています。  
  
##  <a name="enablemultiplesort"></a>  CMFCListCtrl::EnableMultipleSort  
 複数の列でリスト コントロール内のデータの行の並べ替えを有効にします。  
  
```  
void EnableMultipleSort(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `bEnable`  
 複数の列の並べ替えモードを有効にするかどうかを指定するブール値。  
  
### <a name="remarks"></a>コメント  
 複数の列に基づく並べ替えを有効にすると、列は、階層を持つ操作を行います。 データの行は、まず主列で並べ替えられます。 対応する値は、優先度に基づいた後続の各列で並べ替えられます。  
  
##  <a name="getheaderctrl"></a>  CMFCListCtrl::GetHeaderCtrl  
 ヘッダー コントロールへの参照を返します。  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>戻り値  
 基になるへの参照を[CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md)オブジェクト。  
  
### <a name="remarks"></a>コメント  
 リスト コントロールのヘッダー コントロールは、列のタイトルを含むウィンドウです。 これは通常、列のすぐ上にあります。  
  
##  <a name="ismultiplesort"></a>  CMFCListCtrl::IsMultipleSort  
 リスト コントロールの現在がサポートするか複数の列で並べ替えを確認します。  
  
```  
BOOL IsMultipleSort() const;  
```  
  
### <a name="return-value"></a>戻り値  
 `TRUE` リスト コントロールには、複数の並べ替えがサポートされている場合`FALSE`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 ときに、 [CMFCListCtrl クラス](../../mfc/reference/cmfclistctrl-class.md)複数の並べ替えをサポートしているユーザーは、複数の列でリスト コントロール内のデータを並べ替えることができます。 複数の並べ替えを有効にするを呼び出す[CMFCListCtrl::EnableMultipleSort](#enablemultiplesort)です。  
  
##  <a name="oncompareitems"></a>  CMFCListCtrl::OnCompareItems  
 フレームワークは、2 つの項目を比較するときに、このメソッドを呼び出します。  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `lParam1`  
 比較する最初の項目です。  
  
 [入力] `lParam2`  
 比較する 2 番目の項目です。  
  
 [入力] `iColumn`  
 このメソッドは、並べ替え、列のインデックス。  
  
### <a name="return-value"></a>戻り値  
 2 つのアイテムの相対位置を示す整数。 負の値は、こと、2 つ目の前に指定する必要があります最初の項目、正の値を示しますを最初の項目が、2 番目に従う必要があります 0 は、2 つの項目が同等であることを意味を示します。  
  
### <a name="remarks"></a>コメント  
 既定の実装を常に 0 を返します。 並べ替えアルゴリズムを指定するには、この関数をオーバーライドする必要があります。  
  
##  <a name="ongetcellbkcolor"></a>  CMFCListCtrl::OnGetCellBkColor  
 フレームワークは、個々 のセルの背景色を確認する必要がありますがある場合、このメソッドを呼び出します。  
  
```  
virtual COLORREF OnGetCellBkColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRow`  
 対象のセルの行。  
  
 [入力] `nColumn`  
 対象のセルの列です。  
  
### <a name="return-value"></a>戻り値  
 A`COLOREF`セルの背景色を指定する値。  
  
### <a name="remarks"></a>コメント  
 既定の実装`OnGetCellBkColor`指定された入力パラメーターを使用しないと、代わりを呼び出すだけ`GetBkColor`です。 したがって、既定では、リスト コントロール全体は、同じの背景色があります。 オーバーライドできます`OnGetCellBkColor`を別の背景色で個々 のセルをマークする派生クラスでします。  
  
##  <a name="ongetcellfont"></a>  CMFCListCtrl::OnGetCellFont  
 フレームワークは、個々 のセルのフォントを取得する場合、このメソッドを呼び出します。  
  
```  
virtual HFONT OnGetCellFont(
    int nRow,  
    int nColumn,  
    DWORD dwData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRow`  
 対象のセルの行。  
  
 [入力] `nColumn`  
 対象のセルの列です。  
  
 [入力] `dwData`  
 ユーザー定義データ。 既定の実装では、このパラメーターは使用しません。  
  
### <a name="return-value"></a>戻り値  
 現在のセルで使用されているフォントへのハンドル。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドが戻る`NULL`です。 リスト コントロール内のセルのすべてである同じフォント。 各セルで異なるフォントを提供するために、このメソッドをオーバーライドします。  
  
##  <a name="ongetcelltextcolor"></a>  CMFCListCtrl::OnGetCellTextColor  
 フレームワークは、個々 のセルのテキストの色を決定する必要があるときに、このメソッドを呼び出します。  
  
```  
virtual COLORREF OnGetCellTextColor(
    int nRow,  
    int nColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nRow`  
 対象のセルの行。  
  
 [入力] `nColumn`  
 対象のセルの列です。  
  
### <a name="return-value"></a>戻り値  
 A`COLOREF`セルのテキストの色を指定する値。  
  
### <a name="remarks"></a>コメント  
 既定では、このメソッドを呼び出す`GetTextColor`入力パラメーターに関係なく。 リスト コントロール全体は、同じテキストの色があります。 オーバーライドできます`OnGetCellTextColor`を別のテキストの色で個々 のセルをマークする派生クラスでします。  
  
##  <a name="removesortcolumn"></a>  CMFCListCtrl::RemoveSortColumn  
 並べ替えられた列の一覧から、並べ替え列を削除します。  
  
```  
void RemoveSortColumn(int iColumn);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 削除する列。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ヘッダー コントロールから並べ替え列を削除します。 呼び出す[CMFCHeaderCtrl::RemoveSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#removesortcolumn)です。  
  
##  <a name="setsortcolumn"></a>  CMFCListCtrl::SetSortColumn  
 現在の並べ替え列と並べ替え順序を設定します。  
  
```  
void SetSortColumn(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 並べ替える列。  
  
 [入力] `bAscending`  
 並べ替え順序を指定するブール値。  
  
 [入力] `bAdd`  
 メソッドによって示される列かどうかを指定するブール値を`iColumn`並べ替え列の一覧にします。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、メソッドを使用して、ヘッダー コントロールに入力パラメーターを渡します[CMFCHeaderCtrl::SetSortColumn](../../mfc/reference/cmfcheaderctrl-class.md#setsortcolumn)です。  
  
##  <a name="sort"></a>  CMFCListCtrl::Sort  
 リスト コントロールを並べ替えます。  
  
```  
virtual void Sort(
    int iColumn,  
    BOOL bAscending = TRUE,  
    BOOL bAdd = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `iColumn`  
 並べ替える列。  
  
 [入力] `bAscending`  
 並べ替え順序を指定するブール値。  
  
 [入力] `bAdd`  
 このメソッドによって示される列かどうかを指定するブール値を`iColumn`並べ替え列の一覧にします。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CListCtrl クラス](../../mfc/reference/clistctrl-class.md)
