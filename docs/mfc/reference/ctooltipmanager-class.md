---
description: '詳細情報: CTooltipManager クラス'
title: CTooltipManager クラス
ms.date: 11/04/2016
f1_keywords:
- CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager
- AFXTOOLTIPMANAGER/CTooltipManager::CreateToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::DeleteToolTip
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipParams
- AFXTOOLTIPMANAGER/CTooltipManager::SetTooltipText
- AFXTOOLTIPMANAGER/CTooltipManager::UpdateTooltips
helpviewer_keywords:
- CTooltipManager [MFC], CreateToolTip
- CTooltipManager [MFC], DeleteToolTip
- CTooltipManager [MFC], SetTooltipParams
- CTooltipManager [MFC], SetTooltipText
- CTooltipManager [MFC], UpdateTooltips
ms.assetid: c71779d7-8b6e-47ef-8500-d4552731fe86
ms.openlocfilehash: 0ec6d691abbceb7026fe9656c17ff899f1d07759
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318547"
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
|[CTooltipManager::SetTooltipParams](#settooltipparams)|指定された Windows コントロールの種類のツールヒント コントロールの外観をカスタマイズします。|
|[CTooltipManager::SetTooltipText](#settooltiptext)|ツールヒント コントロールのテキストと説明を設定します。|
|[CTooltipManager::UpdateTooltips](#updatetooltips)||

## <a name="remarks"></a>解説

[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)、 `CMFCToolTipInfo` 、を一緒に使用して、カスタマイズされた `CTooltipManager` ツールヒントをアプリケーションに実装します。 これらのツールヒントクラスを使用する方法の例については、 [CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md) のトピックを参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtooltipmanager

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a> CTooltipManager:: CreateToolTip

ツールヒントコントロールを作成します。

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>パラメーター

*pToolTip*<br/>
入出力ツールヒントポインターへの参照。 関数が戻ったときに、新しく作成されたツールヒントをポイントするように設定されています。

*pWndParent*<br/>
からツールヒントの親。

*nType*<br/>
からツールヒントの種類。

### <a name="return-value"></a>戻り値

ツールヒントが正常に作成された場合は0以外の。

### <a name="remarks"></a>解説

*Ptooltip* で返されたツールヒントコントロールを削除するには、 [CTooltipManager::D eletetooltip](#deletetooltip)を呼び出す必要があります。

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)は、 *nType* によって指定されたツールヒントの種類に基づいて、作成する各ツールヒントのビジュアル表示パラメーターを設定します。 1つまたは複数のツールヒントの種類のパラメーターを変更するには、 [CTooltipManager:: SetTooltipParams](#settooltipparams)を呼び出します。

有効なツールヒントの種類を次の表に示します。

|ツールヒントの種類|コントロールカテゴリ|型の例|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|ボタン。|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|キャプションバー。|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|他のカテゴリに適合しないコントロール。|[なし] :|
|AFX_TOOLTIP_TYPE_DOCKBAR|ドッキング可能なペイン。|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|テキストボックス。|[なし] :|
|AFX_TOOLTIP_TYPE_MINIFRAME|ミニフレーム。|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|Planner。|[なし] :|
|AFX_TOOLTIP_TYPE_RIBBON|リボンバー。|CMFCRibbonBar、CMFCRibbonPanelMenuBar|
|AFX_TOOLTIP_TYPE_TAB|タブコントロール。|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|ツールバー。|CMFCToolBar、CMFCPopupMenuBar|
|AFX_TOOLTIP_TYPE_TOOLBOX|ツールボックス。|[なし] :|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a> CTooltipManager::D eleteToolTip

ツールヒント コントロールを削除します。

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>パラメーター

*pToolTip*<br/>
[入力、出力]破棄するツールヒントへのポインターへの参照。

### <a name="remarks"></a>解説

[CTooltipManager:: CreateToolTip](#createtooltip)によって作成された各[CToolTipCtrl クラス](../../mfc/reference/ctooltipctrl-class.md)に対して、このメソッドを呼び出します。 親コントロールは、そのハンドラーからこのメソッドを呼び出す必要があり `OnDestroy` ます。 これは、フレームワークからツールヒントを正しく削除するために必要です。 このメソッドは、を返す前に *Ptooltip* を NULL に設定します。

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a> CTooltipManager:: SetTooltipParams

指定された Windows コントロール型のツールヒントコントロールの外観をカスタマイズします。

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>パラメーター

*nTypes*<br/>
からコントロールの種類を指定します。

*pRTC*<br/>
からカスタムツールヒントのランタイムクラス。

*pParams*<br/>
からツールヒントパラメーター。

### <a name="remarks"></a>解説

このメソッドは、 [CToolTipManager](../../mfc/reference/ctooltipmanager-class.md) がツールヒントを作成するときに使用するランタイムクラスと初期パラメーターを設定します。 コントロールが [CTooltipManager:: CreateToolTip](#createtooltip) を呼び出し、 *ntypes* によって示される型の1つであるツールヒントの型を渡すと、ツールヒントマネージャーによって、 *prtc* によって指定されたランタイムクラスのインスタンスである tooltip コントロールが作成され、 *pparams* によって指定されたパラメーターが新しいツールヒントに渡されます。

このメソッドを呼び出すと、既存のすべてのツールヒントの所有者が AFX_WM_UPDATETOOLTIPS メッセージを受信し、 [CTooltipManager:: CreateToolTip](#createtooltip)を使用してツールヒントを再作成する必要があります。

*Ntypes* は、 [CTooltipManager:: createtooltip](#createtooltip) で使用される有効なツールヒントの種類の任意の組み合わせにすることも、AFX_TOOLTIP_TYPE_ALL することもできます。 AFX_TOOLTIP_TYPE_ALL を渡すと、すべてのツールヒントの種類が影響を受けます。

### <a name="example"></a>例

クラスのメソッドを使用する方法を次の例に示し `SetTooltipParams` `CTooltipManager` ます。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a> CTooltipManager:: SetTooltipText

ツールヒントのテキストと説明を設定します。

```
static void SetTooltipText(
    TOOLINFO* pTI,
    CToolTipCtrl* pToolTip,
    UINT nType,
    const CString strText,
    LPCTSTR lpszDescr=NULL);
```

### <a name="parameters"></a>パラメーター

*pTI*<br/>
からTOOLINFO オブジェクトへのポインター。

*pToolTip*<br/>
[入力、出力]テキストと説明を設定するツールヒントコントロールへのポインター。

*nType*<br/>
からこのツールヒントが関連付けられているコントロールの種類を指定します。

*strText*<br/>
からツールヒントのテキストとして設定するテキスト。

*lpszDescr*<br/>
からツールヒントの説明へのポインター。 NULL にすることができます。

### <a name="remarks"></a>解説

*NType* の値は、ツールヒントを作成したときに [CTooltipManager:: Createtooltip](#createtooltip)の *nType* パラメーターと同じ値である必要があります。

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a> CTooltipManager:: UpdateTooltips ヒント

詳細については、Visual Studio のインストールの **VC \\ atlmfc \\ src \\ mfc** フォルダーにあるソースコードを参照してください。

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[CMFCToolTipInfo クラス](../../mfc/reference/cmfctooltipinfo-class.md)
