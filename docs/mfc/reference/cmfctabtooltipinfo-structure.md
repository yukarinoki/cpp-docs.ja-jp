---
title: CMFCTabToolTipInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: a507d1e69b3524074e50fde0e87fc5ebb6e5ca03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367340"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo 構造体

この構造体は、ユーザーがマウスを移動している MDI タブに関する情報を提供します。

## <a name="syntax"></a>構文

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>メンバー

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[ヒント::m_nTabIndex](#m_ntabindex)|タブ コントロールのインデックスを指定します。|
|[ヒント::m_pTabWnd](#m_ptabwnd)|タブ コントロールへのポインター。|
|[ヒント::m_strText](#m_strtext)|ツールヒントのテキスト。|

## <a name="remarks"></a>解説

`CMFCTabToolTipInfo`構造体へのポインターは、AFX_WM_ON_GET_TAB_TOOLTIP メッセージのパラメーターとして渡されます。 このメッセージは、MDI タブが有効で、ユーザーがタブ コントロールの上にマウス を移動すると生成されます。

## <a name="example"></a>例

次の例は`CMFCTabToolTipInfo`[、MDITabsDemo のサンプル](../../overview/visual-cpp-samples.md)で使用される方法を示しています: MFC タブ付き MDI アプリケーション 。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxbasetabctrl.h

## <a name="cmfctabtooltipinfom_ntabindex"></a><a name="m_ntabindex"></a>ヒント::m_nTabIndex

タブ コントロールのインデックスを指定します。

```
int m_nTabIndex;
```

### <a name="remarks"></a>解説

ユーザーがホバーしているタブのインデックス。

### <a name="example"></a>例

次の例は`m_nTabIndex`[、MDITabsDemo のサンプル](../../overview/visual-cpp-samples.md)で使用される方法を示しています: MFC タブ付き MDI アプリケーション 。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_ptabwnd"></a><a name="m_ptabwnd"></a>ヒント::m_pTabWnd

タブ コントロールへのポインター。

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>例

次の例は`m_pTabWnd`[、MDITabsDemo のサンプル](../../overview/visual-cpp-samples.md)で使用される方法を示しています: MFC タブ付き MDI アプリケーション 。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_strtext"></a><a name="m_strtext"></a>ヒント::m_strText

ツールヒントのテキスト。

```
CString m_strText;
```

### <a name="remarks"></a>解説

文字列が空の場合、ツールヒントは表示されません。

### <a name="example"></a>例

次の例は`m_strText`[、MDITabsDemo のサンプル](../../overview/visual-cpp-samples.md)で使用される方法を示しています: MFC タブ付き MDI アプリケーション 。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
