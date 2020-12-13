---
description: '詳細情報: CMouseManager クラス'
title: CMouseManager クラス
ms.date: 11/04/2016
f1_keywords:
- CMouseManager
- AFXMOUSEMANAGER/CMouseManager
- AFXMOUSEMANAGER/CMouseManager::AddView
- AFXMOUSEMANAGER/CMouseManager::GetViewDblClickCommand
- AFXMOUSEMANAGER/CMouseManager::GetViewIconId
- AFXMOUSEMANAGER/CMouseManager::GetViewIdByName
- AFXMOUSEMANAGER/CMouseManager::GetViewNames
- AFXMOUSEMANAGER/CMouseManager::LoadState
- AFXMOUSEMANAGER/CMouseManager::SaveState
- AFXMOUSEMANAGER/CMouseManager::SetCommandForDblClk
helpviewer_keywords:
- CMouseManager [MFC], AddView
- CMouseManager [MFC], GetViewDblClickCommand
- CMouseManager [MFC], GetViewIconId
- CMouseManager [MFC], GetViewIdByName
- CMouseManager [MFC], GetViewNames
- CMouseManager [MFC], LoadState
- CMouseManager [MFC], SaveState
- CMouseManager [MFC], SetCommandForDblClk
ms.assetid: a4d05017-4e44-4a40-8b57-4ece0de20481
ms.openlocfilehash: 9816583aa9d05b76f97f1be1487898b5827fbcae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331558"
---
# <a name="cmousemanager-class"></a>CMouseManager クラス

ユーザーがビュー内でダブルクリックしたときに、さまざまなコマンドを特定の [CView](../../mfc/reference/cview-class.md) オブジェクトに関連付けることができるようにします。

## <a name="syntax"></a>構文

```
class CMouseManager : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMouseManager:: AddView](#addview)|オブジェクトを `CView` **カスタマイズ** ダイアログボックスに追加します。 ユーザーは、[ **カスタマイズ** ] ダイアログボックスを使用して、ダブルクリックを、一覧表示されている各ビューのコマンドと関連付けることができます。|
|[CMouseManager:: GetViewDblClickCommand](#getviewdblclickcommand)|指定されたビュー内でユーザーがダブルクリックしたときに実行されるコマンドを返します。|
|[CMouseManager:: GetViewIconId](#getviewiconid)|指定されたビュー ID に関連付けられたアイコンを返します。|
|[CMouseManager:: GetViewIdByName](#getviewidbyname)|指定されたビュー名に関連付けられているビュー ID を返します。|
|[CMouseManager:: GetViewNames](#getviewnames)|追加されたすべてのビュー名のリストを取得します。|
|[CMouseManager:: LoadState](#loadstate)|`CMouseManager`Windows レジストリから状態を読み込みます。|
|[CMouseManager:: SaveState](#savestate)|`CMouseManager`Windows レジストリに状態を書き込みます。|
|[CMouseManager:: SetCommandForDblClk](#setcommandfordblclk)|指定されたコマンドと指定されたビューを関連付けます。|

## <a name="remarks"></a>解説

クラスは、 `CMouseManager` オブジェクトのコレクションを保持し `CView` ます。 各ビューは、名前と ID によって識別されます。 これらのビューは、[ **カスタマイズ** ] ダイアログボックスに表示されます。 ユーザーは、[ **カスタマイズ** ] ダイアログボックスを使用して、任意のビューに関連付けられているコマンドを変更できます。 関連付けられているコマンドは、ユーザーがそのビューでダブルクリックしたときに実行されます。 コーディングの観点からこれをサポートするには、WM_LBUTTONDBLCLK メッセージを処理し、そのオブジェクトのコードで [CWinAppEx:: OnViewDoubleClick](../../mfc/reference/cwinappex-class.md#onviewdoubleclick) 関数を呼び出す必要があります。「」を確認して `CView` ください。

オブジェクトを手動で作成しないでください `CMouseManager` 。 アプリケーションのフレームワークによって作成されます。 また、ユーザーがアプリケーションを終了すると自動的に破棄されます。 アプリケーションのマウスマネージャーへのポインターを取得するには、 [CWinAppEx:: GetMouseManager](../../mfc/reference/cwinappex-class.md#getmousemanager)を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CMouseManager`

## <a name="requirements"></a>要件

**ヘッダー:** afxmousemanager

## <a name="cmousemanageraddview"></a><a name="addview"></a> CMouseManager:: AddView

カスタムのマウス動作をサポートするために、 [CView](../../mfc/reference/cview-class.md) オブジェクトを [Cmousemanager クラス](../../mfc/reference/cmousemanager-class.md) に登録します。

```
BOOL AddView(
    int iViewId,
    UINT uiViewNameResId,
    UINT uiIconId = 0);

BOOL AddView(
    int iId,
    LPCTSTR lpszViewName,
    UINT uiIconId = 0);
```

### <a name="parameters"></a>パラメーター

*iViewId*<br/>
からビュー ID。

*uiViewNameResId*<br/>
からビュー名を参照するリソース文字列 ID。

*uiIconId*<br/>
からビューアイコン ID。

*iId*<br/>
からビュー ID。

*lpszViewName*<br/>
からビュー名。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

マウスのカスタム動作をサポートするには、オブジェクトにビューを登録する必要があり `CMouseManager` ます。 クラスから派生したオブジェクトは、 `CView` マウスマネージャーで登録できます。 ビューに関連付けられている文字列とアイコンは、[**ユーザー設定**] ダイアログボックスの [**マウス**] タブに表示されます。

*IViewId* や *iId* などのビュー id を作成して管理するのはプログラマの役割です。

マウスのカスタム動作を指定する方法の詳細については、「 [キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)」を参照してください。

### <a name="example"></a>例

次の例では、 `CMouseManager` クラスのメソッドとメソッドを使用して、オブジェクトへのポインターを取得する方法を示し `CWinAppEx::GetMouseManager` `AddView` `CMouseManager` ます。 このコードスニペットは、 [状態コレクションサンプル](../../overview/visual-cpp-samples.md)の一部です。

[!code-cpp[NVC_MFC_StateCollection#4](../../mfc/reference/codesnippet/cpp/cmousemanager-class_1.cpp)]

## <a name="cmousemanagergetviewdblclickcommand"></a><a name="getviewdblclickcommand"></a> CMouseManager:: GetViewDblClickCommand

指定されたビュー内でユーザーがダブルクリックしたときに実行されるコマンドを返します。

```
UINT GetViewDblClickCommand(int iId) const;
```

### <a name="parameters"></a>パラメーター

*iId*<br/>
からビュー ID。

### <a name="return-value"></a>戻り値

ビューがコマンドに関連付けられている場合は、コマンド識別子。それ以外の場合は0です。

## <a name="cmousemanagergetviewiconid"></a><a name="getviewiconid"></a> CMouseManager:: GetViewIconId

ビュー ID に関連付けられたアイコンを取得します。

```
UINT GetViewIconId(int iViewId) const;
```

### <a name="parameters"></a>パラメーター

*iViewId*<br/>
からビュー ID。

### <a name="return-value"></a>戻り値

成功した場合はアイコンリソース識別子。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメソッドは、 [Cmousemanager:: AddView](#addview)を使用して最初にビューが登録されていない場合に失敗します。

## <a name="cmousemanagergetviewidbyname"></a><a name="getviewidbyname"></a> CMouseManager:: GetViewIdByName

ビュー名に関連付けられているビュー ID を取得します。

```
int GetViewIdByName(LPCTSTR lpszName) const;
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
からビュー名。

### <a name="return-value"></a>戻り値

成功した場合はビュー ID。それ以外の場合は0です。

### <a name="remarks"></a>解説

このメソッド [は、Cmousemanager:: AddView](#addview)を使用して登録されたビューを検索します。

## <a name="cmousemanagergetviewnames"></a><a name="getviewnames"></a> CMouseManager:: GetViewNames

登録されているすべてのビュー名のリストを取得します。

```cpp
void GetViewNames(CStringList& listOfNames) const;
```

### <a name="parameters"></a>パラメーター

*listOfNames*<br/>
入出力オブジェクトへの参照 `CStringList` 。

### <a name="remarks"></a>解説

このメソッドは、 `listOfNames` [Cmousemanager:: addview](#addview)を使用して登録されたすべてのビューの名前をパラメーターに入力します。

## <a name="cmousemanagerloadstate"></a><a name="loadstate"></a> CMouseManager:: LoadState

レジストリから [Cmousemanager クラス](../../mfc/reference/cmousemanager-class.md) の状態を読み込みます。

```
BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からレジストリキーのパス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

レジストリから読み込まれた状態情報には、登録済みビュー、ビュー識別子、および関連付けられたコマンドが含まれます。 パラメーター *Lpszprofilename* が NULL の場合、この関数は、 `CMouseManager` [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)によって制御される既定のレジストリの場所からデータを読み込みます。

ほとんどの場合、この関数を直接呼び出す必要はありません。 これは、ワークスペースの初期化プロセスの一部として呼び出されます。 ワークスペースの初期化プロセスの詳細については、「 [CWinAppEx:: LoadState](../../mfc/reference/cwinappex-class.md#loadstate)」を参照してください。

## <a name="cmousemanagersavestate"></a><a name="savestate"></a> CMouseManager:: SaveState

[Cmousemanager クラス](../../mfc/reference/cmousemanager-class.md)の状態をレジストリに書き込みます。

```
BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```

### <a name="parameters"></a>パラメーター

*lpszProfileName*<br/>
からレジストリキーのパス。

### <a name="return-value"></a>戻り値

正常終了した場合は 0 以外を返します。それ以外の場合は 0 を返します。

### <a name="remarks"></a>解説

レジストリに書き込まれた状態情報には、登録済みのすべてのビュー、ビュー識別子、および関連付けられたコマンドが含まれます。 パラメーター *Lpszprofilename* が NULL の場合、この関数は、 `CMouseManager` [CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)によって制御される既定のレジストリの場所にデータを書き込みます。

ほとんどの場合、この関数を直接呼び出す必要はありません。 これは、ワークスペースのシリアル化プロセスの一部として呼び出されます。 ワークスペースのシリアル化プロセスの詳細については、「 [CWinAppEx:: SaveState](../../mfc/reference/cwinappex-class.md#savestate)」を参照してください。

## <a name="cmousemanagersetcommandfordblclk"></a><a name="setcommandfordblclk"></a> CMouseManager:: SetCommandForDblClk

カスタムコマンドを、最初にマウスマネージャーに登録されたビューに関連付けます。

```cpp
void SetCommandForDblClk(
    int iViewId,
    UINT uiCmd);
```

### <a name="parameters"></a>パラメーター

*iViewId*<br/>
からビュー識別子。

*uiCmd*<br/>
からコマンド識別子。

### <a name="remarks"></a>解説

カスタムコマンドをビューに関連付けるには、まず [Cmousemanager:: AddView](#addview)を使用してビューを登録する必要があります。 メソッドでは、 `AddView` 入力パラメーターとしてビュー識別子が必要です。 ビューを登録すると、に指定したのと `CMouseManager::SetCommandForDblClk` 同じビュー識別子入力パラメーターを使用してを呼び出すことができ `AddView` ます。 その後、ユーザーが登録されたビューでマウスをダブルクリックすると、アプリケーションは UiCmd によって示されるコマンドを実行し *ます。* マウスのカスタム動作をサポートするには、マウスマネージャーに登録されているビューをカスタマイズする必要もあります。 マウスのカスタム動作の詳細については、「 [キーボードおよびマウスのカスタマイズ](../keyboard-and-mouse-customization.md)」を参照してください。

*UiCmd* が0に設定されている場合は、指定したビューがコマンドに関連付けられなくなります。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CWinAppEx クラス](../../mfc/reference/cwinappex-class.md)<br/>
[キーボードとマウスのカスタマイズ](../../mfc/keyboard-and-mouse-customization.md)
