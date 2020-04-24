---
title: クラス
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
ms.openlocfilehash: 4e721740fc100a34ea08dd7ff5f9291eea2d9b36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752172"
---
# <a name="ctooltipmanager-class"></a>クラス

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

[CMFCToolTipCtrl クラス](../../mfc/reference/cmfctooltipctrl-class.md) `CMFCToolTipInfo`、および`CTooltipManager`を一緒に使用して、アプリケーションでカスタマイズされたツールヒントを実装します。 これらのツールヒント クラスの使用例については、「[クラスの CMFCToolTipCtrl」](../../mfc/reference/cmfctooltipctrl-class.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxツールチップマネージャー.h

## <a name="ctooltipmanagercreatetooltip"></a><a name="createtooltip"></a>ツールヒントを作成します。

ツールヒント コントロールを作成します。

```
static BOOL CreateToolTip(
    CToolTipCtrl*& pToolTip,
    CWnd* pWndParent,
    UINT nType);
```

### <a name="parameters"></a>パラメーター

*ツールチップ*<br/>
[アウト]ツールヒント ポインターへの参照。 関数が返されるときに、新しく作成されたツールヒントを指す設定です。

*親の子*<br/>
[in]ツールヒントの親です。

*nType*<br/>
[in]ツールヒントのタイプ。

### <a name="return-value"></a>戻り値

ツールヒントが正常に作成された場合は、0 以外の値を返します。

### <a name="remarks"></a>解説

*pToolTip*で渡されるツールヒント コントロールを削除するには[、CTooltipManager::Dツール ヒント](#deletetooltip)を呼び出す必要があります。

[CTooltipManager](../../mfc/reference/ctooltipmanager-class.md)は *、nType*が指定したツールヒントの種類に基づいて、作成する各ツールヒントのビジュアル表示パラメーターを設定します。 1 つ以上のツールヒントの種類のパラメーターを変更するには[、CTooltipManager::設定ツールヒントパラム](#settooltipparams)を呼び出します。

有効なツールヒントの種類を次の表に示します。

|ツールヒントの種類|コントロールカテゴリ|タイプの例|
|------------------|----------------------|-------------------|
|AFX_TOOLTIP_TYPE_BUTTON|ボタン。|CMFCButton|
|AFX_TOOLTIP_TYPE_CAPTIONBAR|キャプション バー。|CMFCCaptionBar|
|AFX_TOOLTIP_TYPE_DEFAULT|他のカテゴリに適合しないコントロール。|[なし] :|
|AFX_TOOLTIP_TYPE_DOCKBAR|ドッキング可能なペイン。|CDockablePane|
|AFX_TOOLTIP_TYPE_EDIT|テキスト ボックス。|[なし] :|
|AFX_TOOLTIP_TYPE_MINIFRAME|ミニフレーム。|CPaneFrameWnd|
|AFX_TOOLTIP_TYPE_PLANNER|プランナー。|[なし] :|
|AFX_TOOLTIP_TYPE_RIBBON|リボン バー。|メニュー バー|
|AFX_TOOLTIP_TYPE_TAB|タブ コントロール。|CMFCTabCtrl|
|AFX_TOOLTIP_TYPE_TOOLBAR|ツールバー。|メニューバー|
|AFX_TOOLTIP_TYPE_TOOLBOX|ツールボックス。|[なし] :|

## <a name="ctooltipmanagerdeletetooltip"></a><a name="deletetooltip"></a>ツールヒント:D

ツールヒント コントロールを削除します。

```
static void DeleteToolTip(CToolTipCtrl*& pToolTip);
```

### <a name="parameters"></a>パラメーター

*ツールチップ*<br/>
[イン、アウト]破棄されるツールヒントへのポインターへの参照。

### <a name="remarks"></a>解説

このメソッドは、C ツール ヒント マネージャーによって作成された各[CToolTipCtrl クラス](../../mfc/reference/ctooltipctrl-class.md)に対して呼び出[します](#createtooltip)。 親コントロールは、ハンドラーからこのメソッドを`OnDestroy`呼び出す必要があります。 これは、フレームワークからツールヒントを正しく削除するために必要です。 このメソッドは *、pToolTip*が返される前に null に設定します。

## <a name="ctooltipmanagersettooltipparams"></a><a name="settooltipparams"></a>ツールチップマネージャー::ツールチップパラムの設定

指定した Windows コントロールの種類に対するツールヒント コントロールの外観をカスタマイズします。

```cpp
void SetTooltipParams(
    UINT nTypes,
    CRuntimeClass* pRTC=RUNTIME_CLASS(CMFCToolTipCtrl),
    CMFCToolTipInfo* pParams=NULL);
```

### <a name="parameters"></a>パラメーター

*nタイプ*<br/>
[in]コントロールの種類を指定します。

*pRTC*<br/>
[in]カスタム ツールヒントのランタイム クラス。

*pParams*<br/>
[in]ツールヒント のパラメーター。

### <a name="remarks"></a>解説

このメソッドは、ツールヒントを作成するときに[CToolTipManager](../../mfc/reference/ctooltipmanager-class.md)が使用するランタイム クラスと初期パラメーターを設定します。 コントロールが[CTooltipManager::CreateToolTip](#createtooltip)を呼び出し *、nTypes*で示される型の 1 つであるツールヒントの種類を渡すと、ツールヒント マネージャーは *、pRTC*で指定されたランタイム クラスのインスタンスであるツールヒント コントロールを作成し *、pParams*で指定されたパラメーターを新しいツールヒントに渡します。

このメソッドを呼び出すと、既存のすべてのツールヒントの所有者は、AFX_WM_UPDATETOOLTIPSメッセージを受信し[、CTooltipManager::CreateToolTip](#createtooltip)を使用してツールヒントを再作成する必要があります。

*nTypes*は[、CTooltipManager::CreateToolTip](#createtooltip)が使用する有効なツールヒントの種類を任意に組み合わせて使用することも、AFX_TOOLTIP_TYPE_ALLすることもできます。 AFX_TOOLTIP_TYPE_ALL渡すと、すべてのツールヒントタイプが影響を受けます。

### <a name="example"></a>例

クラスのメソッドの使用方法を`SetTooltipParams`次の例に示します`CTooltipManager`。 このコード スニペットは、「 [クライアント サンプルの描画](../../overview/visual-cpp-samples.md)」の一部です。

[!code-cpp[NVC_MFC_DrawClient#11](../../mfc/reference/codesnippet/cpp/ctooltipmanager-class_1.cpp)]

## <a name="ctooltipmanagersettooltiptext"></a><a name="settooltiptext"></a>ツールヒントマネージャー::ツールヒントテキストを設定します。

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

*Pti*<br/>
[in]TOOLINFO オブジェクトへのポインター。

*ツールチップ*<br/>
[イン、アウト]テキストと説明を設定するツールヒント コントロールへのポインター。

*nType*<br/>
[in]このツールヒントが関連付けられているコントロールの種類を指定します。

*str テキスト*<br/>
[in]ツールヒントのテキストとして設定するテキスト。

*lpszDescr*<br/>
[in]ツールヒントの説明へのポインター。 NULL にすることができます。

### <a name="remarks"></a>解説

*nType*の値は、ツールヒントを作成したときに[、CTooltipManager::CreateToolTip](#createtooltip)の*nType*パラメーターと同じ値である必要があります。

## <a name="ctooltipmanagerupdatetooltips"></a><a name="updatetooltips"></a>ツールチップマネージャー::ツールチップの更新

詳細については、Visual Studio のインストールの**\\VC\\atlmfc\\src mfc**フォルダーにあるソース コードを参照してください。

```cpp
void UpdateTooltips();
```

### <a name="remarks"></a>解説

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctooltipctrl-class.md)<br/>
[クラス](../../mfc/reference/cmfctooltipinfo-class.md)
