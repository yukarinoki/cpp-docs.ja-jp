---
description: '詳細情報: CMFCTasksPaneTask クラス'
title: CMFCTasksPaneTask クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::CMFCTasksPaneTask
- AFXTASKSPANE/CMFCTasksPaneTask::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTask::m_bAutoDestroyWindow
- AFXTASKSPANE/CMFCTasksPaneTask::m_bIsBold
- AFXTASKSPANE/CMFCTasksPaneTask::m_dwUserData
- AFXTASKSPANE/CMFCTasksPaneTask::m_hwndTask
- AFXTASKSPANE/CMFCTasksPaneTask::m_nIcon
- AFXTASKSPANE/CMFCTasksPaneTask::m_nWindowHeight
- AFXTASKSPANE/CMFCTasksPaneTask::m_pGroup
- AFXTASKSPANE/CMFCTasksPaneTask::m_rect
- AFXTASKSPANE/CMFCTasksPaneTask::m_strName
- AFXTASKSPANE/CMFCTasksPaneTask::m_uiCommandID
helpviewer_keywords:
- CMFCTasksPaneTask [MFC], CMFCTasksPaneTask
- CMFCTasksPaneTask [MFC], SetACCData
- CMFCTasksPaneTask [MFC], m_bAutoDestroyWindow
- CMFCTasksPaneTask [MFC], m_bIsBold
- CMFCTasksPaneTask [MFC], m_dwUserData
- CMFCTasksPaneTask [MFC], m_hwndTask
- CMFCTasksPaneTask [MFC], m_nIcon
- CMFCTasksPaneTask [MFC], m_nWindowHeight
- CMFCTasksPaneTask [MFC], m_pGroup
- CMFCTasksPaneTask [MFC], m_rect
- CMFCTasksPaneTask [MFC], m_strName
- CMFCTasksPaneTask [MFC], m_uiCommandID
ms.assetid: c5a7513b-cd8f-4e2e-b16f-650e1fe30954
ms.openlocfilehash: 8dad8520c938cae655143464189897d216a5f3ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306769"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask クラス

クラスは、 `CMFCTasksPaneTask` 作業ウィンドウコントロール ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)) のタスクを表すヘルパークラスです。 タスクオブジェクトは、タスクグループ ( [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)) 内の項目を表します。 各タスクには、ユーザーがタスク名の左側に表示されるタスクやアイコンをクリックしたときにフレームワークが実行するコマンドを設定できます。

## <a name="syntax"></a>構文

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCTasksPaneTask:: CMFCTasksPaneTask](#cmfctaskspanetask)|`CMFCTasksPaneTask` オブジェクトを構築して、初期化します。|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCTasksPaneTask:: Setのデータ](#setaccdata)|現在のタスクのユーザー補助データを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCTasksPaneTask:: m_bAutoDestroyWindow](#m_bautodestroywindow)|タスクウィンドウを自動的に破棄するかどうかを決定します。|
|[CMFCTasksPaneTask:: m_bIsBold](#m_bisbold)|フレームワークがタスクラベルを太字で描画するかどうかを決定します。|
|[CMFCTasksPaneTask:: m_dwUserData](#m_dwuserdata)|フレームワークによってタスクに関連付けられるユーザー定義データを格納します。 タスクに関連付けられたデータがない場合は、0に設定します。|
|[CMFCTasksPaneTask:: m_hwndTask](#m_hwndtask)|タスクウィンドウへのハンドル。|
|[CMFCTasksPaneTask:: m_nIcon](#m_nicon)|フレームワークによってタスクの横に表示されるイメージのイメージリスト内のインデックス。|
|[CMFCTasksPaneTask:: m_nWindowHeight](#m_nwindowheight)|タスクウィンドウの高さ。 タスクウィンドウがない場合、この値は0です。|
|[CMFCTasksPaneTask:: m_pGroup](#m_pgroup)|`CMFCTasksPaneTaskGroup`このタスクが属するへのポインター。|
|[CMFCTasksPaneTask:: m_rect](#m_rect)|タスクの外接する四角形を指定します。|
|[CMFCTasksPaneTask:: m_strName](#m_strname)|タスクの名前です。|
|[CMFCTasksPaneTask:: m_uiCommandID](#m_uicommandid)|ユーザーがタスクをクリックしたときにフレームワークが実行するコマンドのコマンド ID を指定します。 この値が有効なコマンド ID でない場合、タスクは単純なラベルとして扱われます。|

## <a name="remarks"></a>解説

次の図は、3つのタスクを含むタスクグループを示しています。

![タスクグループ、展開](../../mfc/reference/media/nexttaskgrpexpand.png "展開されたタスク グループ")

> [!NOTE]
> タスクに有効なコマンド ID がない場合は、単純なラベルとして扱われます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtaskspane.h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a> CMFCTasksPaneTask:: CMFCTasksPaneTask

`CMFCTasksPaneTask` オブジェクトを構築して、初期化します。

```
CMFCTasksPaneTask(
    CMFCTasksPaneTaskGroup* pGroup,
    LPCTSTR lpszName,
    int nIcon,
    UINT uiCommandID,
    DWORD dwUserData = 0,
    HWND hwndTask = NULL,
    BOOL bAutoDestroyWindow = FALSE,
    int nWindowHeight = 0);
```

### <a name="parameters"></a>パラメーター

*pGroup*<br/>
タスクが所属する [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) を指定します。

*lpszName*<br/>
タスクの名前を指定します。

*nIcon*<br/>
イメージリスト内のタスクのイメージのインデックスを指定します。

*uiCommandID*<br/>
タスクをクリックしたときに実行されるコマンドのコマンド ID を指定します。

*dwUserData*<br/>
ユーザー定義データ。

*hwndTask*<br/>
タスクウィンドウへのハンドルを指定します。

*bAutoDestroyWindow*<br/>
TRUE の場合、タスクウィンドウは自動的に破棄されます。

*nWindowHeight*<br/>
タスクウィンドウの高さを指定します。

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a> CMFCTasksPaneTask:: m_bAutoDestroyWindow

タスクウィンドウを自動的に破棄するかどうかを決定します。

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>解説

タスクウィンドウ ( [CMFCTasksPaneTask:: m_hwndTask](#m_hwndtask)) を自動的に破棄するように指定するには、TRUE に設定します。それ以外の場合は FALSE。

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a> CMFCTasksPaneTask:: m_bIsBold

タスクラベルを太字テキストで描画するかどうかを決定します。

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>解説

タスクラベルに太字のテキストを表示するには、このメンバーを TRUE に設定します。

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a> CMFCTasksPaneTask:: m_dwUserData

タスクに関連付けられているユーザー定義データを格納します。 タスクにデータが関連付けられていない場合は、0に設定します。

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a> CMFCTasksPaneTask:: m_hwndTask

タスクウィンドウへのハンドル。

```
HWND m_hwndTask;
```

### <a name="remarks"></a>解説

タスクウィンドウを追加するには、 [CMFCTasksPane:: AddWindow](../../mfc/reference/cmfctaskspane-class.md#addwindow)を呼び出します。

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a> CMFCTasksPaneTask:: m_nIcon

指定したタスクの横に表示されるイメージを識別するイメージリスト内のインデックス位置。

```
int m_nIcon;
```

### <a name="remarks"></a>解説

イメージリストは [CMFCTasksPane:: SetIconsList](../../mfc/reference/cmfctaskspane-class.md#seticonslist)によって設定されます。

`m_nIcon`イメージを使用せずにタスクを表示する場合は、-1 に設定します。

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a> CMFCTasksPaneTask:: m_nWindowHeight

タスクウィンドウの高さ。 タスクウィンドウがない場合、この値は0です。

```
int m_nWindowHeight;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a> CMFCTasksPaneTask:: m_pGroup

このタスクが所属する [CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md) へのポインター。

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>解説

すべてのタスクに親グループが必要です。 グループを作業ウィンドウに追加するには、 [CMFCTasksPane:: AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)を呼び出します。

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTask:: m_rect

タスクの外接する四角形を指定します。

```
CRect m_rect;
```

### <a name="remarks"></a>解説

この値は、タスクが描画されるときにフレームワークによって計算されます。

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTask:: m_strName

タスクの名前です。

```
CString m_strName;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a> CMFCTasksPaneTask:: m_uiCommandID

ユーザーがタスクをクリックしたときに実行されるコマンドのコマンド ID を指定します。 この値が有効なコマンド ID でない場合、タスクは単純なラベルとして扱われます。

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTask:: Setのデータ

現在のタスクのユーザー補助データを決定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
から現在のタスクの親ウィンドウを表します。

*data*<br/>
入出力 `CAccessibilityData` 現在のタスクのユーザー補助データを格納する型のオブジェクト。

### <a name="return-value"></a>戻り値

*データ* パラメーターに現在のタスクのアクセシビリティデータが正常に設定された場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)
