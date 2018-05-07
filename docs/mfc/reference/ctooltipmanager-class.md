---
title: CTooltipManager クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
dev_langs:
- C++
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78b191766e33d291317ef50a4d5373dc26428577
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ctooltipmanager-class"></a>CTooltipManager クラス
ツールヒントに関するランタイム情報を保持します。 `CTooltipManager` クラスのインスタンスは、アプリケーションごとに 1 回作成されます。  
  
## <a name="syntax"></a>構文  
  
```  
class CTooltipManager : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CTooltipManager::CreateToolTip](#createtooltip)|指定された Windows コントロールの種類のツールヒント コントロールを作成します。|  
|[CTooltipManager::DeleteToolTip](#deletetooltip)|ツールヒント コントロールを削除します。|  
|[:Settooltipparams](#settooltipparams)|指定された Windows コントロールの種類のツールヒント コントロールの外観をカスタマイズします。|  
|[CTooltipManager::SetTooltipText](#settooltiptext)|ツールヒント コントロールのテキストと説明を設定します。|  
|[CTooltipManager::UpdateTooltips](#updatetooltips)||  
  
## <a name="remarks"></a>コメント  
 使用して[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo`、および`CTooltipManager`アプリケーションでカスタマイズされたツールヒントを実装します。 これらのツールヒントのクラスを使用する方法の例は、次を参照してください。、 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)トピックです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxtooltipmanager.h  
  
##  <a name="createtooltip"></a>  CTooltipManager::CreateToolTip  
 ツール ヒント コントロールを作成します。  
  
```  
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,  
    CWnd* pWndParent,  
    UINT nType);
```  
  
### <a name="parameters"></a>パラメーター  
 [出力] `pToolTip`  
 ツールヒントのポインターへの参照。 新しく作成されたツールヒントを指す、関数が戻るときに設定されます。  
  
 [入力] `pWndParent`  
 ツールヒントの親です。  
  
 [入力] `nType`  
 ツール ヒントの種類です。  
  
### <a name="return-value"></a>戻り値  
 0 以外の場合、ツール ヒントが正常に作成されました。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります[CTooltipManager::DeleteToolTip](#deletetooltip)で戻されたツールヒント コントロールを削除する`pToolTip`です。  
  
 [CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)する種類のセットを作成する各ツールヒントのビジュアル表示パラメーターがツールヒントに基づく`nType`を指定します。 1 つまたは複数のツールヒント型のパラメーターを変更するには、呼び出す[:settooltipparams](#settooltipparams)です。  
  
 有効なツールヒントの種類は、次の表のとおりです。  
  
|ツールヒントの種類|コントロールの分類|種類の例|  
|------------------|----------------------|-------------------|  
|AFX_TOOLTIP_TYPE_BUTTON|ボタンをクリックします。|CMFCButton|  
|AFX_TOOLTIP_TYPE_CAPTIONBAR|キャプション バーです。|CMFCCaptionBar|  
|AFX_TOOLTIP_TYPE_DEFAULT|別のカテゴリに適合しないコントロールです。|なし。|  
|AFX_TOOLTIP_TYPE_DOCKBAR|ドッキング可能なウィンドウ。|CDockablePane|  
|AFX_TOOLTIP_TYPE_EDIT|テキスト ボックスです。|なし。|  
|AFX_TOOLTIP_TYPE_MINIFRAME|ミニフレームです。|CPaneFrameWnd|  
|AFX_TOOLTIP_TYPE_PLANNER|プランナー|なし。|  
|AFX_TOOLTIP_TYPE_RIBBON|リボン バー。|CMFCRibbonBar、CMFCRibbonPanelMenuBar|  
|AFX_TOOLTIP_TYPE_TAB|タブ コントロールです。|CMFCTabCtrl|  
|AFX_TOOLTIP_TYPE_TOOLBAR|ツールバーです。|CMFCToolBar、CMFCPopupMenuBar|  
|AFX_TOOLTIP_TYPE_TOOLBOX|ツールボックス。|なし。|  
  
##  <a name="deletetooltip"></a>  CTooltipManager::DeleteToolTip  
 ツールヒント コントロールを削除します。  
  
```  
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力、出力] `pToolTip`  
 破棄するツールヒントへのポインターへの参照。  
  
### <a name="remarks"></a>コメント  
 このメソッドの各呼び出し[CToolTipCtrl クラス](../../mfc/reference/ctooltipctrl-class.md)によって作成された[CTooltipManager::CreateToolTip](#createtooltip)です。 親コントロールからこのメソッドを呼び出す必要があります、`OnDestroy`ハンドラー。 これは、正しくフレームワークからヒントを削除する必要があります。 このメソッドは設定`pToolTip`に`NULL`を返す前にします。  
  
##  <a name="settooltipparams"></a>  :Settooltipparams  
 指定された Windows コントロールの種類のツールヒント コントロールの外観をカスタマイズします。  
  
```  
void SetTooltipParams(
    UINT nTypes,  
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),  
    CMFCToolTipInfo* pParams=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `nTypes`  
 コントロールの種類を指定します。  
  
 [入力] `pRTC`  
 カスタム ツールヒントのランタイム クラスです。  
  
 [入力] `pParams`  
 ツール ヒントのパラメーターです。  
  
### <a name="remarks"></a>コメント  
 このメソッドを設定、ランタイム クラスと最初のパラメーターを[CToolTipManager](../../mfc/reference/ctooltipmanager-class.md)ツールヒントを作成するときに使用します。 コントロールを呼び出すと[CTooltipManager::CreateToolTip](#createtooltip)がツールヒントにパスとなる型で示される型の 1 つと`nTypes`、ツールヒント マネージャーは、指定されたランタイム クラスのインスタンスであるツールヒント コントロールを作成によって`pRTC`で指定されたパラメーターを渡す`pParams`新しいツールヒントにします。  
  
 このメソッドを呼び出す、既存のすべてのツールヒント所有者が AFX_WM_UPDATETOOLTIPS メッセージを受信しすると、ツールヒントを使用して再作成する必要があります[CTooltipManager::CreateToolTip](#createtooltip)です。  
  
 `nTypes` 有効なツールヒントの任意の組み合わせの種類を指定できます[CTooltipManager::CreateToolTip](#createtooltip)が使用することもできます AFX_TOOLTIP_TYPE_ALL です。 AFX_TOOLTIP_TYPE_ALL を渡すと、すべてのツール ヒントの種類に影響します。  
  
### <a name="example"></a>例  
 次の例で使用する方法、`SetTooltipParams`のメソッド、`CTooltipManager`クラスです。 このコード スニペットは、「 [クライアント サンプルの描画](../../visual-cpp-samples.md)」の一部です。  
  
 [!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]  
  
##  <a name="settooltiptext"></a>  CTooltipManager::SetTooltipText  
 テキストとツールヒントの説明を設定します。  
  
```  
static void SetTooltipText(
    TOOLINFO* pTI,  
    CToolTipCtrl* pToolTip,  
    UINT nType,  
    const CString strText,  
    LPCTSTR lpszDescr=NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 [入力] `pTI`  
 TOOLINFO オブジェクトへのポインター。  
  
 [入力、出力] `pToolTip`  
 テキストと説明を設定する対象のツールヒント コントロールへのポインター。  
  
 [入力] `nType`  
 このツールヒントが関連付けられているコントロールの種類を指定します。  
  
 [入力] `strText`  
 ツールヒントのテキストとして設定するテキストです。  
  
 [入力] `lpszDescr`  
 ツールヒントの説明へのポインター。 指定できます`NULL`です。  
  
### <a name="remarks"></a>コメント  
 値`nType`と同じ値にする必要があります、`nType`のパラメーター [CTooltipManager::CreateToolTip](#createtooltip)ツールヒントを作成したときにします。  
  
##  <a name="updatetooltips"></a>  CTooltipManager::UpdateTooltips  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void UpdateTooltips();
```  
  
### <a name="remarks"></a>コメント  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../../mfc/reference/mfc-classes.md)   
 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)   
 [CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)
