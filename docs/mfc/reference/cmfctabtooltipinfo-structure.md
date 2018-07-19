---
title: CMFCTabToolTipInfo 構造 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabToolTipInfo
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabToolTipInfo struct
ms.assetid: 9c3b3fb9-1497-4d59-932b-0da9348dd5e2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e27dfd3570226aeab20d10f204d147f9f2b456d
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037484"
---
# <a name="cmfctabtooltipinfo-structure"></a>CMFCTabToolTipInfo 構造体
この構造体は、ユーザーのホバー MDI タブの情報を提供します。  
  
## <a name="syntax"></a>構文  
  
```  
struct CMFCTabToolTipInfo  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="data-members"></a>データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CMFCTabToolTipInfo::m_nTabIndex](#m_ntabindex)|タブ コントロールのインデックスを指定します。|  
|[CMFCTabToolTipInfo::m_pTabWnd](#m_ptabwnd)|タブ コントロールへのポインター。|  
|[CMFCTabToolTipInfo::m_strText](#m_strtext)|ツールヒントのテキスト。|  
  
## <a name="remarks"></a>Remarks  
 ポインター、`CMFCTabToolTipInfo`構造は AFX_WM_ON_GET_TAB_TOOLTIP メッセージのパラメーターとして渡されます。 MDI タブが有効になっており、ユーザーがタブ コントロール上に置いたときに、このメッセージが生成されます。  
  
## <a name="example"></a>例  
 例を次にどのように`CMFCTabToolTipInfo`で使用される、 [MDITabsDemo サンプル: MDI タブ付きアプリケーションを MFC](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CMFCTabToolTipInfo](../../mfc/reference/cmfctabtooltipinfo-structure.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxbasetabctrl.h  
  
##  <a name="m_ntabindex"></a>  CMFCTabToolTipInfo::m_nTabIndex  
 タブ コントロールのインデックスを指定します。  
  
```  
int m_nTabIndex;  
```  
  
### <a name="remarks"></a>Remarks  
 ユーザーのホバーをタブのインデックス。  
  
### <a name="example"></a>例  
 例を次にどのように`m_nTabIndex`で使用される、 [MDITabsDemo サンプル: MDI タブ付きアプリケーションを MFC](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_ptabwnd"></a>  CMFCTabToolTipInfo::m_pTabWnd  
 タブ コントロールへのポインター。  
  
```  
CMFCBaseTabCtrl* m_pTabWnd;  
```  
  
### <a name="example"></a>例  
 例を次にどのように`m_pTabWnd`で使用される、 [MDITabsDemo サンプル: MDI タブ付きアプリケーションを MFC](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
##  <a name="m_strtext"></a>  CMFCTabToolTipInfo::m_strText  
 ツールヒントのテキスト。  
  
```  
CString m_strText;  
```  
  
### <a name="remarks"></a>Remarks  
 文字列が空の場合、ツールヒントは表示されません。  
  
### <a name="example"></a>例  
 例を次にどのように`m_strText`で使用される、 [MDITabsDemo サンプル: MDI タブ付きアプリケーションを MFC](../../visual-cpp-samples.md)です。  
  
 [!code-cpp[NVC_MFC_MDITabsDemo#2](../../mfc/reference/codesnippet/cpp/cmfctabtooltipinfo-structure_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)
