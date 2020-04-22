---
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
ms.openlocfilehash: 14ac32524436ff46449171ad90599e60f63dff2a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750157"
---
# <a name="canimationgroup-class"></a>CAnimationGroup クラス

アニメーション グループを実装し、アニメーション ストーリーボード、アニメーション オブジェクト、およびトランジションを組み合わせてアニメーションを定義します。

## <a name="syntax"></a>構文

```
class CAnimationGroup;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cアニメーショングループ::Cアニメーショングループ](#canimationgroup)|アニメーション グループを作成します。|
|[C アニメーショングループ::~Cアニメーショングループ](#_dtorcanimationgroup)|デストラクターです。 アニメーション グループが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[アニメーショングループ:アニメーション](#animate)|グループをアニメーション化します。|
|[Cアニメーショングループ::移行を適用します。](#applytransitions)|アニメーション オブジェクトにトランジションを適用します。|
|[アニメーショングループ::アニメーションオブジェクトを検索します。](#findanimationobject)|指定したアニメーション変数を含むアニメーション オブジェクトを検索します。|
|[グループグループを取得します。](#getgroupid)|グループ ID を返します。|
|[Cアニメーショングループ::キーフレームの削除](#removekeyframes)|アニメーション グループに属するすべてのキーフレームを削除し、必要に応じて破棄します。|
|[C アニメーショングループ::トランジションの削除](#removetransitions)|アニメーション グループに属するアニメーション オブジェクトからトランジションを削除します。|
|[Cアニメーショングループ::スケジュール](#schedule)|指定した時間にアニメーションをスケジュールします。|
|[Cアニメーショングループ::設定オートデストロイトランジション](#setautodestroytransitions)|グループに属するすべてのアニメーション オブジェクトが自動的にトランジションを破棄するように指示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーショングループ::キーフレームの追加](#addkeyframes)|ストーリーボードにキーフレームを追加するヘルパー。|
|[C アニメーショングループ::トランジションの追加](#addtransitions)|ストーリーボードにトランジションを追加するヘルパー。|
|[Cアニメーショングループ::移行を作成します。](#createtransitions)|COM 遷移オブジェクトを作成するヘルパー。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cアニメーショングループ::m_bAutoclearTransitions](#m_bautocleartransitions)|グループに属するアニメーション オブジェクトから遷移をクリアする方法を指定します。 このメンバーが TRUE の場合、アニメーションがスケジュールされると、遷移は自動的に削除されます。 それ以外の場合は、手動でトランジションを削除する必要があります。|
|[Cアニメーショングループ::m_bAutodestroyAnimationObjects](#m_bautodestroyanimationobjects)|アニメーション オブジェクトを破棄する方法を指定します。 このパラメータが TRUE の場合、グループが破棄されると、アニメーション オブジェクトは自動的に破棄されます。 それ以外の場合は、アニメーション オブジェクトを手動で破棄する必要があります。 既定値は FALSE です。 この値を TRUE に設定するのは、グループに属するすべてのアニメーション オブジェクトが、演算子 new で動的に割り当てられている場合のみです。|
|[Cアニメーショングループ::m_bAutodestroyKeyframes](#m_bautodestroykeyframes)|キーフレームを破棄する方法を指定します。 この値が TRUE の場合、すべてのキーフレームが削除され、破棄されます。それ以外の場合は、リストからしか削除されません。 既定値は TRUE です。|
|[Cアニメーショングループ::m_lstAnimationObjects](#m_lstanimationobjects)|アニメーション オブジェクトの一覧を格納します。|
|[Cアニメーショングループ::m_lstKeyFrames](#m_lstkeyframes)|キーフレームのリストが含まれます。|
|[Cアニメーショングループ::m_pStoryboard](#m_pstoryboard)|アニメーション ストーリーボードへのポイント。 このポインターは、Animate での呼び出し後にのみ有効です。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[Cアニメーショングループ::m_nGroupID](#m_ngroupid)|アニメーション グループの一意の識別子。|
|[Cアニメーショングループ::m_pParentController](#m_pparentcontroller)|このグループが属するアニメーション コントローラへのポインタ。|

## <a name="remarks"></a>解説

アニメーション グループは、アニメーション オブジェクトを追加するときにアニメーション コントローラ (CAnimationController) によって自動的に作成されます: ::アニメーション オブジェクト。 アニメーション グループは GroupID によって識別され、通常はアニメーション グループを操作するためのパラメータとして使用されます。 GroupID は、新しいアニメーション グループに追加される最初のアニメーション オブジェクトから取得されます。 カプセル化されたアニメーション ストーリーボードは、CAnimationController::AnimateGroup を呼び出した後に作成され、パブリック メンバー m_pStoryboardを介してアクセスできます。

## <a name="inheritance-hierarchy"></a>継承階層

`CAnimationGroup`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationgroupcanimationgroup"></a><a name="_dtorcanimationgroup"></a>C アニメーショングループ::~Cアニメーショングループ

デストラクターです。 アニメーション グループが破棄されるときに呼び出されます。

```
~CAnimationGroup();
```

## <a name="canimationgroupaddkeyframes"></a><a name="addkeyframes"></a>Cアニメーショングループ::キーフレームの追加

ストーリーボードにキーフレームを追加するヘルパー。

```cpp
void AddKeyframes(IUIAnimationStoryboard* pStoryboard, BOOL bAddDeep);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
ストーリーボード COM オブジェクトへのポインター。

*ディープを追加します。*<br/>
このメソッドが、他のキーフレームに依存するストーリーボードキーフレームに追加するかどうかを指定します。

## <a name="canimationgroupaddtransitions"></a><a name="addtransitions"></a>C アニメーショングループ::トランジションの追加

ストーリーボードにトランジションを追加するヘルパー。

```cpp
void AddTransitions(
    IUIAnimationStoryboard* pStoryboard,
    BOOL bDependOnKeyframes);
```

### <a name="parameters"></a>パラメーター

*ストーリーボード*<br/>
ストーリーボード COM オブジェクトへのポインター。

*ブディペンディオンキーフレーム*

## <a name="canimationgroupanimate"></a><a name="animate"></a>アニメーショングループ:アニメーション

グループをアニメーション化します。

```
BOOL Animate(
    IUIAnimationManager* pManager,
    IUIAnimationTimer* pTimer,
    BOOL bScheduleNow);
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
*今すぐ設定*
*bScheduleNow*

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、内部ストーリーボードを作成し、遷移を作成して適用し、bScheduleNow が TRUE の場合にアニメーションをスケジュールします。 bScheduleNow が FALSE の場合は、指定した時刻にアニメーションを開始するためにスケジュールを呼び出す必要があります。

## <a name="canimationgroupapplytransitions"></a><a name="applytransitions"></a>Cアニメーショングループ::移行を適用します。

アニメーション オブジェクトにトランジションを適用します。

```cpp
void ApplyTransitions();
```

### <a name="remarks"></a>解説

このメソッドは、ストーリーボードが作成されていない場合は、デバッグ モードで ASSERTS します。 最初にすべてのトランジションを作成し、次に「静的」キーフレーム(オフセットに依存するキーフレーム)を追加し、キーフレームに依存しないトランジションを追加し、トランジションやその他のキーフレームに応じてキーフレームを追加し、キーフレームに依存するトランジションを最後に追加します。

## <a name="canimationgroupcanimationgroup"></a><a name="canimationgroup"></a>Cアニメーショングループ::Cアニメーショングループ

アニメーション グループを作成します。

```
CAnimationGroup(CAnimationController* pParentController, UINT32 nGroupID);
```

### <a name="parameters"></a>パラメーター

*を行う*<br/>
グループを作成するアニメーション コントローラへのポインター。

*グループ ID*<br/>
グループ ID を指定します。

## <a name="canimationgroupcreatetransitions"></a><a name="createtransitions"></a>Cアニメーショングループ::移行を作成します。

COM 遷移オブジェクトを作成するヘルパー。

```
BOOL CreateTransitions();
```

### <a name="return-value"></a>戻り値

TRUE はメソッドが成功し、それ以外の場合は FALSE です。

## <a name="canimationgroupfindanimationobject"></a><a name="findanimationobject"></a>アニメーショングループ::アニメーションオブジェクトを検索します。

指定したアニメーション変数を含むアニメーション オブジェクトを検索します。

```
CAnimationBaseObject* FindAnimationObject(IUIAnimationVariable* pVariable);
```

### <a name="parameters"></a>パラメーター

*変数*<br/>
アニメーション変数へのポインター。

### <a name="return-value"></a>戻り値

アニメーション オブジェクトへのポインター、 または NULL (アニメーション オブジェクトが見つからない場合)。

## <a name="canimationgroupgetgroupid"></a><a name="getgroupid"></a>グループグループを取得します。

グループ ID を返します。

```
UINT32 GetGroupID() const;
```

### <a name="return-value"></a>戻り値

グループ識別子。

## <a name="canimationgroupm_bautocleartransitions"></a><a name="m_bautocleartransitions"></a>Cアニメーショングループ::m_bAutoclearTransitions

グループに属するアニメーション オブジェクトから遷移をクリアする方法を指定します。 このメンバーが TRUE の場合、アニメーションがスケジュールされると、遷移は自動的に削除されます。 それ以外の場合は、手動でトランジションを削除する必要があります。

```
BOOL m_bAutoclearTransitions;
```

## <a name="canimationgroupm_bautodestroyanimationobjects"></a><a name="m_bautodestroyanimationobjects"></a>Cアニメーショングループ::m_bAutodestroyAnimationObjects

アニメーション オブジェクトを破棄する方法を指定します。 このパラメータが TRUE の場合、グループが破棄されると、アニメーション オブジェクトは自動的に破棄されます。 それ以外の場合は、アニメーション オブジェクトを手動で破棄する必要があります。 既定値は FALSE です。 この値を TRUE に設定するのは、グループに属するすべてのアニメーション オブジェクトが、演算子 new で動的に割り当てられている場合のみです。

```
BOOL m_bAutodestroyAnimationObjects;
```

## <a name="canimationgroupm_bautodestroykeyframes"></a><a name="m_bautodestroykeyframes"></a>Cアニメーショングループ::m_bAutodestroyKeyframes

キーフレームを破棄する方法を指定します。 この値が TRUE の場合、すべてのキーフレームが削除され、破棄されます。それ以外の場合は、リストからしか削除されません。 既定値は TRUE です。

```
BOOL m_bAutodestroyKeyframes;
```

## <a name="canimationgroupm_lstanimationobjects"></a><a name="m_lstanimationobjects"></a>Cアニメーショングループ::m_lstAnimationObjects

アニメーション オブジェクトの一覧を格納します。

```
CObList m_lstAnimationObjects;
```

## <a name="canimationgroupm_lstkeyframes"></a><a name="m_lstkeyframes"></a>Cアニメーショングループ::m_lstKeyFrames

キーフレームのリストが含まれます。

```
CObList m_lstKeyFrames;
```

## <a name="canimationgroupm_ngroupid"></a><a name="m_ngroupid"></a>Cアニメーショングループ::m_nGroupID

アニメーション グループの一意の識別子。

```
UINT32 m_nGroupID;
```

## <a name="canimationgroupm_pparentcontroller"></a><a name="m_pparentcontroller"></a>Cアニメーショングループ::m_pParentController

このグループが属するアニメーション コントローラへのポインタ。

```
CAnimationController* m_pParentController;
```

## <a name="canimationgroupm_pstoryboard"></a><a name="m_pstoryboard"></a>Cアニメーショングループ::m_pStoryboard

アニメーション ストーリーボードへのポイント。 このポインターは、Animate での呼び出し後にのみ有効です。

```
ATL::CComPtr<IUIAnimationStoryboard> m_pStoryboard;
```

## <a name="canimationgroupremovekeyframes"></a><a name="removekeyframes"></a>Cアニメーショングループ::キーフレームの削除

アニメーション グループに属するすべてのキーフレームを削除し、必要に応じて破棄します。

```cpp
void RemoveKeyframes();
```

### <a name="remarks"></a>解説

もしm_bAutodestroyKeyframesメンバーがTRUEの場合、キーフレームは削除されて破壊され、それ以外の場合はキーフレームはキーフレームの内部リストから削除されます。

## <a name="canimationgroupremovetransitions"></a><a name="removetransitions"></a>C アニメーショングループ::トランジションの削除

アニメーション グループに属するアニメーション オブジェクトからトランジションを削除します。

```cpp
void RemoveTransitions();
```

### <a name="remarks"></a>解説

フラグm_bAutoclearTransitions TRUE に設定されている場合、このメソッドはグループに属するすべてのアニメーション オブジェクトをループし、CAnimationObject::ClearTransitions(FALSE) を呼び出します。

## <a name="canimationgroupschedule"></a><a name="schedule"></a>Cアニメーショングループ::スケジュール

指定した時間にアニメーションをスケジュールします。

```
BOOL Schedule(IUIAnimationTimer* pTimer, UI_ANIMATION_SECONDS time);
```

### <a name="parameters"></a>パラメーター

*pタイマー*<br/>
アニメーション タイマーへのポインター。

*time*<br/>
アニメーションのスケジュールを設定する時間を指定します。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は TRUE。メソッドが失敗した場合、またはアニメーションが bScheduleNow を FALSE に設定して呼び出されていない場合は FALSE。

### <a name="remarks"></a>解説

指定した時間にアニメーションをスケジュールします。 最初に、bScheduleNow を FALSE に設定してアニメーションを呼び出す必要があります。

## <a name="canimationgroupsetautodestroytransitions"></a><a name="setautodestroytransitions"></a>Cアニメーショングループ::設定オートデストロイトランジション

グループに属するすべてのアニメーション オブジェクトが自動的にトランジションを破棄するように指示します。

```cpp
void SetAutodestroyTransitions(BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>パラメーター

*b自動破壊*<br/>
トランジションを破棄する方法を指定します。

### <a name="remarks"></a>解説

この値を FALSE に設定するのは、スタックに遷移を割り当てる場合だけです。 既定値は TRUE なので、演算子 new を使用して遷移オブジェクトを割り当てることを強くお勧めします。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
