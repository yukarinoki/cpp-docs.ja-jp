---
description: '詳細情報: CMFCTasksPaneTaskGroup クラス'
title: CMFCTasksPaneTaskGroup クラス
ms.date: 11/19/2018
f1_keywords:
- CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::CMFCTasksPaneTaskGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::SetACCData
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsBottom
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsCollapsed
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_bIsSpecial
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_lstTasks
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rect
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_rectGroup
- AFXTASKSPANE/CMFCTasksPaneTaskGroup::m_strName
helpviewer_keywords:
- CMFCTasksPaneTaskGroup [MFC], CMFCTasksPaneTaskGroup
- CMFCTasksPaneTaskGroup [MFC], SetACCData
- CMFCTasksPaneTaskGroup [MFC], m_bIsBottom
- CMFCTasksPaneTaskGroup [MFC], m_bIsCollapsed
- CMFCTasksPaneTaskGroup [MFC], m_bIsSpecial
- CMFCTasksPaneTaskGroup [MFC], m_lstTasks
- CMFCTasksPaneTaskGroup [MFC], m_rect
- CMFCTasksPaneTaskGroup [MFC], m_rectGroup
- CMFCTasksPaneTaskGroup [MFC], m_strName
ms.assetid: 2111640b-a46e-4b27-b033-29e88632b86a
ms.openlocfilehash: 6b09923c70ad6208b1b029e6ad555c22cd4c771f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254704"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup クラス

クラスは、 `CMFCTasksPaneTaskGroup` [CMFCTasksPane](../../mfc/reference/cmfctaskspane-class.md) コントロールによって使用されるヘルパークラスです。 `CMFCTasksPaneTaskGroup` 型のオブジェクトは *タスク グループ* を表します。 タスク グループは、閉じるボタンがある独立したボックスにフレームワークによって表示される項目の一覧です。 このボックスには、オプションのキャプション (グループ名) があります。 グループが閉じると、タスクの一覧は表示されません。

## <a name="syntax"></a>構文

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: CMFCTasksPaneTaskGroup](#cmfctaskspanetaskgroup)|`CMFCTasksPaneTaskGroup` オブジェクトを構築します。|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: Setのデータ](#setaccdata)|現在のタスクグループのユーザー補助データを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[CMFCTasksPaneTaskGroup:: m_bIsBottom](#m_bisbottom)|タスクグループを作業ウィンドウコントロールの下部に揃えるかどうかを決定します。|
|[CMFCTasksPaneTaskGroup:: m_bIsCollapsed](#m_biscollapsed)|タスクグループが折りたたまれているかどうかを判断します。|
|[CMFCTasksPaneTaskGroup:: m_bIsSpecial](#m_bisspecial)|タスクグループが特別であるかどうかを判断し *ます。* フレームワークでは、特殊なキャプションが異なる色で表示されます。|
|[CMFCTasksPaneTaskGroup:: m_lstTasks](#m_lsttasks)|タスクの内部リストを格納します。|
|[CMFCTasksPaneTaskGroup:: m_rect](#m_rect)|グループキャプションの外接する四角形を指定します。|
|[CMFCTasksPaneTaskGroup:: m_rectGroup](#m_rectgroup)|グループの外接する四角形を指定します。|
|[CMFCTasksPaneTaskGroup:: m_strName](#m_strname)|グループの名前を指定します。|

## <a name="remarks"></a>解説

次の図は、展開されたタスクグループを示しています。

![タスクグループ、展開](../../mfc/reference/media/nexttaskgrpexpand.png "展開されたタスク グループ")

次の図は、折りたたまれたタスクグループを示しています。

![折りたたまれたタスク グループ](../../mfc/reference/media/nexttaskgrpcollapse.png "折りたたまれたタスク グループ")

次の図は、キャプションのないタスクグループを示しています。

![キャプションのないタスク グループ](../../mfc/reference/media/nexttaskgrpnocapt.png "キャプションのないタスク グループ")

次の図は、2つのタスクグループを示しています。 最初のタスクグループは、フラグを TRUE に設定することによって特殊としてマークされますが、 `m_bIsSpecial` 2 番目のタスクグループは特別ではありません。 最初のタスクグループのキャプションが2番目のタスクグループよりも濃いことに注意してください。

![特殊なタスク グループ](../../mfc/reference/media/nexttaskgrpspecial.png "特殊なタスク グループ")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxtaskspane.h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a> CMFCTasksPaneTaskGroup:: CMFCTasksPaneTaskGroup

`CMFCTasksPaneTaskGroup` オブジェクトを構築します。

```
CMFCTasksPaneTaskGroup(
    LPCTSTR lpszName,
    BOOL bIsBottom,
    BOOL bIsSpecial=FALSE,
    BOOL bIsCollapsed=FALSE,
    CMFCTasksPanePropertyPage* pPage=NULL,
    HICON hIcon=NULL);
```

### <a name="parameters"></a>パラメーター

*lpszName*<br/>
グループキャプション内のグループの名前を指定します。

*bIsBottom*<br/>
グループを作業ウィンドウコントロールの下部に揃えるかどうかを指定します。

*bIsSpecial*<br/>
グループが *特別な* ものとして指定されているかどうかを指定します。そのため、グループキャプションに別の色が設定されているかどうかを示します。

*bIsCollapsed*<br/>
グループを折りたたむかどうかを指定します。

*pPage*<br/>
このタスクグループが属しているプロパティページを指定します。

*hIcon*<br/>
グループキャプションに表示するアイコンを指定します。

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a> CMFCTasksPaneTaskGroup:: m_bIsBottom

タスクグループを作業ウィンドウコントロールの下部に揃えるかどうかを決定します。

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>解説

作業ウィンドウコントロールの下部に配置できるグループは1つだけです。 このタスクグループは最後に追加する必要があります。 詳細については、「 [CMFCTasksPane:: AddGroup](../../mfc/reference/cmfctaskspane-class.md#addgroup)」を参照してください。

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a> CMFCTasksPaneTaskGroup:: m_bIsCollapsed

タスクグループが折りたたまれているかどうかを判断します。

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>解説

[CMFCTasksPane:: EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)を呼び出すことにより、作業ウィンドウでグループを折りたたむ機能を有効または無効にすることができます。

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a> CMFCTasksPaneTaskGroup:: m_bIsSpecial

タスクグループが *特別* であるかどうか、および特別なタスクグループのキャプションを別の色で識別する必要があるかどうかを判断します。

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>解説

アプリケーションが Windows XP ビジュアルテーマを使用していて、 `m_bIsSpecial` が FALSE の場合、フレームワークは EBP_NORMALGROUPBACKGROUND フラグを使用してを呼び出し `DrawThemeBackground` ます。 `m_bIsSpecial`が TRUE の場合、フレームワークは `DrawThemeBackground` EBP_SPECIALGROUPBACKGROUND フラグを使用してを呼び出します。

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a> CMFCTasksPaneTaskGroup:: m_lstTasks

タスクの内部リストを格納します。

```
CObList m_lstTasks;
```

### <a name="remarks"></a>解説

この一覧に入力するには、 [CMFCTasksPane:: AddTask](../../mfc/reference/cmfctaskspane-class.md#addtask)を呼び出します。

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a> CMFCTasksPaneTaskGroup:: m_rect

グループキャプションの外接する四角形を指定します。

```
CRect m_rect;
```

### <a name="remarks"></a>解説

この値は、フレームワークによって自動的に計算されます。

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a> CMFCTasksPaneTaskGroup:: m_rectGroup

グループの外接する四角形を指定します。

```
CRect m_rectGroup;
```

### <a name="remarks"></a>解説

この値は、フレームワークによって自動的に計算されます。

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a> CMFCTasksPaneTaskGroup:: m_strName

グループの名前を指定します。

```
CString m_strName;
```

### <a name="remarks"></a>解説

この値が空の場合、グループのキャプションは表示されず、グループを折りたたむことはできません。

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a> CMFCTasksPaneTaskGroup:: Setのデータ

現在のタスクグループのユーザー補助データを決定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*pParent*<br/>
から現在のタスクグループの親ウィンドウを表します。

*data*<br/>
入出力 `CAccessibilityData` 現在のタスクグループのアクセシビリティデータを格納する型のオブジェクト。

### <a name="return-value"></a>戻り値

*データ* パラメーターに現在のタスクグループのアクセシビリティデータが正常に設定された場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[階層図](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCTasksPane クラス](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask クラス](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[CMFCOutlookBar クラス](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[CObject クラス](../../mfc/reference/cobject-class.md)
