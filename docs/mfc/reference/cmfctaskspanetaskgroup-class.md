---
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
ms.openlocfilehash: 4c24eba646bede462a5f3cfb85715278cfa7daee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366263"
---
# <a name="cmfctaskspanetaskgroup-class"></a>CMFCTasksPaneTaskGroup クラス

クラス`CMFCTasksPaneTaskGroup`は、コントロールによって使用されるヘルパー クラス[です](../../mfc/reference/cmfctaskspane-class.md)。 `CMFCTasksPaneTaskGroup` 型のオブジェクトは *タスク グループ*を表します。 タスク グループは、閉じるボタンがある独立したボックスにフレームワークによって表示される項目の一覧です。 このボックスには、オプションのキャプション (グループ名) があります。 グループが閉じると、タスクの一覧は表示されません。

## <a name="syntax"></a>構文

```
class CMFCTasksPaneTaskGroup : public CObject
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[タスクグループ::CMFC タスクペインタスクグループ](#cmfctaskspanetaskgroup)|`CMFCTasksPaneTaskGroup` オブジェクトを構築します。|
|`CMFCTasksPaneTaskGroup::~CMFCTasksPaneTaskGroup`|デストラクターです。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[タスクグループ::セットアプデータ](#setaccdata)|現在のタスク グループのアクセシビリティ データを決定します。|

### <a name="data-members"></a>データ メンバー

|名前|説明|
|----------|-----------------|
|[タスクグループ::m_bIsBottom](#m_bisbottom)|タスク グループを作業ウィンドウ コントロールの下部に配置するかどうかを指定します。|
|[タスクグループ::m_bIsCollapsed](#m_biscollapsed)|タスク グループが折りたたまれているかどうかを判断します。|
|[タスクグループ::m_bIsSpecial](#m_bisspecial)|タスク グループが特殊かどうかを判断*します。* フレームワークは、異なる色で特別なキャプションを表示します。|
|[タスクグループ::m_lstTasks](#m_lsttasks)|タスクの内部リストが含まれます。|
|[タスクグループ::m_rect](#m_rect)|グループ キャプションの外接する四角形を指定します。|
|[タスクグループ::m_rectGroup](#m_rectgroup)|グループの外接する四角形を指定します。|
|[タスクグループ::m_strName](#m_strname)|グループの名前を指定します。|

## <a name="remarks"></a>解説

次の図は、展開されたタスク グループを示しています。

![タスク グループ、展開](../../mfc/reference/media/nexttaskgrpexpand.png "展開されたタスク グループ")

次の図は、折りたたまれたタスク グループを示しています。

![折りたたまれたタスク グループ](../../mfc/reference/media/nexttaskgrpcollapse.png "折りたたまれたタスク グループ")

次の図は、キャプションのないタスク グループを示しています。

![キャプションのないタスク グループ](../../mfc/reference/media/nexttaskgrpnocapt.png "キャプションのないタスク グループ")

次の図は、2 つのタスク グループを示しています。 最初のタスク グループは、フラグを`m_bIsSpecial`TRUE に設定して特殊としてマークされますが、2 番目のタスク グループは特別ではありません。 最初のタスク グループのキャプションが 2 番目のタスク グループよりも暗い方法に注意してください。

![特殊なタスク グループ](../../mfc/reference/media/nexttaskgrpspecial.png "特殊なタスク グループ")

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CMFCTasksPaneTaskGroup](../../mfc/reference/cmfctaskspanetaskgroup-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afx タスクペイン.h

## <a name="cmfctaskspanetaskgroupcmfctaskspanetaskgroup"></a><a name="cmfctaskspanetaskgroup"></a>タスクグループ::CMFC タスクペインタスクグループ

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

*名前を指定します。*<br/>
グループ キャプションのグループの名前を指定します。

*bIsボトム*<br/>
グループを作業ウィンドウ コントロールの下部に配置するかどうかを指定します。

*bIsスペシャル*<br/>
グループを*特殊*として指定するかどうかを指定します。

*BIs崩壊*<br/>
グループを折りたたむかどうかを指定します。

*ページ*<br/>
このタスク グループが属するプロパティ ページを指定します。

*Hicon*<br/>
グループ キャプションに表示されるアイコンを指定します。

### <a name="remarks"></a>解説

## <a name="cmfctaskspanetaskgroupm_bisbottom"></a><a name="m_bisbottom"></a>タスクグループ::m_bIsBottom

タスク グループを作業ウィンドウ コントロールの下部に配置するかどうかを指定します。

```
BOOL m_bIsBottom;
```

### <a name="remarks"></a>解説

作業ウィンドウ コントロールの下部に配置できるグループは 1 つだけです。 このタスク グループは最後に追加する必要があります。 詳細については[、「CMFC タスク ペイン::グループの追加](../../mfc/reference/cmfctaskspane-class.md#addgroup)」を参照してください。

## <a name="cmfctaskspanetaskgroupm_biscollapsed"></a><a name="m_biscollapsed"></a>タスクグループ::m_bIsCollapsed

タスク グループが折りたたまれているかどうかを判断します。

```
BOOL m_bIsCollapsed;
```

### <a name="remarks"></a>解説

作業ウィンドウでグループを折りたたむ機能を有効または無効にするには[、CMFCTasksPane::EnableGroupCollapse](../../mfc/reference/cmfctaskspane-class.md#enablegroupcollapse)を呼び出します。

## <a name="cmfctaskspanetaskgroupm_bisspecial"></a><a name="m_bisspecial"></a>タスクグループ::m_bIsSpecial

タスク グループが*特殊*であるかどうか、および特殊なタスク グループのキャプションを別の色で識別するかどうかを決定します。

```
BOOL m_bIsSpecial;
```

### <a name="remarks"></a>解説

アプリケーションが Windows XP ビジュアル テーマを使用`m_bIsSpecial`していて FALSE の場合`DrawThemeBackground`、フレームワークはEBP_NORMALGROUPBACKGROUND フラグを使用して呼び出します。 TRUE`m_bIsSpecial`の場合、フレームワークは`DrawThemeBackground`EBP_SPECIALGROUPBACKGROUND フラグを使用して呼び出します。

## <a name="cmfctaskspanetaskgroupm_lsttasks"></a><a name="m_lsttasks"></a>タスクグループ::m_lstTasks

タスクの内部リストが含まれます。

```
CObList m_lstTasks;
```

### <a name="remarks"></a>解説

このリストを埋めるには[、CMFC タスク ペインを](../../mfc/reference/cmfctaskspane-class.md#addtask)呼び出します。

## <a name="cmfctaskspanetaskgroupm_rect"></a><a name="m_rect"></a>タスクグループ::m_rect

グループ キャプションの外接する四角形を指定します。

```
CRect m_rect;
```

### <a name="remarks"></a>解説

この値はフレームワークによって自動的に計算されます。

## <a name="cmfctaskspanetaskgroupm_rectgroup"></a><a name="m_rectgroup"></a>タスクグループ::m_rectGroup

グループの外接する四角形を指定します。

```
CRect m_rectGroup;
```

### <a name="remarks"></a>解説

この値はフレームワークによって自動的に計算されます。

## <a name="cmfctaskspanetaskgroupm_strname"></a><a name="m_strname"></a>タスクグループ::m_strName

グループの名前を指定します。

```
CString m_strName;
```

### <a name="remarks"></a>解説

この値が空の場合、グループキャプションは表示されず、グループを折りたたむことはできません。

## <a name="cmfctaskspanetaskgroupsetaccdata"></a><a name="setaccdata"></a>タスクグループ::セットアプデータ

現在のタスク グループのアクセシビリティ データを決定します。

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>パラメーター

*親*<br/>
[in]現在のタスク グループの親ウィンドウを表します。

*データ*<br/>
[アウト]現在のタスク`CAccessibilityData`グループのアクセシビリティ データが設定されている型のオブジェクト。

### <a name="return-value"></a>戻り値

*データ*パラメーターに、現在のタスク グループのユーザー補助データが正常に設定された場合は TRUE。それ以外の場合は FALSE。

## <a name="see-also"></a>関連項目

[階層グラフ](../../mfc/hierarchy-chart.md)<br/>
[クラス](../../mfc/reference/mfc-classes.md)<br/>
[クラス](../../mfc/reference/cmfctaskspane-class.md)<br/>
[CMFCTasksPaneTask クラス](../../mfc/reference/cmfctaskspanetask-class.md)<br/>
[クラス](../../mfc/reference/cmfcoutlookbar-class.md)<br/>
[Cオブジェクトクラス](../../mfc/reference/cobject-class.md)
