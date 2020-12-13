---
description: '詳細情報: CAnimationGroup クラス'
title: CAnimationGroup クラス
ms.date: 03/27/2019
f1_keywords:
- CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::CAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationGroup::Animate
- AFXANIMATIONCONTROLLER/CAnimationGroup::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationGroup::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::Schedule
- AFXANIMATIONCONTROLLER/CAnimationGroup::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::AddTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutoclearTransitions
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_bAutodestroyKeyframes
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_lstKeyFrames
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pStoryboard
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationGroup::m_pParentController
helpviewer_keywords:
- CAnimationGroup [MFC], CAnimationGroup
- CAnimationGroup [MFC], Animate
- CAnimationGroup [MFC], ApplyTransitions
- CAnimationGroup [MFC], FindAnimationObject
- CAnimationGroup [MFC], GetGroupID
- CAnimationGroup [MFC], RemoveKeyframes
- CAnimationGroup [MFC], RemoveTransitions
- CAnimationGroup [MFC], Schedule
- CAnimationGroup [MFC], SetAutodestroyTransitions
- CAnimationGroup [MFC], AddKeyframes
- CAnimationGroup [MFC], AddTransitions
- CAnimationGroup [MFC], CreateTransitions
- CAnimationGroup [MFC], m_bAutoclearTransitions
- CAnimationGroup [MFC], m_bAutodestroyAnimationObjects
- CAnimationGroup [MFC], m_bAutodestroyKeyframes
- CAnimationGroup [MFC], m_lstAnimationObjects
- CAnimationGroup [MFC], m_lstKeyFrames
- CAnimationGroup [MFC], m_pStoryboard
- CAnimationGroup [MFC], m_nGroupID
- CAnimationGroup [MFC], m_pParentController
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
ms.openlocfilehash: 45fd49b95f73811f52795b87bf3de2dd004fa5ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336803"
---
# <a name="canimationgroup-class"></a>CAnimationGroup クラス

アニメーションのストーリーボード、アニメーションオブジェクト、および遷移を組み合わせてアニメーションを定義するアニメーショングループを実装します。

## <a name="syntax"></a>構文

```
class CAnimationGroup;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CAnimationGroup:: CAnimationGroup](#canimationgroup)|アニメーショングループを構築します。|
|[CAnimationGroup:: ~ CAnimationGroup](#_dtorcanimationgroup)|デストラクターです。 アニメーショングループが破棄されているときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationGroup:: Animate](#animate)|グループをアニメーション化します。|
|[CAnimationGroup:: ApplyTransitions](#applytransitions)|アニメーションオブジェクトへの切り替え効果を適用します。|
|[CAnimationGroup:: Findアニメーションオブジェクト](#findanimationobject)|指定されたアニメーション変数を格納しているアニメーションオブジェクトを検索します。|
|[CAnimationGroup:: GetGroupID](#getgroupid)|GroupID を返します。|
|[CAnimationGroup:: RemoveKeyframes フレーム](#removekeyframes)|アニメーショングループに属しているすべてのキーフレームを削除し、必要に応じて破棄します。|
|[CAnimationGroup:: RemoveTransitions](#removetransitions)|アニメーショングループに属しているアニメーションオブジェクトからの切り替え効果を削除します。|
|[CAnimationGroup:: Schedule](#schedule)|指定した時刻にアニメーションをスケジュールします。|
|[CAnimationGroup:: SetAutodestroyTransitions](#setautodestroytransitions)|グループに属するすべてのアニメーションオブジェクトが、自動的に遷移を破棄します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationGroup:: AddKeyframes フレーム](#addkeyframes)|ストーリーボードにキーフレームを追加するヘルパー。|
|[CAnimationGroup:: AddTransitions](#addtransitions)|ストーリーボードに遷移を追加するヘルパー。|
|[CAnimationGroup:: CreateTransitions](#createtransitions)|COM 遷移オブジェクトを作成するヘルパー。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationGroup:: m_bAutoclearTransitions](#m_bautocleartransitions)|グループに属するアニメーションオブジェクトからの遷移をクリアする方法を指定します。 このメンバーが TRUE の場合、アニメーションがスケジュールされていると、遷移は自動的に削除されます。 それ以外の場合は、手動で移行を削除する必要があります。|
|[CAnimationGroup:: m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|アニメーションオブジェクトを破棄する方法を指定します。 このパラメーターが TRUE の場合、グループが破棄されるとアニメーションオブジェクトが自動的に破棄されます。 それ以外の場合は、手動でアニメーションオブジェクトを破棄する必要があります。 既定値は FALSE です。 グループに属するすべてのアニメーションオブジェクトが、operator new を使用して動的に割り当てられる場合にのみ、この値を TRUE に設定します。|
|[CAnimationGroup:: m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|キーフレームを破棄する方法を指定します。 この値が TRUE の場合、すべてのキーフレームが削除され、破棄されます。それ以外の場合は、一覧からのみ削除されます。 既定値は TRUE です。|
|[CAnimationGroup:: m_lstAnimationObjects](#m_lstanimationobjects)|アニメーションオブジェクトの一覧が含まれています。|
|[CAnimationGroup:: m_lstKeyFrames](#m_lstkeyframes)|キーフレームの一覧が含まれています。|
|[CAnimationGroup:: m_pStoryboard](#m_pstoryboard)|アニメーションストーリーボードをポイントします。 このポインターは、アニメーションでを呼び出した後にのみ有効です。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationGroup:: m_nGroupID](#m_ngroupid)|アニメーショングループの一意識別子。|
|[CAnimationGroup:: m_pParentController](#m_pparentcontroller)|このグループが属するアニメーションコントローラーへのポインター。|

## <a name="remarks"></a>解説

アニメーショングループは、CAnimationController:: Addanimation オブジェクトを使用してアニメーションオブジェクトを追加するときに、アニメーションコントローラー (CAnimationController) によって自動的に作成されます。 アニメーショングループは GroupID によって識別されます。これは通常、アニメーショングループを操作するためのパラメーターとして取得されます。 GroupID は、新しいアニメーショングループに追加される最初のアニメーションオブジェクトから取得されます。 CAnimationController:: AnimateGroup を呼び出した後に、カプセル化されたアニメーションストーリーボードが作成され、パブリックメンバー m_pStoryboard を介してアクセスできます。

## <a name="inheritance-hierarchy"></a>継承階層

`CAnimationGroup`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a> CAnimationGroup:: ~ CAnimationGroup

デストラクターです。 アニメーショングループが破棄されているときに呼び出されます。

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a> CAnimationGroup:: AddKeyframes フレーム

ストーリーボードにキーフレームを追加するヘルパー。

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
ストーリーボード COM オブジェクトへのポインター。

*bAddDeep*<br/>
他のキーフレームに依存するストーリーボードキーフレームにこのメソッドを追加するかどうかを指定します。

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a> CAnimationGroup:: AddTransitions

ストーリーボードに遷移を追加するヘルパー。

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>パラメーター

*pStoryboard*<br/>
ストーリーボード COM オブジェクトへのポインター。

*B依存性 Onキーフレーム*

## <a name="canimationgroupanimate"></a><a name="animate"></a> CAnimationGroup:: Animate

グループをアニメーション化します。

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>パラメーター

*pManager*<br/>
*Ptimer* 
*bScheduleNow*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、内部ストーリーボードを作成し、遷移を作成して適用し、bScheduleNow が TRUE の場合にアニメーションをスケジュールします。 BScheduleNow が FALSE の場合は、指定された時間にアニメーションを開始するために Schedule を呼び出す必要があります。

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a> CAnimationGroup:: ApplyTransitions

アニメーションオブジェクトへの切り替え効果を適用します。

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>解説

ストーリーボードが作成されていない場合、このメソッドはデバッグモードでアサートします。 最初にすべての遷移を作成し、次に "静的な" キーフレーム (オフセットに依存するキーフレーム) を追加します。また、キーフレームに依存しない遷移を追加し、遷移やその他のキーフレームに応じてキーフレームを追加し、最後にキーフレームに依存する遷移を追加します。

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a> CAnimationGroup:: CAnimationGroup

アニメーショングループを構築します。

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>パラメーター

*pParentController*<br/>
グループを作成するアニメーションコントローラーへのポインター。

*nGroupID*<br/>
GroupID を指定します。

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a> CAnimationGroup:: CreateTransitions

COM 遷移オブジェクトを作成するヘルパー。

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>戻り値

メソッドが成功する場合は TRUE、それ以外の場合は FALSE。

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a> CAnimationGroup:: Findアニメーションオブジェクト

指定されたアニメーション変数を格納しているアニメーションオブジェクトを検索します。

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>パラメーター

*pVariable*<br/>
アニメーション変数へのポインター。

### <a name="return-value"></a>戻り値

アニメーションオブジェクトへのポインター。アニメーションオブジェクトが見つからない場合は NULL。

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a> CAnimationGroup:: GetGroupID

GroupID を返します。

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>戻り値

グループ識別子。

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a> CAnimationGroup:: m_bAutoclearTransitions

グループに属するアニメーションオブジェクトからの遷移をクリアする方法を指定します。 このメンバーが TRUE の場合、アニメーションがスケジュールされていると、遷移は自動的に削除されます。 それ以外の場合は、手動で移行を削除する必要があります。

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a> CAnimationGroup:: m_bAutodestroyAnimationObjects

アニメーションオブジェクトを破棄する方法を指定します。 このパラメーターが TRUE の場合、グループが破棄されるとアニメーションオブジェクトが自動的に破棄されます。 それ以外の場合は、手動でアニメーションオブジェクトを破棄する必要があります。 既定値は FALSE です。 グループに属するすべてのアニメーションオブジェクトが、operator new を使用して動的に割り当てられる場合にのみ、この値を TRUE に設定します。

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a> CAnimationGroup:: m_bAutodestroyKeyframes

キーフレームを破棄する方法を指定します。 この値が TRUE の場合、すべてのキーフレームが削除され、破棄されます。それ以外の場合は、一覧からのみ削除されます。 既定値は TRUE です。

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a> CAnimationGroup:: m_lstAnimationObjects

アニメーションオブジェクトの一覧が含まれています。

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a> CAnimationGroup:: m_lstKeyFrames

キーフレームの一覧が含まれています。

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a> CAnimationGroup:: m_nGroupID

アニメーショングループの一意識別子。

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a> CAnimationGroup:: m_pParentController

このグループが属するアニメーションコントローラーへのポインター。

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a> CAnimationGroup:: m_pStoryboard

アニメーションストーリーボードをポイントします。 このポインターは、アニメーションでを呼び出した後にのみ有効です。

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a> CAnimationGroup:: RemoveKeyframes フレーム

アニメーショングループに属しているすべてのキーフレームを削除し、必要に応じて破棄します。

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>解説

M_bAutodestroyKeyframes メンバーが TRUE の場合、キーフレームが削除されて破棄されます。それ以外の場合は、キーフレームの内部リストからキーフレームが削除されます。

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a> CAnimationGroup:: RemoveTransitions

アニメーショングループに属しているアニメーションオブジェクトからの切り替え効果を削除します。

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>解説

M_bAutoclearTransitions フラグが TRUE に設定されている場合、このメソッドは、グループに属するすべてのアニメーションオブジェクトをループし、CAnimationObject:: ClearTransitions (FALSE) を呼び出します。

## <a name="canimationgroupschedule"></a><a name="schedule"></a> CAnimationGroup:: Schedule

指定した時刻にアニメーションをスケジュールします。

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>パラメーター

*pTimer*<br/>
アニメーションタイマーへのポインター。

*time*<br/>
アニメーションをスケジュールする時間を指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。メソッドが失敗した場合、または bScheduleNow を FALSE に設定してアニメーションが呼び出されなかった場合は FALSE。

### <a name="remarks"></a>解説

指定した時刻にアニメーションをスケジュールするには、この関数を呼び出します。 最初に bScheduleNow を FALSE に設定して、アニメーションを呼び出す必要があります。

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a> CAnimationGroup:: SetAutodestroyTransitions

グループに属するすべてのアニメーションオブジェクトが、自動的に遷移を破棄します。

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*bAutoDestroy*<br/>
遷移を破棄する方法を指定します。

### <a name="remarks"></a>解説

スタックに遷移を割り当てる場合にのみ、この値を FALSE に設定します。 既定値は TRUE であるため、operator new を使用して遷移オブジェクトを割り当てることを強くお勧めします。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
