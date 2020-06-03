---
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
ms.openlocfilehash: 49fccdf161da7deb1fd88a12a107df40bafdae92
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375868"
---
# <a name="cmfctaskspanetask-class"></a>CMFCTasksPaneTask クラス

クラス`CMFCTasksPaneTask`は、作業ウィンドウ コントロール ( [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md)) のタスクを表すヘルパー クラスです。 タスク オブジェクトは、タスク[グループ内の](../../mfc/reference/cmfctaskspanetaskgroup-class.md)項目を表します 。 各タスクには、ユーザーがタスク名の左側に表示されるタスクやアイコンをクリックしたときにフレームワークが実行するコマンドを設定できます。

## <a name="syntax"></a>構文

```
class CMFCTasksPaneTask : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[タスク::CMFC タスク ペインタスク](#cmfctaskspanetask)|`CMFCTasksPaneTask` オブジェクトを構築して、初期化します。|
|`CMFCTasksPaneTask::~CMFCTasksPaneTask`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[タスク::セットアプデータ](#setaccdata)|現在のタスクのアクセシビリティ データを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[タスク::m_bAutoDestroyWindow](#m_bautodestroywindow)|タスク ウィンドウが自動的に破棄されるかどうかを判断します。|
|[タスク::m_bIsBold](#m_bisbold)|フレームワークがタスク ラベルを太字テキストで描画するかどうかを決定します。|
|[タスク::m_dwUserData](#m_dwuserdata)|フレームワークがタスクに関連付けるユーザー定義データを格納します。 タスクに関連付けられたデータがない場合は、0 に設定します。|
|[タスク::m_hwndTask](#m_hwndtask)|タスク ウィンドウへのハンドル。|
|[タスク::m_nIcon](#m_nicon)|フレームワークがタスクの横に表示するイメージのイメージ リスト内のインデックス。|
|[タスク::m_nWindowHeight](#m_nwindowheight)|タスク ウィンドウの高さ。 タスクウィンドウがない場合、この値はゼロです。|
|[タスク::m_pGroup](#m_pgroup)|このタスクが属`CMFCTasksPaneTaskGroup`するへのポインター。|
|[タスク::m_rect](#m_rect)|タスクの外接する四角形を指定します。|
|[タスク::m_strName](#m_strname)|タスクの名前。|
|[タスク::m_uiCommandID](#m_uicommandid)|ユーザーがタスクをクリックしたときにフレームワークが実行するコマンドのコマンド ID を指定します。 この値が有効なコマンド ID でない場合、タスクは単純なラベルとして扱われます。|

## <a name="remarks"></a>解説

次の図は、3 つのタスクを含むタスク グループを示しています。

![タスク グループ、展開](../../mfc/reference/media/nexttaskgrpexpand.png "展開されたタスク グループ")

> [!NOTE]
> タスクに有効なコマンド ID がない場合は、単純なラベルとして扱われます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTask](../../mfc/reference/cmfctaskspanetask-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx タスクペイン.h

## <a name="cmfctaskspanetaskcmfctaskspanetask"></a><a name="cmfctaskspanetask"></a>タスク::CMFC タスク ペインタスク

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

*グループ化*<br/>
タスクが属する[CMFC タスク ペイン タスク グループ](../../mfc/reference/cmfctaskspanetaskgroup-class.md)を指定します。

*名前を指定します。*<br/>
タスクの名前を指定します。

*ニコン*<br/>
イメージ リスト内のタスクのイメージのインデックスを指定します。

*コマンド ID*<br/>
タスクがクリックされたときに実行されるコマンドのコマンド ID を指定します。

*データ*<br/>
ユーザー定義データ。

*タスク*<br/>
タスク ウィンドウへのハンドルを指定します。

*ウィンドウを破壊する*<br/>
TRUE の場合、タスク ウィンドウは自動的に破棄されます。

*ウィンドウの高さ*<br/>
タスク ウィンドウの高さを指定します。

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_bautodestroywindow"></a><a name="m_bautodestroywindow"></a>タスク::m_bAutoDestroyWindow

タスク ウィンドウが自動的に破棄されるかどうかを判断します。

```
BOOL m_bAutoDestroyWindow;
```

### <a name="remarks"></a>解説

タスク ウィンドウ ( [CMFCTasksPaneTask::m_hwndTask](#m_hwndtask)) を自動的に破棄するように指定するには TRUE に設定します。それ以外の場合は FALSE。

## <a name="cmfctaskspanetaskm_bisbold"></a><a name="m_bisbold"></a>タスク::m_bIsBold

タスク ラベルを太字で描画するかどうかを指定します。

```
BOOL m_bIsBold;
```

### <a name="remarks"></a>解説

タスク ラベルの太字テキストを表示するには、このメンバーを TRUE に設定します。

## <a name="cmfctaskspanetaskm_dwuserdata"></a><a name="m_dwuserdata"></a>タスク::m_dwUserData

タスクに関連付けられているユーザー定義データが含まれます。 タスクに関連付けられているデータがない場合は、ゼロに設定します。

```
DWORD m_dwUserData;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_hwndtask"></a><a name="m_hwndtask"></a>タスク::m_hwndTask

タスク ウィンドウへのハンドル。

```
HWND m_hwndTask;
```

### <a name="remarks"></a>解説

タスク ウィンドウを追加するには[、CMFC タスク ペインを](../../mfc/reference/cmfctaskspane-class.md#addwindow)呼び出します。

## <a name="cmfctaskspanetaskm_nicon"></a><a name="m_nicon"></a>タスク::m_nIcon

指定したタスクの横に表示されるイメージを識別するイメージ リスト内のインデックス位置。

```
int m_nIcon;
```

### <a name="remarks"></a>解説

イメージ リストは[、CMFC タスク ペインによって設定されます。](../../mfc/reference/cmfctaskspane-class.md#seticonslist)

画像`m_nIcon`を使用せずにタスクを表示する場合は、-1 に設定します。

## <a name="cmfctaskspanetaskm_nwindowheight"></a><a name="m_nwindowheight"></a>タスク::m_nWindowHeight

タスク ウィンドウの高さ。 タスクウィンドウがない場合、この値はゼロです。

```
int m_nWindowHeight;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_pgroup"></a><a name="m_pgroup"></a>タスク::m_pGroup

このタスクが属する[CMFC タスク ペインタスク グループ](../../mfc/reference/cmfctaskspanetaskgroup-class.md)へのポインター。

```
CMFCTasksPaneTaskGroup* m_pGroup;
```

### <a name="remarks"></a>解説

すべてのタスクには親グループが必要です。 グループを作業ウィンドウに追加するには[、CMFCTasksPane::AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)を呼び出します。

## <a name="cmfctaskspanetaskm_rect"></a><a name="m_rect"></a>タスク::m_rect

タスクの外接する四角形を指定します。

```
CRect m_rect;
```

### <a name="remarks"></a>解説

この値は、タスクが描画されるときにフレームワークによって計算されます。

## <a name="cmfctaskspanetaskm_strname"></a><a name="m_strname"></a>タスク::m_strName

タスクの名前。

```
CString m_strName;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskm_uicommandid"></a><a name="m_uicommandid"></a>タスク::m_uiCommandID

ユーザーがタスクをクリックしたときに実行されるコマンドのコマンド ID を指定します。 この値が有効なコマンド ID でない場合、タスクは単純なラベルとして扱われます。

```
UINT m_uiCommandID;
```

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetasksetaccdata"></a><a name="setaccdata"></a>タスク::セットアプデータ

現在のタスクのアクセシビリティ データを決定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*親*<br/>
[in]現在のタスクの親ウィンドウを表します。

*データ*<br/>
[アウト]現在のタスクの`CAccessibilityData`アクセシビリティ データが設定されている型のオブジェクト。

### <a name="return-value"></a>戻り値

*データ*パラメーターに現在のタスクのユーザー補助データが正常に設定された場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)
