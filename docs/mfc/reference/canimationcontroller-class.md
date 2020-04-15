---
title: CAnimationController クラス
ms.date: 03/27/2019
f1_keywords:
- CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::CAnimationController
- AFXANIMATIONCONTROLLER/CAnimationController::AddAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::AddKeyframeToGroup
- AFXANIMATIONCONTROLLER/CAnimationController::AnimateGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CleanUpGroup
- AFXANIMATIONCONTROLLER/CAnimationController::CreateKeyframe
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationManagerEvent
- AFXANIMATIONCONTROLLER/CAnimationController::EnableAnimationTimerEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnablePriorityComparisonHandler
- AFXANIMATIONCONTROLLER/CAnimationController::EnableStoryboardEventHandler
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::FindAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::GetKeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::GetUIAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::GetUITransitionLibrary
- AFXANIMATIONCONTROLLER/CAnimationController::IsAnimationInProgress
- AFXANIMATIONCONTROLLER/CAnimationController::IsValid
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationIntegerValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationManagerStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPostUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerPreUpdate
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationTimerRenderingTooSlow
- AFXANIMATIONCONTROLLER/CAnimationController::OnAnimationValueChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnBeforeAnimationStart
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCancel
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityCompress
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityConclude
- AFXANIMATIONCONTROLLER/CAnimationController::OnHasPriorityTrim
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardStatusChanged
- AFXANIMATIONCONTROLLER/CAnimationController::OnStoryboardUpdated
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAllAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationGroup
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationController::RemoveTransitions
- AFXANIMATIONCONTROLLER/CAnimationController::ScheduleGroup
- AFXANIMATIONCONTROLLER/CAnimationController::SetRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::UpdateAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::OnAfterSchedule
- AFXANIMATIONCONTROLLER/CAnimationController::gkeyframeStoryboardStart
- AFXANIMATIONCONTROLLER/CAnimationController::m_bIsValid
- AFXANIMATIONCONTROLLER/CAnimationController::m_lstAnimationGroups
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationManager
- AFXANIMATIONCONTROLLER/CAnimationController::m_pAnimationTimer
- AFXANIMATIONCONTROLLER/CAnimationController::m_pRelatedWnd
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionFactory
- AFXANIMATIONCONTROLLER/CAnimationController::m_pTransitionLibrary
helpviewer_keywords:
- CAnimationController [MFC], CAnimationController
- CAnimationController [MFC], AddAnimationObject
- CAnimationController [MFC], AddKeyframeToGroup
- CAnimationController [MFC], AnimateGroup
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], CreateKeyframe
- CAnimationController [MFC], EnableAnimationManagerEvent
- CAnimationController [MFC], EnableAnimationTimerEventHandler
- CAnimationController [MFC], EnablePriorityComparisonHandler
- CAnimationController [MFC], EnableStoryboardEventHandler
- CAnimationController [MFC], FindAnimationGroup
- CAnimationController [MFC], FindAnimationObject
- CAnimationController [MFC], GetKeyframeStoryboardStart
- CAnimationController [MFC], GetUIAnimationManager
- CAnimationController [MFC], GetUIAnimationTimer
- CAnimationController [MFC], GetUITransitionFactory
- CAnimationController [MFC], GetUITransitionLibrary
- CAnimationController [MFC], IsAnimationInProgress
- CAnimationController [MFC], IsValid
- CAnimationController [MFC], OnAnimationIntegerValueChanged
- CAnimationController [MFC], OnAnimationManagerStatusChanged
- CAnimationController [MFC], OnAnimationTimerPostUpdate
- CAnimationController [MFC], OnAnimationTimerPreUpdate
- CAnimationController [MFC], OnAnimationTimerRenderingTooSlow
- CAnimationController [MFC], OnAnimationValueChanged
- CAnimationController [MFC], OnBeforeAnimationStart
- CAnimationController [MFC], OnHasPriorityCancel
- CAnimationController [MFC], OnHasPriorityCompress
- CAnimationController [MFC], OnHasPriorityConclude
- CAnimationController [MFC], OnHasPriorityTrim
- CAnimationController [MFC], OnStoryboardStatusChanged
- CAnimationController [MFC], OnStoryboardUpdated
- CAnimationController [MFC], RemoveAllAnimationGroups
- CAnimationController [MFC], RemoveAnimationGroup
- CAnimationController [MFC], RemoveAnimationObject
- CAnimationController [MFC], RemoveTransitions
- CAnimationController [MFC], ScheduleGroup
- CAnimationController [MFC], SetRelatedWnd
- CAnimationController [MFC], UpdateAnimationManager
- CAnimationController [MFC], CleanUpGroup
- CAnimationController [MFC], OnAfterSchedule
- CAnimationController [MFC], gkeyframeStoryboardStart
- CAnimationController [MFC], m_bIsValid
- CAnimationController [MFC], m_lstAnimationGroups
- CAnimationController [MFC], m_pAnimationManager
- CAnimationController [MFC], m_pAnimationTimer
- CAnimationController [MFC], m_pRelatedWnd
- CAnimationController [MFC], m_pTransitionFactory
- CAnimationController [MFC], m_pTransitionLibrary
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
ms.openlocfilehash: 34a02567bfeb76666cc38ccf05dcc285a1f658f5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369753"
---
# <a name="canimationcontroller-class"></a>CAnimationController クラス

アニメーションを作成および管理するための中心的なインターフェイスを提供する、アニメーション コントローラーを実装します。

## <a name="syntax"></a>構文

```
class CAnimationController : public CObject;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cアニメーションコントローラ::Cアニメーションコントローラ](#canimationcontroller)|アニメーション コントローラを構築します。|
|[C アニメーションコントローラ::~Cアニメーションコントローラ](#_dtorcanimationcontroller)|デストラクターです。 アニメーション コントローラ オブジェクトが破棄されるときに呼び出されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[アニメーションコントローラ::アニメーションオブジェクトの追加](#addanimationobject)|アニメーション コントローラに属するグループにアニメーション オブジェクトを追加します。|
|[グループ化](#addkeyframetogroup)|グループにキーフレームを追加します。|
|[アニメーショングループ:アニメーショングループ](#animategroup)|アニメーションを実行するグループを準備し、必要に応じてスケジュールを設定します。|
|[クアニメーションコントローラ::クリーンアップグループ](#cleanupgroup)|オーバーロードされます。 アニメーションがスケジュールされたときにグループをクリーンアップするためにフレームワークによって呼び出されます。|
|[CAnimationController::CreateKeyframe](#createkeyframe)|オーバーロードされます。 遷移に依存するキーフレームを作成し、指定したグループに追加します。|
|[イベントを実行します。](#enableanimationmanagerevent)|アニメーション マネージャーの状態が変化したときに呼び出すハンドラーを設定または解放します。|
|[を実行します。](#enableanimationtimereventhandler)|タイミング イベントのハンドラとタイミング更新用のハンドラを設定または解放します。|
|[を実行します。](#enableprioritycomparisonhandler)|スケジュールされたストーリーボードをキャンセル、終了、トリミング、または圧縮できるかどうかを判断するために呼び出す優先比較ハンドラを設定または解除します。|
|[を有効にするイベント ハンドラー](#enablestoryboardeventhandler)|ストーリーボードの状態および更新イベントのハンドラーを設定または解放します。|
|[アニメーショングループを見つける](#findanimationgroup)|オーバーロードされます。 ストーリーボードでアニメーション グループを検索します。|
|[アニメーションコントローラ::アニメーションオブジェクトを検索します。](#findanimationobject)|指定したアニメーション変数を含むアニメーション オブジェクトを検索します。|
|[アニメーションコントローラ::ゲットキーフレームストーリーボードスタート](#getkeyframestoryboardstart)|ストーリーボードの開始位置を示すキーフレームを返します。|
|[アニメーションマネージャー::ゲットイアニメーションマネージャー](#getuianimationmanager)|カプセル化された IUIAnimationManager オブジェクトへのアクセスを提供します。|
|[アニメーションコントローラ::ゲットUIアニメーションタイマー](#getuianimationtimer)|カプセル化された IUIAnimationTimer オブジェクトへのアクセスを提供します。|
|[を切り替え::取得UIトランジションファクトリー](#getuitransitionfactory)|遷移ライブラリの作成に失敗した場合は、IUIAnimationTransitionFactory インターフェイスまたは NULL へのポインター。|
|[を切り替え::インターフェイスライブラリ](#getuitransitionlibrary)|カプセル化された IUI アニメーショントランジション ライブラリ オブジェクトへのアクセスを提供します。|
|[アニメーションコントローラ::イスアニメーションインプログレス](#isanimationinprogress)|少なくとも 1 つのグループがアニメーションを再生しているかどうかを示します。|
|[Cアニメーションコントローラ::IsValid](#isvalid)|アニメーション コントローラが有効かどうかを示します。|
|[を変更します。](#onanimationintegervaluechanged)|アニメーション変数の整数値が変更されたときに、フレームワークによって呼び出されます。|
|[を変更しました。](#onanimationmanagerstatuschanged)|アニメーション マネージャーから StatusChanged イベントに応答してフレームワークによって呼び出されます。|
|[Cアニメーションコントローラ::オンアニメーションタイマーポストアップデート](#onanimationtimerpostupdate)|アニメーションの更新が完了した後にフレームワークによって呼び出されます。|
|[C アニメーションコントローラ::オンアニメーションタイマープレアップデート](#onanimationtimerpreupdate)|アニメーションの更新を開始する前に、フレームワークによって呼び出されます。|
|[Cアニメーションコントローラ::オンアニメーションタイマーレンダリングスロー](#onanimationtimerrenderingtooslow)|アニメーションのレンダリング フレーム レートが望ましい最小フレーム レートを下回ったときに、フレームワークによって呼び出されます。|
|[アニメーションコントローラ::アニメーション値が変更されました](#onanimationvaluechanged)|アニメーション変数の値が変更されたときに、フレームワークによって呼び出されます。|
|[Cアニメーションコントローラ::オンBeforeアニメーションスタート](#onbeforeanimationstart)|アニメーションがスケジュールされる直前にフレームワークによって呼び出されます。|
|[をクリックします。](#onhasprioritycancel)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|
|[Cアニメーションコントローラ::オンハスプライオリティコンプレッサー](#onhasprioritycompress)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|
|[コンティプライズコンティを設定します。](#onhaspriorityconclude)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|
|[アニメーションコントローラ::オンハスプライオリティトリム](#onhasprioritytrim)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|
|[Cアニメーションコントローラ::オンストーリーボードステータス変更](#onstoryboardstatuschanged)|ストーリーボードの状態が変更されたときに、フレームワークによって呼び出されます。|
|[Cアニメーションコントローラ::オンストーリーボード更新](#onstoryboardupdated)|ストーリーボードが更新されたときに、フレームワークによって呼び出されます。|
|[をグループ化する](#removeallanimationgroups)|アニメーション コントローラからすべてのアニメーション グループを削除します。|
|[アニメーショングループを削除します。](#removeanimationgroup)|指定した ID のアニメーション グループをアニメーション コントローラから削除します。|
|[アニメーションコントローラ::アニメーションオブジェクトの削除](#removeanimationobject)|アニメーション コントローラからアニメーション オブジェクトを削除します。|
|[Cアニメーションコントローラ::トランジションの削除](#removetransitions)|指定したグループに属するアニメーション オブジェクトから遷移を削除します。|
|[Cアニメーションコントローラ::スケジュールグループ](#schedulegroup)|アニメーションをスケジュールします。|
|[Cアニメーションコントローラ::セット関連ウンド](#setrelatedwnd)|アニメーション コントローラとウィンドウの関係を確立します。|
|[アニメーションマネージャー::アニメーションマネージャー](#updateanimationmanager)|アニメーションマネージャーに、すべてのアニメーション変数の値を更新するように指示します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[クアニメーションコントローラ::クリーンアップグループ](#cleanupgroup)|オーバーロードされます。 グループをクリーンアップするヘルパー。|
|[Cアニメーションコントローラ::アフタースケジュール](#onafterschedule)|指定したグループのアニメーションがスケジュールされているときに、フレームワークによって呼び出されます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[アニメーションコントローラ::gキーフレームストーリーボードスタート](#g_keyframestoryboardstart)|ストーリーボードの開始を表すキーフレーム。|
|[m_bIsValid](#m_bisvalid)|アニメーション コントローラが有効かどうかを指定します。 現在の OS が Windows アニメーション API をサポートしていない場合、このメンバーは FALSE に設定されます。|
|[アニメーションコントローラ::m_lstAnimationGroups](#m_lstanimationgroups)|このアニメーション コントローラに属するアニメーション グループのリスト。|
|[アニメーションコントローラ::m_pAnimationManager](#m_panimationmanager)|アニメーション マネージャー COM オブジェクトへのポインターを格納します。|
|[アニメーションコントローラ::m_pAnimationTimer](#m_panimationtimer)|アニメーション タイマ COM オブジェクトへのポインターを格納します。|
|[アニメーションコントローラ::m_pRelatedWnd](#m_prelatedwnd)|アニメーション マネージャーの状態が変更された場合、または更新後イベントが発生したときに自動的に再描画できる、関連する CWnd オブジェクトへのポインター。 NULL にすることができます。|
|[コアニメーションコントローラ::m_pTransitionFactory](#m_ptransitionfactory)|遷移ファクトリ COM オブジェクトへのポインターを格納します。|
|[Cアニメーションコントローラ::m_pTransitionLibrary](#m_ptransitionlibrary)|遷移ライブラリ COM オブジェクトへのポインターを格納します。|

## <a name="remarks"></a>解説

CAnimationController クラスは、アニメーションを管理するキー クラスです。 アプリケーションでアニメーション コントローラのインスタンスを 1 つ以上作成し、必要に応じて CAnimationController::SetRelatedWnd を使用してアニメーション コントローラのインスタンスを CWnd オブジェクトに接続できます。 この接続は、アニメーション マネージャの状態が変更された場合やアニメーション タイマーが更新されたときに、WM_PAINTメッセージを関連するウィンドウに自動的に送信するために必要です。 このリレーションを有効にしていない場合は、アニメーションを手動で表示するウィンドウを再描画する必要があります。 このためには、CAnimationController からクラスを派生し、OnAnimationManagerStatusStatusChanged または OnAnimationTimerPostUpdate をオーバーライドし、必要に応じて 1 つ以上のウィンドウを無効にできます。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

`CAnimationController`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationcontrollercanimationcontroller"></a><a name="_dtorcanimationcontroller"></a>C アニメーションコントローラ::~Cアニメーションコントローラ

デストラクターです。 アニメーション コントローラ オブジェクトが破棄されるときに呼び出されます。

```
virtual ~CAnimationController(void);
```

## <a name="canimationcontrolleraddanimationobject"></a><a name="addanimationobject"></a>アニメーションコントローラ::アニメーションオブジェクトの追加

アニメーション コントローラに属するグループにアニメーション オブジェクトを追加します。

```
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```

### <a name="parameters"></a>パラメーター

*pObject*<br/>
アニメーション オブジェクトへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合に pObject が追加された既存または新しいアニメーション グループへのポインター。別のアニメーション コントローラに属するグループに pObject が既に追加されている場合は NULL。

### <a name="remarks"></a>解説

アニメーション オブジェクトをアニメーション コントローラに追加します。 オブジェクトは、オブジェクトのグループ ID に従ってグループに追加されます (CAnimationBaseObject::SetID を参照)。 アニメーション コントローラは、指定された GroupID を使用して最初に追加されたオブジェクトである場合、新しいグループを作成します。 アニメーション オブジェクトは、1 つのアニメーション コントローラにのみ追加できます。 オブジェクトを別のコントローラに追加する必要がある場合は、最初に RemoveAnimationObject を呼び出します。 グループに追加済みのオブジェクトに対して新しい GroupID を指定して SetID を呼び出すと、そのオブジェクトは古いグループから削除され、指定された ID の別のグループに追加されます。

## <a name="canimationcontrolleraddkeyframetogroup"></a><a name="addkeyframetogroup"></a>グループ化

グループにキーフレームを追加します。

```
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

*pキーフレーム*<br/>
キーフレームへのポインター。

### <a name="return-value"></a>戻り値

関数が成功した場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

通常、このメソッドを呼び出す必要はありません、代わりにCAnimationController::CreateKeyframeを使用して、作成されたキーフレームを自動的に作成してグループに追加します。

## <a name="canimationcontrolleranimategroup"></a><a name="animategroup"></a>アニメーショングループ:アニメーショングループ

アニメーションを実行するグループを準備し、必要に応じてスケジュールを設定します。

```
BOOL AnimateGroup(
    UINT32 nGroupID,
    BOOL bScheduleNow = TRUE);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

*今すぐスケジュールを設定します。*<br/>
アニメーションをすぐに実行するかどうかを指定します。

### <a name="return-value"></a>戻り値

アニメーションが正常にスケジュールされ、実行された場合は TRUE。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボードの作成、アニメーション変数の追加、トランジションの適用、キーフレームの設定を行います。 bScheduleNow を FALSE に設定すると、スケジュールが遅れることがあります。 この場合、指定したグループは、アニメーション用に設定されたストーリーボードを保持します。 その時点で、ストーリーボード変数とアニメーション変数のイベントを設定できます。 実際にアニメーションを実行する必要がある場合は、CAnimationController::スケジュールグループを呼び出します。

## <a name="canimationcontrollercanimationcontroller"></a><a name="canimationcontroller"></a>Cアニメーションコントローラ::Cアニメーションコントローラ

アニメーション コントローラを構築します。

```
CAnimationController(void);
```

## <a name="canimationcontrollercleanupgroup"></a><a name="cleanupgroup"></a>クアニメーションコントローラ::クリーンアップグループ

アニメーションがスケジュールされたときにグループをクリーンアップするためにフレームワークによって呼び出されます。

```
void CleanUpGroup(UINT32 nGroupID);
void CleanUpGroup(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

*グループ化*<br/>
クリーンアップするアニメーション グループへのポインター。

### <a name="remarks"></a>解説

このメソッドは、アニメーションがスケジュールされた後は関係ないので、指定したグループからすべてのトランジションとキーフレームを削除します。

## <a name="canimationcontrollercreatekeyframe"></a><a name="createkeyframe"></a>クアニメーションコントローラ::キーフレームの作成

遷移に依存するキーフレームを作成し、指定したグループに追加します。

```
CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseTransition* pTransition);

CKeyFrame* CreateKeyframe(
    UINT32 nGroupID,
    CBaseKeyFrame* pKeyframe,
    UI_ANIMATION_SECONDS offset = 0.0);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
キーフレームを作成する対象グループの ID を指定します。

*移行*<br/>
遷移へのポインター。 この移行の完了後に、ストーリーボードにキーフレームが挿入されます。

*pキーフレーム*<br/>
このキーフレームの基準キーフレームへのポインター。

*offset*<br/>
pKeyframe で指定した基準キーフレームからのオフセット (秒単位)。

### <a name="return-value"></a>戻り値

関数が正常に終了した場合は、新しく作成されたキーフレームへのポインター。

### <a name="remarks"></a>解説

返されたポインターを格納して、新しく作成されたキーフレームを他のキーフレームの基準にすることができます (2 番目のオーバーロードを参照)。 キーフレームで遷移を開始することもできます。CBaseTransition::SetKeyframes をご覧ください。 このようにして作成したキーフレームを削除する必要はありません。アニメーション グループによって自動的に削除されます。 キーフレームを他のキーフレームや遷移に基づいて作成する場合は注意し、循環参照が発生しないようにしてください。

## <a name="canimationcontrollerenableanimationmanagerevent"></a><a name="enableanimationmanagerevent"></a>イベントを実行します。

アニメーション マネージャーの状態が変化したときに呼び出すハンドラーを設定または解放します。

```
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
ハンドラを設定するか解放するかを指定します。

### <a name="return-value"></a>戻り値

ハンドラーが正常に設定または解放された場合は TRUE。

### <a name="remarks"></a>解説

ハンドラーが設定されている (有効にする) と、アニメーション マネージャーの状態が変更されたときに、Windows アニメーションが OnAnimationManagerStatusChanged を呼び出します。

## <a name="canimationcontrollerenableanimationtimereventhandler"></a><a name="enableanimationtimereventhandler"></a>を実行します。

タイミング イベントのハンドラとタイミング更新用のハンドラを設定または解放します。

```
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```

### <a name="parameters"></a>パラメーター

*b 有効にする*<br/>
ハンドラーを設定するか解放するかを指定します。

*アイドル動作*<br/>
タイマー更新ハンドラーのアイドル動作を指定します。

### <a name="return-value"></a>戻り値

ハンドラーが正常に設定または解放された場合は TRUE。最初にハンドラーを解放せずに、このメソッドが 2 回目に呼び出された場合、または他のエラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

ハンドラーが設定されている (有効にする) Windows アニメーション API が呼び出すと、OnAnimationTimerPreUpdate、オンアニメーションタイマーポストアップデート、レンダリングトゥースローメソッドが呼び出されます。 Windows アニメーション API の更新ストーリーボードを有効にするには、アニメーション タイマーを有効にする必要があります。 それ以外の場合は、すべてのアニメーション変数の値を更新するようにアニメーション マネージャーを指示するために、CAnimationController::UpdateAnimationManager を呼び出す必要があります。

## <a name="canimationcontrollerenableprioritycomparisonhandler"></a><a name="enableprioritycomparisonhandler"></a>を実行します。

スケジュールされたストーリーボードをキャンセル、終了、トリミング、または圧縮できるかどうかを判断するために呼び出す優先比較ハンドラを設定または解除します。

```
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```

### <a name="parameters"></a>パラメーター

*タイプを変更します。*<br/>
設定または解放するハンドラを指定するUI_ANIMATION_PHT_フラグの組み合わせ (備考を参照)。

### <a name="return-value"></a>戻り値

ハンドラーが正常に設定または解放された場合は TRUE。

### <a name="remarks"></a>解説

ハンドラーが設定されている (有効にした) Windows アニメーションは、dwHandlerType に応じて次の仮想メソッドを呼び出します。 dwHandler は、次のフラグの組み合わせにすることができます: UI_ANIMATION_PHT_NONE - すべてのハンドラーを解放 UI_ANIMATION_PHT_CANCELする - すべてのハンドラーを解放する - 設定の比較ハンドラーUI_ANIMATION_PHT_CONCLUDE - UI_ANIMATION_PHT_COMPRESSの終了 - 比較ハンドラーの圧縮 UI_ANIMATION_PHT_TRIM - UI_ANIMATION_PHT_CANCEL_REMOVEのトリミング - UI_ANIMATION_PHT_CONCLUDE_REMOVEの終了 - 終了比較ハンドラーUI_ANIMATION_PHT_COMPRESS_REMOVEを削除する - 比較ハンドラーを削除UI_ANIMATION_PHT_TRIM_REMOVE - 比較ハンドラーを削除します。トリム比較ハンドラを削除する

## <a name="canimationcontrollerenablestoryboardeventhandler"></a><a name="enablestoryboardeventhandler"></a>を有効にするイベント ハンドラー

ストーリーボードの状態および更新イベントのハンドラーを設定または解放します。

```
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,
    BOOL bEnable = TRUE);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

*b 有効にする*<br/>
ハンドラを設定するか解放するかを指定します。

### <a name="return-value"></a>戻り値

ハンドラーが正常に設定または解放された場合は TRUE。指定したアニメーション グループが見つかったか、指定したグループのアニメーションが開始されておらず、その内部ストーリーボードが NULL の場合は FALSE。

### <a name="remarks"></a>解説

ハンドラーが設定されている (有効にする) と 、Windows アニメーション API は、オンストーリーボードステータス変更とオンストーリーボードを呼び出す仮想メソッドを更新します。 ハンドラーは、カプセル化された IUIAnimationAnimationStoryboard オブジェクトを作成するため、指定されたアニメーション グループに対して CAnimationController::Animate が呼び出された後に設定する必要があります。

## <a name="canimationcontrollerfindanimationgroup"></a><a name="findanimationgroup"></a>アニメーショングループを見つける

グループ ID でアニメーション グループを検索します。

```
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

*ストーリーボード*<br/>
ストーリーボードへのポインター。

### <a name="return-value"></a>戻り値

指定した ID を持つグループが見つからない場合は、アニメーション グループへのポインターまたは NULL。

### <a name="remarks"></a>解説

このメソッドは、実行時にアニメーション グループを検索するために使います。 グループが作成され、特定の GroupID を持つ最初のアニメーション オブジェクトがアニメーション コントローラに追加されるときに、アニメーション グループの内部リストに追加されます。

## <a name="canimationcontrollerfindanimationobject"></a><a name="findanimationobject"></a>アニメーションコントローラ::アニメーションオブジェクトを検索します。

指定したアニメーション変数を含むアニメーション オブジェクトを検索します。

```
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,
    CAnimationBaseObject** ppObject,
    CAnimationGroup** ppGroup);
```

### <a name="parameters"></a>パラメーター

*変数*<br/>
アニメーション変数へのポインター。

*オブジェクト*<br/>
出力。 アニメーション オブジェクトへのポインターまたは NULL を含みます。

*ppグループ*<br/>
出力。 アニメーション オブジェクトを保持するアニメーション グループへのポインターを格納します。

### <a name="return-value"></a>戻り値

オブジェクトが見つかった場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

受信アニメーション変数からアニメーション オブジェクトを検索する必要がある場合に、イベント ハンドラーから呼び出されます。

## <a name="canimationcontrollergkeyframestoryboardstart"></a><a name="g_keyframestoryboardstart"></a>アニメーションコントローラ::gキーフレームストーリーボードスタート

ストーリーボードの開始を表すキーフレーム。

```
static CBaseKeyFrame gkeyframeStoryboardStart;
```

## <a name="canimationcontrollergetkeyframestoryboardstart"></a><a name="getkeyframestoryboardstart"></a>アニメーションコントローラ::ゲットキーフレームストーリーボードスタート

ストーリーボードの開始位置を示すキーフレームを返します。

```
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```

### <a name="return-value"></a>戻り値

ストーリーボードの開始を識別する基本キーフレームへのポインター。

### <a name="remarks"></a>解説

ストーリーボードが開始する瞬間に他のキーフレームまたはトランジションの基準を設定するには、このキーフレームを取得します。

## <a name="canimationcontrollergetuianimationmanager"></a><a name="getuianimationmanager"></a>アニメーションマネージャー::ゲットイアニメーションマネージャー

カプセル化された IUIAnimationManager オブジェクトへのアクセスを提供します。

```
IUIAnimationManager* GetUIAnimationManager();
```

### <a name="return-value"></a>戻り値

アニメーション マネージャーの作成に失敗した場合は、IUIAnimationManager インターフェイスまたは NULL へのポインター。

### <a name="remarks"></a>解説

現在の OS が Windows アニメーション API をサポートしていない場合、このメソッドは NULL を返し、その後 CAnimationController::IsValid のすべての呼び出しは FALSE を返します。 アニメーション コントローラによってラップされていないインターフェイス メソッドを呼び出すために IUIAnimationManager にアクセスする必要がある場合があります。

## <a name="canimationcontrollergetuianimationtimer"></a><a name="getuianimationtimer"></a>アニメーションコントローラ::ゲットUIアニメーションタイマー

カプセル化された IUIAnimationTimer オブジェクトへのアクセスを提供します。

```
IUIAnimationTimer* GetUIAnimationTimer();
```

### <a name="return-value"></a>戻り値

アニメーション タイマーの作成に失敗した場合は、IUIAnimationTimer インターフェイスまたは NULL へのポインター。

### <a name="remarks"></a>解説

現在の OS が Windows アニメーション API をサポートしていない場合、このメソッドは NULL を返し、その後 CAnimationController::IsValid のすべての呼び出しは FALSE を返します。

## <a name="canimationcontrollergetuitransitionfactory"></a><a name="getuitransitionfactory"></a>を切り替え::取得UIトランジションファクトリー

遷移ライブラリの作成に失敗した場合は、IUIAnimationTransitionFactory インターフェイスまたは NULL へのポインター。

```
IUIAnimationTransitionFactory* GetUITransitionFactory();
```

### <a name="return-value"></a>戻り値

遷移ファクトリの作成に失敗した場合は、IUIAnimationTransitionFactory または NULL へのポインター。

### <a name="remarks"></a>解説

現在の OS が Windows アニメーション API をサポートしていない場合、このメソッドは NULL を返し、その後 CAnimationController::IsValid のすべての呼び出しは FALSE を返します。

## <a name="canimationcontrollergetuitransitionlibrary"></a><a name="getuitransitionlibrary"></a>を切り替え::インターフェイスライブラリ

カプセル化された IUI アニメーショントランジション ライブラリ オブジェクトへのアクセスを提供します。

```
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```

### <a name="return-value"></a>戻り値

遷移ライブラリの作成に失敗した場合は、IUIAnimationトランジションライブラリインターフェイスまたはNULLへのポインタ。

### <a name="remarks"></a>解説

現在の OS が Windows アニメーション API をサポートしていない場合、このメソッドは NULL を返し、その後 CAnimationController::IsValid のすべての呼び出しは FALSE を返します。

## <a name="canimationcontrollerisanimationinprogress"></a><a name="isanimationinprogress"></a>アニメーションコントローラ::イスアニメーションインプログレス

少なくとも 1 つのグループがアニメーションを再生しているかどうかを示します。

```
virtual BOOL IsAnimationInProgress();
```

### <a name="return-value"></a>戻り値

このアニメーション コントローラに進行中のアニメーションがある場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

アニメーション マネージャのステータスをチェックし、ステータスがUI_ANIMATION_MANAGER_BUSY場合は TRUE を返します。

## <a name="canimationcontrollerisvalid"></a><a name="isvalid"></a>Cアニメーションコントローラ::IsValid

アニメーション コントローラが有効かどうかを示します。

```
BOOL IsValid() const;
```

### <a name="return-value"></a>戻り値

アニメーション コントローラが有効な場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

このメソッドは、Windows アニメーション API が現在の OS でサポートされておらず、登録されていないためにアニメーション マネージャーの作成に失敗した場合にのみ、FALSE を返します。 このフラグの設定を行うには、COM ライブラリの初期化後に少なくとも 1 回は GetUIAnimationManager を呼び出す必要があります。

## <a name="canimationcontrollerm_bisvalid"></a><a name="m_bisvalid"></a>m_bIsValid

アニメーション コントローラが有効かどうかを指定します。 現在の OS が Windows アニメーション API をサポートしていない場合、このメンバーは FALSE に設定されます。

```
BOOL m_bIsValid;
```

## <a name="canimationcontrollerm_lstanimationgroups"></a><a name="m_lstanimationgroups"></a>アニメーションコントローラ::m_lstAnimationGroups

このアニメーション コントローラに属するアニメーション グループのリスト。

```
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;
```

## <a name="canimationcontrollerm_panimationmanager"></a><a name="m_panimationmanager"></a>アニメーションコントローラ::m_pAnimationManager

アニメーション マネージャー COM オブジェクトへのポインターを格納します。

```
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;
```

## <a name="canimationcontrollerm_panimationtimer"></a><a name="m_panimationtimer"></a>アニメーションコントローラ::m_pAnimationTimer

アニメーション タイマ COM オブジェクトへのポインターを格納します。

```
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;
```

## <a name="canimationcontrollerm_prelatedwnd"></a><a name="m_prelatedwnd"></a>アニメーションコントローラ::m_pRelatedWnd

アニメーション マネージャーの状態が変更された場合、または更新後イベントが発生したときに自動的に再描画できる、関連する CWnd オブジェクトへのポインター。 NULL にすることができます。

```
CWnd* m_pRelatedWnd;
```

## <a name="canimationcontrollerm_ptransitionfactory"></a><a name="m_ptransitionfactory"></a>コアニメーションコントローラ::m_pTransitionFactory

遷移ファクトリ COM オブジェクトへのポインターを格納します。

```
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;
```

## <a name="canimationcontrollerm_ptransitionlibrary"></a><a name="m_ptransitionlibrary"></a>Cアニメーションコントローラ::m_pTransitionLibrary

遷移ライブラリ COM オブジェクトへのポインターを格納します。

```
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;
```

## <a name="canimationcontrolleronafterschedule"></a><a name="onafterschedule"></a>Cアニメーションコントローラ::アフタースケジュール

指定したグループのアニメーションがスケジュールされているときに、フレームワークによって呼び出されます。

```
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
スケジュールされているアニメーション グループへのポインター。

### <a name="remarks"></a>解説

既定の実装では、指定したグループからキーフレームを削除し、指定したグループに属するアニメーション変数からトランジションを削除します。 アニメーションのスケジュール時に追加のアクションを実行するために、派生クラスでオーバーライドできます。

## <a name="canimationcontrolleronanimationintegervaluechanged"></a><a name="onanimationintegervaluechanged"></a>を変更します。

アニメーション変数の整数値が変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnAnimationIntegerValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    INT32 newValue,
    INT32 prevValue);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
値が変更されたアニメーション オブジェクトを保持するアニメーション グループへのポインター。

*pObject*<br/>
値が変更されたアニメーション変数を含むアニメーション オブジェクトへのポインター。

*変数*<br/>
アニメーション変数へのポインター。

*newValue*<br/>
新しい値を指定します。

*前値*<br/>
前の値を指定します。

### <a name="remarks"></a>解説

このメソッドは、特定のアニメーション変数またはアニメーション オブジェクトに対して呼び出された EnableIntegerValueChangedEvent を使用してアニメーション変数イベントを有効にした場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。

## <a name="canimationcontrolleronanimationmanagerstatuschanged"></a><a name="onanimationmanagerstatuschanged"></a>を変更しました。

アニメーション マネージャーから StatusChanged イベントに応答してフレームワークによって呼び出されます。

```
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```

### <a name="parameters"></a>パラメーター

*newStatus*<br/>
新しいアニメーション マネージャーの状態。

*以前のステータス*<br/>
以前のアニメーション マネージャーの状態。

### <a name="remarks"></a>解説

このメソッドは、アニメーション マネージャー イベントを有効にする場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 既定の実装では、関連するウィンドウが SetRelatedWnd で設定されている場合は、そのウィンドウが更新されます。

## <a name="canimationcontrolleronanimationtimerpostupdate"></a><a name="onanimationtimerpostupdate"></a>Cアニメーションコントローラ::オンアニメーションタイマーポストアップデート

アニメーションの更新が完了した後にフレームワークによって呼び出されます。

```
virtual void OnAnimationTimerPostUpdate();
```

### <a name="remarks"></a>解説

このメソッドは、を使用してタイマー イベント ハンドラーを有効にする場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。

## <a name="canimationcontrolleronanimationtimerpreupdate"></a><a name="onanimationtimerpreupdate"></a>C アニメーションコントローラ::オンアニメーションタイマープレアップデート

アニメーションの更新を開始する前に、フレームワークによって呼び出されます。

```
virtual void OnAnimationTimerPreUpdate();
```

### <a name="remarks"></a>解説

このメソッドは、を使用してタイマー イベント ハンドラーを有効にする場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。

## <a name="canimationcontrolleronanimationtimerrenderingtooslow"></a><a name="onanimationtimerrenderingtooslow"></a>Cアニメーションコントローラ::オンアニメーションタイマーレンダリングスロー

アニメーションのレンダリング フレーム レートが望ましい最小フレーム レートを下回ったときに、フレームワークによって呼び出されます。

```
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```

### <a name="parameters"></a>パラメーター

*Fps*<br/>
現在のフレーム レート (1 秒あたりのフレーム数)。

### <a name="remarks"></a>解説

このメソッドは、を使用してタイマー イベント ハンドラーを有効にする場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 望ましい最小フレーム レートは、IUI アニメーション タイマー::セットフレームレートしきい値を呼び出すことによって指定されます。

## <a name="canimationcontrolleronanimationvaluechanged"></a><a name="onanimationvaluechanged"></a>アニメーションコントローラ::アニメーション値が変更されました

アニメーション変数の値が変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnAnimationValueChanged(
    CAnimationGroup* pGroup,
    CAnimationBaseObject* pObject,
    IUIAnimationVariable* variable,
    DOUBLE newValue,
    DOUBLE prevValue);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
値が変更されたアニメーション オブジェクトを保持するアニメーション グループへのポインター。

*pObject*<br/>
値が変更されたアニメーション変数を含むアニメーション オブジェクトへのポインター。

*変数*<br/>
アニメーション変数へのポインター。

*newValue*<br/>
新しい値を指定します。

*前値*<br/>
前の値を指定します。

### <a name="remarks"></a>解説

このメソッドは、特定のアニメーション変数またはアニメーション オブジェクトに対して呼び出された EnableValueChangedEvent を使用してアニメーション変数イベントを有効にした場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。

## <a name="canimationcontrolleronbeforeanimationstart"></a><a name="onbeforeanimationstart"></a>Cアニメーションコントローラ::オンBeforeアニメーションスタート

アニメーションがスケジュールされる直前にフレームワークによって呼び出されます。

```
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
アニメーションが開始されるアニメーション グループへのポインター。

### <a name="remarks"></a>解説

この呼び出しは関連 CWnd にルーティングされ、指定されたグループのアニメーションが開始される前に追加のアクションを実行するために、派生クラスでオーバーライドできます。

## <a name="canimationcontrolleronhasprioritycancel"></a><a name="onhasprioritycancel"></a>をクリックします。

スケジュールの競合を解決するために、フレームワークによって呼び出されます。

```
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>パラメーター

*グループスケジュール*<br/>
現在スケジュールされているストーリーボードを所有しているグループ。

*新しいグループ*<br/>
pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。

*プライオリティ効果*<br/>
pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。

### <a name="return-value"></a>戻り値

pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_CANCEL を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 [競合管理](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)の詳細については、Windows アニメーション API のドキュメントを参照してください。

## <a name="canimationcontrolleronhasprioritycompress"></a><a name="onhasprioritycompress"></a>Cアニメーションコントローラ::オンハスプライオリティコンプレッサー

スケジュールの競合を解決するために、フレームワークによって呼び出されます。

```
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>パラメーター

*グループスケジュール*<br/>
現在スケジュールされているストーリーボードを所有しているグループ。

*新しいグループ*<br/>
pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。

*プライオリティ効果*<br/>
pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。

### <a name="return-value"></a>戻り値

pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_COMPRESS を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 [競合管理](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)の詳細については、Windows アニメーション API のドキュメントを参照してください。

## <a name="canimationcontrolleronhaspriorityconclude"></a><a name="onhaspriorityconclude"></a>コンティプライズコンティを設定します。

スケジュールの競合を解決するために、フレームワークによって呼び出されます。

```
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>パラメーター

*グループスケジュール*<br/>
現在スケジュールされているストーリーボードを所有しているグループ。

*新しいグループ*<br/>
pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。

*プライオリティ効果*<br/>
pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。

### <a name="return-value"></a>戻り値

pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_CONCLUDE を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 [競合管理](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)の詳細については、Windows アニメーション API のドキュメントを参照してください。

## <a name="canimationcontrolleronhasprioritytrim"></a><a name="onhasprioritytrim"></a>アニメーションコントローラ::オンハスプライオリティトリム

スケジュールの競合を解決するために、フレームワークによって呼び出されます。

```
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```

### <a name="parameters"></a>パラメーター

*グループスケジュール*<br/>
現在スケジュールされているストーリーボードを所有しているグループ。

*新しいグループ*<br/>
pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。

*プライオリティ効果*<br/>
pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。

### <a name="return-value"></a>戻り値

pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_TRIM を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 [競合管理](/windows/win32/api/uianimation/nf-uianimation-iuianimationprioritycomparison-haspriority)の詳細については、Windows アニメーション API のドキュメントを参照してください。

## <a name="canimationcontrolleronstoryboardstatuschanged"></a><a name="onstoryboardstatuschanged"></a>Cアニメーションコントローラ::オンストーリーボードステータス変更

ストーリーボードの状態が変更されたときに、フレームワークによって呼び出されます。

```
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,
    UI_ANIMATION_STORYBOARD_STATUS newStatus,
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
状態が変更されたストーリーボードを所有するアニメーション グループへのポインター。

*newStatus*<br/>
新しいステータスを指定します。

*以前のステータス*<br/>
直前の状態を指定します。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボード イベントを有効にする場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。

## <a name="canimationcontrolleronstoryboardupdated"></a><a name="onstoryboardupdated"></a>Cアニメーションコントローラ::オンストーリーボード更新

ストーリーボードが更新されたときに、フレームワークによって呼び出されます。

```
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```

### <a name="parameters"></a>パラメーター

*グループ化*<br/>
ストーリーボードを所有するグループへのポインター。

### <a name="remarks"></a>解説

このメソッドは、ストーリーボード イベントを有効にする場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。

## <a name="canimationcontrollerremoveallanimationgroups"></a><a name="removeallanimationgroups"></a>をグループ化する

アニメーション コントローラからすべてのアニメーション グループを削除します。

```
void RemoveAllAnimationGroups();
```

### <a name="remarks"></a>解説

すべてのグループは削除され、アプリケーション レベルで保存されている場合は、そのグループのポインターを無効にする必要があります。 削除されるグループの CAnimationGroup::m_bAutodestroyAnimationObjects が TRUE の場合、そのグループに属するすべてのアニメーション オブジェクトが削除されます。それ以外の場合は、親アニメーション コントローラへの参照が NULL に設定され、別のコントローラに追加できます。

## <a name="canimationcontrollerremoveanimationgroup"></a><a name="removeanimationgroup"></a>アニメーショングループを削除します。

指定した ID のアニメーション グループをアニメーション コントローラから削除します。

```
void RemoveAnimationGroup(UINT32 nGroupID);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
アニメーション グループ ID を指定します。

### <a name="remarks"></a>解説

このメソッドは、グループの内部リストからアニメーション グループを削除して削除します。 CAnimationGroup::m_bAutodestroyAnimationObjects が TRUE の場合、そのグループに属するすべてのアニメーション オブジェクトが削除されます。それ以外の場合は、親アニメーション コントローラへの参照が NULL に設定され、別のコントローラに追加できます。

## <a name="canimationcontrollerremoveanimationobject"></a><a name="removeanimationobject"></a>アニメーションコントローラ::アニメーションオブジェクトの削除

アニメーション コントローラからアニメーション オブジェクトを削除します。

```
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,
    BOOL bNoDelete = FALSE);
```

### <a name="parameters"></a>パラメーター

*pObject*<br/>
アニメーション オブジェクトへのポインター。

*bNo削除*<br/>
このパラメーターが TRUE の場合、オブジェクトは削除時に削除されません。

### <a name="remarks"></a>解説

アニメーション コントローラおよびアニメーション グループからアニメーション オブジェクトを削除します。 特定のオブジェクトをアニメーション化しない場合、またはオブジェクトを別のアニメーション コントローラに移動する必要がある場合は、この関数を呼び出します。 最後のケースでは、bNoDelete は TRUE でなければなりません。

## <a name="canimationcontrollerremovetransitions"></a><a name="removetransitions"></a>Cアニメーションコントローラ::トランジションの削除

指定したグループに属するアニメーション オブジェクトから遷移を削除します。

```
void RemoveTransitions(UINT32 nGroupID);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
グループ ID を指定します。

### <a name="remarks"></a>解説

グループは、アニメーション オブジェクトをループし、各アニメーション オブジェクトに対して ClearTransitions(FALSE) を呼び出します。 このメソッドは、アニメーションがスケジュールされた後にフレームワークによって呼び出されます。

## <a name="canimationcontrollerschedulegroup"></a><a name="schedulegroup"></a>Cアニメーションコントローラ::スケジュールグループ

アニメーションをスケジュールします。

```
BOOL ScheduleGroup(
    UINT32 nGroupID,
    UI_ANIMATION_SECONDS time = 0.0);
```

### <a name="parameters"></a>パラメーター

*グループ ID*<br/>
スケジュールするアニメーション グループ ID を指定します。

*time*<br/>
スケジュールする時間を指定します。

### <a name="return-value"></a>戻り値

アニメーションが正常にスケジュールされた場合は TRUE。 ストーリーボードが作成されていない場合、または他のエラーが発生した場合は FALSE。

### <a name="remarks"></a>解説

パラメータ bScheduleNow を FALSE 前のスケジュールグループに設定して、アニメーショングループを呼び出す必要があります。 IUI アニメーションタイマー::GetTime から取得した目的のアニメーション時間を指定できます。 time パラメータが 0.0 の場合、アニメーションは現在の時刻に対してスケジュールされます。

## <a name="canimationcontrollersetrelatedwnd"></a><a name="setrelatedwnd"></a>Cアニメーションコントローラ::セット関連ウンド

アニメーション コントローラとウィンドウの関係を確立します。

```
void SetRelatedWnd(CWnd* pWnd);
```

### <a name="parameters"></a>パラメーター

*Pwnd*<br/>
設定するウィンドウ オブジェクトへのポインター。

### <a name="remarks"></a>解説

関連する CWnd オブジェクトが設定されている場合、アニメーション マネージャのステータスが変更された場合や、更新後のタイマーが発生したときに、アニメーション コントローラは自動的に更新 (メッセージWM_PAINT送信) できます。

## <a name="canimationcontrollerupdateanimationmanager"></a><a name="updateanimationmanager"></a>アニメーションマネージャー::アニメーションマネージャー

アニメーションマネージャーに、すべてのアニメーション変数の値を更新するように指示します。

```
virtual void UpdateAnimationManager();
```

### <a name="remarks"></a>解説

このメソッドを呼び出すと、アニメーション マネージャーは現在の時刻に進み、必要に応じてストーリーボードのステータスが変更され、アニメーション変数が適切な補間値に更新されます。 内部的には、このメソッドは、IUIアニメーションタイマーを呼び出します::GetTime(現在)とIUIアニメーションマネージャー::アップデート(タイムナウ)。 この動作をカスタマイズするには、派生クラスでこのメソッドをオーバーライドします。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
