---
description: '詳細情報: CTabView クラス'
title: CTabView クラス
ms.date: 11/04/2016
f1_keywords:
- CTabView
- AFXTABVIEW/CTabView
- AFXTABVIEW/CTabView::AddView
- AFXTABVIEW/CTabView::FindTab
- AFXTABVIEW/CTabView::GetActiveView
- AFXTABVIEW/CTabView::GetTabControl
- AFXTABVIEW/CTabView::RemoveView
- AFXTABVIEW/CTabView::SetActiveView
- AFXTABVIEW/CTabView::IsScrollBar
- AFXTABVIEW/CTabView::OnActivateView
helpviewer_keywords:
- CTabView [MFC], AddView
- CTabView [MFC], FindTab
- CTabView [MFC], GetActiveView
- CTabView [MFC], GetTabControl
- CTabView [MFC], RemoveView
- CTabView [MFC], SetActiveView
- CTabView [MFC], IsScrollBar
- CTabView [MFC], OnActivateView
ms.assetid: 8e6ecd9d-d28d-432b-8ec8-0446f0204d52
ms.openlocfilehash: 59d4169bae108575fcf4844ec7c5c6e1e6681e28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345057"
---
# <a name="ctabview-class"></a>CTabView クラス

クラスは、 `CTabView` MFC のドキュメント/ビューアーキテクチャを使用するアプリケーションで、タブコントロールクラス ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) の使用を簡略化します。

## <a name="syntax"></a>構文

```
class CTabbedView : public CView
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CTabView:: AddView](#addview)|新しいビューをタブコントロールに追加します。|
|[CTabView:: FindTab](#findtab)|タブコントロール内の指定されたビューのインデックスを返します。|
|[CTabView:: GetActiveView](#getactiveview)|現在アクティブなビューへのポインターを返します。|
|[CTabView:: GetTabControl](#gettabcontrol)|ビューに関連付けられているタブコントロールへの参照を返します。|
|[CTabView:: RemoveView](#removeview)|タブコントロールからビューを削除します。|
|[CTabView:: SetActiveView](#setactiveview)|ビューをアクティブにします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CTabView:: IsScrollBar](#isscrollbar)|タブビューを作成して、共有されている水平スクロールバーがあるかどうかを判断するときに、フレームワークによって呼び出されます。|
|[CTabView:: Onアクティブビュー](#onactivateview)|タブビューがアクティブまたは非アクティブになったときにフレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

このクラスを使用すると、ドキュメント/ビューアプリケーションにタブ付きビューを簡単に配置できます。 `CTabView` は、 `CView` 埋め込みオブジェクトを含むの派生クラスです `CMFCTabCtrl` 。 `CTabView` オブジェクトをサポートするために必要なすべてのメッセージ `CMFCTabCtrl` を処理します。 からクラスを派生させ、 `CTabView` アプリケーションに接続してから、 `CView` メソッドを使用して派生クラスを追加し `AddView` ます。 タブコントロールには、それらのビューがタブとして表示されます。

たとえば、スプレッドシート、グラフ、編集可能なフォームなど、さまざまな方法で表現できるドキュメントがあるとします。 必要に応じてデータを描画する個々のビューを作成し、 `CTabView` 派生したオブジェクトに挿入して、追加のコーディングなしでそれらをタブにすることができます。

[TabbedView サンプル: MFC タブ付きビューアプリケーション](../../overview/visual-cpp-samples.md) の使用方法を示し `CTabView` ます。

## <a name="example"></a>例

次の例は `CTabView` 、を TabbedView サンプルで使用する方法を示しています。

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>要件

**ヘッダー:** afxTabView

## <a name="ctabviewaddview"></a><a name="addview"></a> CTabView:: AddView

タブコントロールにビューを追加します。

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>パラメーター

*pViewClass*<br/>
から挿入されたビューのランタイムクラスへのポインター。

*strViewLabel*<br/>
からタブのテキストを指定します。

*iIndex*<br/>
からビューを挿入する位置の、0から始まる位置を指定します。 位置が-1 の場合、新しいタブは最後に挿入されます。

*pContext*<br/>
からビューのへのポインター `CCreateContext` 。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合のビューインデックス。 それ以外の場合は、-1。

### <a name="remarks"></a>解説

フレームに埋め込まれているタブコントロールにビューを追加するには、この関数を呼び出します。

## <a name="ctabviewfindtab"></a><a name="findtab"></a> CTabView:: FindTab

タブコントロール内の指定されたビューのインデックスを返します。

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>パラメーター

*hWndView*<br/>
からビューのハンドル。

### <a name="return-value"></a>戻り値

見つかった場合はビューのインデックス。それ以外の場合は-1。

### <a name="remarks"></a>解説

この関数を呼び出して、指定したハンドルを持つビューのインデックスを取得します。

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a> CTabView:: GetActiveView

現在アクティブなビューへのポインターを返します。

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>戻り値

アクティブなビューへの有効なポインター。アクティブなビューがない場合は NULL。

### <a name="remarks"></a>解説

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a> CTabView:: GetTabControl

ビューに関連付けられているタブコントロールへの参照を返します。

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>戻り値

ビューに関連付けられているタブコントロールへの参照。

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a> CTabView:: IsScrollBar

タブビューを作成して、共有されている水平スクロールバーがあるかどうかを判断するときに、フレームワークによって呼び出されます。

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>戻り値

タブビューを共有スクロールバーと一緒に作成する必要がある場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、 *Ctabview* オブジェクトの作成時にフレームワークによって呼び出されます。

*Ctabview* の派生クラスで *isscrollbar* メソッドをオーバーライドし、共有水平スクロールバーを持つビューを作成する場合は TRUE を返します。

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a> CTabView:: Onアクティブビュー

タブビューがアクティブまたは非アクティブになったときにフレームワークによって呼び出されます。

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>パラメーター

*view*<br/>
からビューへのポインター。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。 `CTabView`この通知を処理するには、派生クラスでこのメソッドをオーバーライドします。

## <a name="ctabviewremoveview"></a><a name="removeview"></a> CTabView:: RemoveView

タブコントロールからビューを削除します。

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>パラメーター

*iTabNum*<br/>
から削除するビューのインデックス。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合の、削除されたビューのインデックス。 それ以外の場合は-1。

### <a name="remarks"></a>解説

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a> CTabView:: SetActiveView

ビューをアクティブにします。

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>パラメーター

*iTabNum*<br/>
からタブビューの0から始まるインデックス。

### <a name="return-value"></a>戻り値

指定されたビューがアクティブになっている場合は TRUE、ビューのインデックスが無効な場合は FALSE。

### <a name="remarks"></a>解説

詳細については、「 [CMFCTabCtrl:: SetActiveTab](../../mfc/reference/cmfctabctrl-class.md#setactivetab)」を参照してください。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[CView クラス](../../mfc/reference/cview-class.md)
