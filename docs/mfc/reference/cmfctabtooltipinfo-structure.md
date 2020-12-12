---
description: '詳細については、次を参照してください: CMFCTabToolTipInfo 構造体'
title: CMFCTabToolTipInfo 構造体
ms.date: 11/04/2016
f1_keywords:
- CMFCTabToolTipInfo
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
ms.openlocfilehash: ce9e9f4fdbcf367921e7f0559a4d04e66f4303dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164069"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo 構造体

この構造体は、ユーザーがマウスポインターを置いている MDI タブに関する情報を提供します。

## <a name="syntax"></a>構文

```
struct CMFCTabToolTipInfo
```

## <a name="members"></a>メンバー

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCTabToolTipInfo:: m_nTabIndex](#m_ntabindex)|タブコントロールのインデックスを指定します。|
|[CMFCTabToolTipInfo:: m_pTabWnd](#m_ptabwnd)|タブコントロールへのポインター。|
|[CMFCTabToolTipInfo:: m_strText](#m_strtext)|ツールヒントのテキスト。|

## <a name="remarks"></a>解説

構造体へのポインター `CMFCTabToolTipInfo` は、AFX_WM_ON_GET_TAB_TOOLTIP メッセージのパラメーターとして渡されます。 このメッセージは、MDI タブが有効になっていて、ユーザーがタブコントロールの上にマウスを置いたときに生成されます。

## <a name="example"></a>例

次の例 `CMFCTabToolTipInfo` では、を [Mditabsdemo サンプル: MFC タブ付き MDI アプリケーション](../../overview/visual-cpp-samples.md)で使用する方法を示します。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="inheritance-hierarchy"></a>継承階層

[CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxbasetabctrl.h

## <a name="cmfctabtooltipinfom_ntabindex"></a><a name="m_ntabindex"></a> CMFCTabToolTipInfo:: m_nTabIndex

タブコントロールのインデックスを指定します。

```
int m_nTabIndex;
```

### <a name="remarks"></a>解説

ユーザーがカーソルを置いているタブのインデックス。

### <a name="example"></a>例

次の例 `m_nTabIndex` では、を [Mditabsdemo サンプル: MFC タブ付き MDI アプリケーション](../../overview/visual-cpp-samples.md)で使用する方法を示します。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_ptabwnd"></a><a name="m_ptabwnd"></a> CMFCTabToolTipInfo:: m_pTabWnd

タブコントロールへのポインター。

```
CMFCBaseTabCtrl* m_pTabWnd;
```

### <a name="example"></a>例

次の例 `m_pTabWnd` では、を [Mditabsdemo サンプル: MFC タブ付き MDI アプリケーション](../../overview/visual-cpp-samples.md)で使用する方法を示します。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="cmfctabtooltipinfom_strtext"></a><a name="m_strtext"></a> CMFCTabToolTipInfo:: m_strText

ツールヒントのテキスト。

```
CString m_strText;
```

### <a name="remarks"></a>解説

文字列が空の場合、ツールヒントは表示されません。

### <a name="example"></a>例

次の例 `m_strText` では、を [Mditabsdemo サンプル: MFC タブ付き MDI アプリケーション](../../overview/visual-cpp-samples.md)で使用する方法を示します。

[!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)
