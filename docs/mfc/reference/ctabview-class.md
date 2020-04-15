---
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
ms.openlocfilehash: ad30cbbf5de195708d2d357a76c38b661d095c2f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365924"
---
# <a name="ctabview-class"></a>CTabView クラス

この`CTabView`クラスは、MFC のドキュメント/ビュー アーキテクチャを使用するアプリケーションでタブ コントロール クラス ( [CMFCTabCtrl](../../mfc/reference/ctabview-class.md)) の使用を簡略化します。

## <a name="syntax"></a>構文

```
class CTabbedView : public CView
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ビューを追加します。](#addview)|タブ コントロールに新しいビューを追加します。|
|[タブビュー::検索タブ](#findtab)|タブ コントロール内の指定されたビューのインデックスを返します。|
|[を表示します。](#getactiveview)|現在アクティブなビューへのポインターを返します。|
|[タブビュー::タブコントロールを取得します。](#gettabcontrol)|ビューに関連付けられているタブ コントロールへの参照を返します。|
|[ビューを削除します。](#removeview)|タブ コントロールからビューを削除します。|
|[表示::アクティブビュー](#setactiveview)|ビューをアクティブにします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[タブビュー::イズスクロールバー](#isscrollbar)|タブ ビューの作成時にフレームワークによって呼び出され、タブ ビューに共有の水平スクロール バーがあるかどうかを判断します。|
|[表示::アクティブ化ビュー](#onactivateview)|タブ ビューがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。|

## <a name="remarks"></a>解説

このクラスを使用すると、タブ付きビューをドキュメント/ビュー アプリケーションに簡単に配置できます。 `CTabView`は、`CView`埋め込み`CMFCTabCtrl`オブジェクトを含む派生クラスです。 `CTabView`オブジェクトをサポートするために必要なすべてのメッセージ`CMFCTabCtrl`を処理します。 クラスを派生`CTabView`させ、アプリケーションにプラグインしてから、メソッドを使用して`CView`派生クラスを`AddView`追加するだけです。 タブ コントロールは、これらのビューをタブとして表示します。

たとえば、スプレッドシート、グラフ、編集可能なフォームなど、さまざまな方法で表現できるドキュメントを作成できます。 必要に応じてデータを描画する個々のビューを作成し、`CTabView`それらを派生オブジェクトに挿入して、追加のコーディングを行わずにタブ付けすることができます。

[タブベッド ビュー サンプル: MFC タブ付きビュー アプリケーション](../../overview/visual-cpp-samples.md)は、 の`CTabView`使用方法を示しています。

## <a name="example"></a>例

次の例は、TabbedView サンプルでの使用方法`CTabView`を示しています。

[!code-cpp[NVC_MFC_TabbedView#1](../../mfc/reference/codesnippet/cpp/ctabview-class_1.h)]

## <a name="requirements"></a>必要条件

**ヘッダー:** afxTabView.h

## <a name="ctabviewaddview"></a><a name="addview"></a>ビューを追加します。

タブ コントロールにビューを追加します。

```
int AddView(
    CRuntimeClass* pViewClass,
    const CString& strViewLabel,
    int iIndex=-1,
    CCreateContext* pContext=NULL);
```

### <a name="parameters"></a>パラメーター

*クラスを表示します。*<br/>
[in]挿入されたビューのランタイム クラスへのポインター。

*ラベル*<br/>
[in]タブのテキストを指定します。

*をクリックします。*<br/>
[in]ビューを挿入する位置を 0 から始まる位置に指定します。 位置が -1 の場合、新しいタブは末尾に挿入されます。

*pContext*<br/>
[in]ビューの への`CCreateContext`ポインター。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合は、ビューインデックス。 それ以外の場合は、-1。

### <a name="remarks"></a>解説

フレームに埋め込まれているタブ コントロールにビューを追加します。

## <a name="ctabviewfindtab"></a><a name="findtab"></a>タブビュー::検索タブ

タブ コントロール内の指定されたビューのインデックスを返します。

```
int FindTab(HWND hWndView) const;
```

### <a name="parameters"></a>パラメーター

*フーンドビュー*<br/>
[in]ビューのハンドル。

### <a name="return-value"></a>戻り値

ビューが見つかった場合は、ビューのインデックス。それ以外の場合は -1。

### <a name="remarks"></a>解説

指定したハンドルを持つビューのインデックスを取得します。

## <a name="ctabviewgetactiveview"></a><a name="getactiveview"></a>を表示します。

現在アクティブなビューへのポインターを返します。

```
CView* GetActiveView() const;
```

### <a name="return-value"></a>戻り値

アクティブ なビューへの有効なポインター。

### <a name="remarks"></a>解説

## <a name="ctabviewgettabcontrol"></a><a name="gettabcontrol"></a>タブビュー::タブコントロールを取得します。

ビューに関連付けられているタブ コントロールへの参照を返します。

```
DECLARE_DYNCREATE CMFCTabCtrl& GetTabControl();
```

### <a name="return-value"></a>戻り値

ビューに関連付けられているタブ コントロールへの参照。

## <a name="ctabviewisscrollbar"></a><a name="isscrollbar"></a>タブビュー::イズスクロールバー

タブ ビューの作成時にフレームワークによって呼び出され、タブ ビューに共有の水平スクロール バーがあるかどうかを判断します。

```
virtual BOOL IsScrollBar() const;
```

### <a name="return-value"></a>戻り値

タブ ビューを共有スクロール バーと共に作成する場合は TRUE。 それ以外の場合は FALSE。

### <a name="remarks"></a>解説

*CTabView*オブジェクトが作成されているときに、フレームワークは、このメソッドを呼び出します。

*CTabView*派生クラスで*IsScrollBar*メソッドをオーバーライドし、水平スクロール バーを共有するビューを作成する場合は TRUE を返します。

## <a name="ctabviewonactivateview"></a><a name="onactivateview"></a>表示::アクティブ化ビュー

タブ ビューがアクティブまたは非アクティブになったときに、フレームワークによって呼び出されます。

```
virtual void OnActivateView(CView* view);
```

### <a name="parameters"></a>パラメーター

*ビュー*<br/>
[in]ビューへのポインター。

### <a name="remarks"></a>解説

既定の実装では、何も行われません。 この通知を処理するには`CTabView`、-derived クラスでこのメソッドをオーバーライドします。

## <a name="ctabviewremoveview"></a><a name="removeview"></a>ビューを削除します。

タブ コントロールからビューを削除します。

```
BOOL RemoveView(int iTabNum);
```

### <a name="parameters"></a>パラメーター

*アイタブバーナム*<br/>
[in]削除するビューのインデックス。

### <a name="return-value"></a>戻り値

このメソッドが成功した場合、削除されたビューのインデックス。 それ以外の場合は -1。

### <a name="remarks"></a>解説

## <a name="ctabviewsetactiveview"></a><a name="setactiveview"></a>表示::アクティブビュー

ビューをアクティブにします。

```
BOOL SetActiveView(int iTabNum);
```

### <a name="parameters"></a>パラメーター

*アイタブバーナム*<br/>
[in]タブ ビューの 0 から始まるインデックス。

### <a name="return-value"></a>戻り値

指定したビューがアクティブにされた場合は TRUE、ビューのインデックスが無効な場合は FALSE。

### <a name="remarks"></a>解説

詳細については[、「CMFC タブCtrl::セットアクティブタブ」を参照してください](../../mfc/reference/cmfctabctrl-class.md#setactivetab)。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTabCtrl](../../mfc/reference/ctabview-class.md)<br/>
[Cビュークラス](../../mfc/reference/cview-class.md)
