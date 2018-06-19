---
title: CAnimationController クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ec93c2d39206bbc0c3076835f55e624d3eef715
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33356925"
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
|[CAnimationController::CAnimationController](#canimationcontroller)|アニメーションのコント ローラーを構築します。|  
|[CAnimationController:: ~ CAnimationController](#canimationcontroller__~canimationcontroller)|デストラクターです。 アニメーション コント ローラー オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationController::AddAnimationObject](#addanimationobject)|アニメーション オブジェクトをアニメーション コント ローラーが属しているグループに追加します。|  
|[CAnimationController::AddKeyframeToGroup](#addkeyframetogroup)|キーフレームをグループに追加されます。|  
|[CAnimationController::AnimateGroup](#animategroup)|アニメーションを実行するグループを準備し、必要に応じてスケジュールを設定します。|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|オーバーロードされます。 アニメーションがスケジュールされているときに、グループをクリーンアップするためにフレームワークによって呼び出されます。|  
|[CAnimationController::CreateKeyframe](#createkeyframe)|オーバーロードされます。 遷移に依存するキーフレームを作成し、指定したグループに追加します。|  
|[CAnimationController::EnableAnimationManagerEvent](#enableanimationmanagerevent)|アニメーション マネージャーのステータスが変わったときに呼び出すハンドラーの解放または設定します。|  
|[CAnimationController::EnableAnimationTimerEventHandler](#enableanimationtimereventhandler)|タイミング イベントのハンドラーと更新のタイミングのハンドラーを解放または設定します。|  
|[Canimationcontroller::enableprioritycomparisonhandler](#enableprioritycomparisonhandler)|解放するかどうかスケジュールされたストーリー ボード取り消された、という結論に達しました、トリミングしたり圧縮を調べます優先度比較ハンドラーまたは設定します。|  
|[CAnimationController::EnableStoryboardEventHandler](#enablestoryboardeventhandler)|設定またはストーリー ボードの状態と更新プログラムのイベントのハンドラーを解放します。|  
|[CAnimationController::FindAnimationGroup](#findanimationgroup)|オーバーロードされます。 そのストーリー ボードを使用してアニメーション グループを検索します。|  
|[CAnimationController::FindAnimationObject](#findanimationobject)|指定したアニメーションの変数を持つアニメーション オブジェクトを検索します。|  
|[CAnimationController::GetKeyframeStoryboardStart](#getkeyframestoryboardstart)|ストーリー ボードの開始を識別するキーフレームを返します。|  
|[CAnimationController::GetUIAnimationManager](#getuianimationmanager)|カプセル化された IUIAnimationManager オブジェクトへのアクセスを提供します。|  
|[CAnimationController::GetUIAnimationTimer](#getuianimationtimer)|カプセル化された IUIAnimationTimer オブジェクトへのアクセスを提供します。|  
|[CAnimationController::GetUITransitionFactory](#getuitransitionfactory)|IUIAnimationTransitionFactory インターフェイスまたは遷移ライブラリの作成に失敗した場合は NULL へのポインター。|  
|[CAnimationController::GetUITransitionLibrary](#getuitransitionlibrary)|カプセル化された IUIAnimationTransitionLibrary オブジェクトへのアクセスを提供します。|  
|[CAnimationController::IsAnimationInProgress](#isanimationinprogress)|少なくとも 1 つのグループがアニメーションを再生しているかどうかを指示します。|  
|[CAnimationController::IsValid](#isvalid)|アニメーション コント ローラーが有効かどうかを指示します。|  
|[CAnimationController::OnAnimationIntegerValueChanged](#onanimationintegervaluechanged)|アニメーション変数の整数値が変更されたときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationManagerStatusChanged](#onanimationmanagerstatuschanged)|アニメーション マネージャーからメイル イベントに応答フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationTimerPostUpdate](#onanimationtimerpostupdate)|アニメーションの更新プログラムの完了後に、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationTimerPreUpdate](#onanimationtimerpreupdate)|アニメーションの更新プログラムの開始前に、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](#onanimationtimerrenderingtooslow)|アニメーションのレンダリングのフレーム レートが最低限の適切なフレーム レートを下回った場合に、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationValueChanged](#onanimationvaluechanged)|アニメーション変数の値が変更されたときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnBeforeAnimationStart](#onbeforeanimationstart)|フレームワークによって呼び出されます、右、アニメーションをスケジュールする前にします。|  
|[CAnimationController::OnHasPriorityCancel](#onhasprioritycancel)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityCompress](#onhasprioritycompress)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityConclude](#onhaspriorityconclude)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityTrim](#onhasprioritytrim)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnStoryboardStatusChanged](#onstoryboardstatuschanged)|ストーリー ボードの状態が変更されたときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnStoryboardUpdated](#onstoryboardupdated)|ストーリー ボードが更新されたときに、フレームワークによって呼び出されます。|  
|[CAnimationController::RemoveAllAnimationGroups](#removeallanimationgroups)|アニメーションのすべてのグループは、アニメーション コント ローラーから削除します。|  
|[CAnimationController::RemoveAnimationGroup](#removeanimationgroup)|アニメーション コント ローラーから、指定した ID を持つ、アニメーション グループを削除します。|  
|[CAnimationController::RemoveAnimationObject](#removeanimationobject)|アニメーション オブジェクトは、アニメーション コント ローラーから削除します。|  
|[CAnimationController::RemoveTransitions](#removetransitions)|指定されたグループに属するアニメーション オブジェクトから遷移を削除します。|  
|[CAnimationController::ScheduleGroup](#schedulegroup)|アニメーションをスケジュールします。|  
|[CAnimationController::SetRelatedWnd](#setrelatedwnd)|アニメーション コント ローラーと、ウィンドウ間のリレーションシップを確立します。|  
|[CAnimationController::UpdateAnimationManager](#updateanimationmanager)|アニメーション マネージャーのすべてのアニメーション変数の値を更新するように指示します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationController::CleanUpGroup](#cleanupgroup)|オーバーロードされます。 グループをクリーンアップするためのヘルパーです。|  
|[CAnimationController::OnAfterSchedule](#onafterschedule)|指定されたグループのアニメーションがスケジュールされているだけときに、フレームワークによって呼び出されます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationController::gkeyframeStoryboardStart](#g_keyframestoryboardstart)|ストーリー ボードの開始を表すキーフレームです。|  
|[CAnimationController::m_bIsValid](#m_bisvalid)|アニメーションのコント ローラーが有効かどうかどうかを指定します。 現在の OS では、Windows Animation API をサポートしていない場合、このメンバーは FALSE に設定します。|  
|[CAnimationController::m_lstAnimationGroups](#m_lstanimationgroups)|このアニメーション コント ローラーに属するアニメーション グループの一覧。|  
|[CAnimationController::m_pAnimationManager](#m_panimationmanager)|アニメーション マネージャーの COM オブジェクトへのポインターを格納します。|  
|[CAnimationController::m_pAnimationTimer](#m_panimationtimer)|アニメーションのタイマーの COM オブジェクトへのポインターを格納します。|  
|[CAnimationController::m_pRelatedWnd](#m_prelatedwnd)|アニメーション マネージャーの状態が変更された、または post 更新イベントが発生したときに自動的に描画できる関連の CWnd オブジェクトへのポインター。 NULL にすることができます。|  
|[CAnimationController::m_pTransitionFactory](#m_ptransitionfactory)|遷移工場出荷時の COM オブジェクトへのポインターを格納します。|  
|[CAnimationController::m_pTransitionLibrary](#m_ptransitionlibrary)|遷移ライブラリ COM オブジェクトへのポインターを格納します。|  
  
## <a name="remarks"></a>コメント  
 CAnimationController クラスは、アニメーションを管理するキー クラスです。 アプリケーションに、アニメーション コント ローラーの 1 つまたは複数のインスタンスを作成して、CAnimationController::SetRelatedWnd を使用して CWnd オブジェクトに必要に応じて、アニメーション コント ローラーのインスタンスを接続します。 アニメーション マネージャーの状態が変更されたか、アニメーションのタイマーが更新されたときに関連するウィンドウへ WM_PAINT メッセージを自動的に送信するには、この接続が必要です。 この関係を有効にしない場合、手動でアニメーションを表示するウィンドウが再描画が必要です。 この目的で CAnimationController からクラスを派生し、OnAnimationManagerStatusChanged や OnAnimationTimerPostUpdate をオーバーライドして必要な場合に、1 つまたは複数の windows を無効にできます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationController`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationcontroller"></a>  CAnimationController:: ~ CAnimationController  
 デストラクターです。 アニメーション コント ローラー オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CAnimationController(void);
```   
  
##  <a name="addanimationobject"></a>  CAnimationController::AddAnimationObject  
 アニメーション オブジェクトをアニメーション コント ローラーが属しているグループに追加します。  
  
```  
CAnimationGroup* AddAnimationObject(CAnimationBaseObject* pObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pObject`  
 アニメーション オブジェクトへのポインター。  
  
### <a name="return-value"></a>戻り値  
 PObject が追加されている関数が成功した場合、既存または新規のアニメーション グループへのポインターPObject は既に別のアニメーション コント ローラーに属しているグループに追加されている場合は NULL です。  
  
### <a name="remarks"></a>コメント  
 アニメーション オブジェクト、アニメーション コント ローラーを追加するのには、このメソッドを呼び出します。 オブジェクトは、オブジェクトの GroupID に従って、グループに追加されます (CAnimationBaseObject::SetID を参照してください)。 指定された GroupID を追加する最初のオブジェクトの場合は、アニメーション コント ローラーは新しいグループを作成します。 アニメーション オブジェクトは、1 つのアニメーション コント ローラーのみを追加できます。 別のコント ローラーにオブジェクトを追加する必要がある場合は、まず RemoveAnimationObject を呼び出します。 オブジェクトが、以前のグループから削除し、指定した ID を持つ別のグループに追加されたグループに既に追加されているオブジェクトの新しい GroupID で SetID を呼び出した場合  
  
##  <a name="addkeyframetogroup"></a>  CAnimationController::AddKeyframeToGroup  
 キーフレームをグループに追加されます。  
  
```  
BOOL AddKeyframeToGroup(
    UINT32 nGroupID,  
    CBaseKeyFrame* pKeyframe);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 グループ ID を指定します  
  
 `pKeyframe`  
 キーフレームへのポインター。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 通常を作成およびグループに自動的に作成されたキーフレームを追加する、このメソッドを呼び出して、CAnimationController::CreateKeyframe を代わりに、使用する必要ありません。  
  
##  <a name="animategroup"></a>  CAnimationController::AnimateGroup  
 アニメーションを実行するグループを準備し、必要に応じてスケジュールを設定します。  
  
```  
BOOL AnimateGroup(
    UINT32 nGroupID,  
    BOOL bScheduleNow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 GroupID を指定します。  
  
 `bScheduleNow`  
 すぐにアニメーションを実行するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 アニメーションが正常にスケジュールして実行する場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ストーリー ボードを作成する、アニメーション変数の追加、切り替え効果を適用すること、およびキーフレームを設定は、実際の作業を行います。 BScheduleNow を FALSE に設定した場合にスケジュールを遅延することができます。 ここでは、指定されたグループには、アニメーションに設定されているストーリー ボードは保持されます。 その時点で、ストーリー ボードとアニメーション変数のイベントをセットアップできます。 ときに実際には、CAnimationController::ScheduleGroup アニメーションの呼び出しを実行する必要があります。  
  
##  <a name="canimationcontroller"></a>  CAnimationController::CAnimationController  
 アニメーションのコント ローラーを構築します。  
  
```  
CAnimationController(void);
```   
  
##  <a name="cleanupgroup"></a>  CAnimationController::CleanUpGroup  
 アニメーションがスケジュールされているときに、グループをクリーンアップするためにフレームワークによって呼び出されます。  
  
```  
void CleanUpGroup(UINT32 nGroupID);  
void CleanUpGroup(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 GroupID を指定します。  
  
 `pGroup`  
 クリーンアップするのにはアニメーション グループへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドすべての遷移とキーフレームから削除、指定されたグループではないため関連後、アニメーションがスケジュールされました。  
  
##  <a name="createkeyframe"></a>  CAnimationController::CreateKeyframe  
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
 `nGroupID`  
 キーフレームを作成する対象グループの ID を指定します。  
  
 `pTransition`  
 遷移へのポインター。 この移行の完了後に、ストーリーボードにキーフレームが挿入されます。  
  
 `pKeyframe`  
 このキーフレームの基準キーフレームへのポインター。  
  
 `offset`  
 pKeyframe で指定した基準キーフレームからのオフセット (秒単位)。  
  
### <a name="return-value"></a>戻り値  
 関数が正常に終了した場合は、新しく作成されたキーフレームへのポインター。  
  
### <a name="remarks"></a>コメント  
 返されたポインターを格納して、新しく作成されたキーフレームを他のキーフレームの基準にすることができます (2 番目のオーバーロードを参照)。 キーフレームで遷移を開始することもできます。CBaseTransition::SetKeyframes をご覧ください。 このようにして作成したキーフレームを削除する必要はありません。アニメーション グループによって自動的に削除されます。 キーフレームを他のキーフレームや遷移に基づいて作成する場合は注意し、循環参照が発生しないようにしてください。  
  
##  <a name="enableanimationmanagerevent"></a>  CAnimationController::EnableAnimationManagerEvent  
 アニメーション マネージャーのステータスが変わったときに呼び出すハンドラーの解放または設定します。  
  
```  
virtual BOOL EnableAnimationManagerEvent(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 設定またはのハンドラーを解除するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 ハンドラーが正常に設定またはリリースされた場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 ハンドラーを (有効) に設定されている場合、Windows Animation は、アニメーション マネージャーの状態が変更されたときに、OnAnimationManagerStatusChanged を呼び出します。  
  
##  <a name="enableanimationtimereventhandler"></a>  CAnimationController::EnableAnimationTimerEventHandler  
 タイミング イベントのハンドラーと更新のタイミングのハンドラーを解放または設定します。  
  
```  
virtual BOOL EnableAnimationTimerEventHandler(
    BOOL bEnable = TRUE,  
    UI_ANIMATION_IDLE_BEHAVIOR idleBehavior = UI_ANIMATION_IDLE_BEHAVIOR_DISABLE);
```  
  
### <a name="parameters"></a>パラメーター  
 `bEnable`  
 設定またはハンドラーを解除するかどうかを指定します。  
  
 `idleBehavior`  
 更新ハンドラーのタイマーのアイドル動作を指定します。  
  
### <a name="return-value"></a>戻り値  
 ハンドラーの設定またはリリース; が正常にある場合は TRUE。FALSE の場合は、このメソッドは、2 回目のハンドラーは、最初に、ボタンを押したまままたはその他のエラーが発生します。  
  
### <a name="remarks"></a>コメント  
 ハンドラーは、設定されている場合 (有効) の Windows Animation API 呼び出し OnAnimationTimerPreUpdate、OnAnimationTimerPostUpdate、OnRenderingTooSlow メソッドです。 Windows Animation API の更新のストーリー ボードを可能にするアニメーション タイマーを有効にする必要があります。 それ以外の場合にすべてのアニメーション変数の値を更新するマネージャー アニメーションを指示するために CAnimationController::UpdateAnimationManager を呼び出す必要があります。  
  
##  <a name="enableprioritycomparisonhandler"></a>  Canimationcontroller::enableprioritycomparisonhandler  
 解放するかどうかスケジュールされたストーリー ボード取り消された、という結論に達しました、トリミングしたり圧縮を調べます優先度比較ハンドラーまたは設定します。  
  
```  
virtual BOOL EnablePriorityComparisonHandler(DWORD dwHandlerType);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwHandlerType`  
 UI_ANIMATION_PHT_ の組み合わせにフラグを設定または解除するには、どのようなハンドラーを指定する (「解説」を参照してください)。  
  
### <a name="return-value"></a>戻り値  
 ハンドラーが正常に設定またはリリースされた場合は TRUE。  
  
### <a name="remarks"></a>コメント  
 Windows Animation が dwHandlerType に応じて次の仮想メソッドを呼び出してハンドラーを (有効) に設定されている場合: OnHasPriorityCancel、OnHasPriorityConclude、OnHasPriorityTrim、OnHasPriorityCompress です。 dwHandler は、次のフラグの組み合わせを指定できます: UI_ANIMATION_PHT_NONE - リリース UI_ANIMATION_PHT_CANCEL - すべてのハンドラーは、[キャンセル] を設定比較ハンドラー UI_ANIMATION_PHT_CONCLUDE - 設定完結比較ハンドラー UI_ANIMATION_PHT_COMPRESS - 設定圧縮する比較ハンドラー UI_ANIMATION_PHT_TRIM - トリム比較ハンドラー UI_ANIMATION_PHT_CANCEL_REMOVE 設定 - [キャンセル] 比較ハンドラー UI_ANIMATION_PHT_CONCLUDE_REMOVE の削除 - 完結比較ハンドラー UI_ANIMATION_PHT_COMPRESS_ の削除します。削除 - 圧縮比較ハンドラー UI_ANIMATION_PHT_TRIM_REMOVE - 削除トリム比較ハンドラーを削除  
  
##  <a name="enablestoryboardeventhandler"></a>  CAnimationController::EnableStoryboardEventHandler  
 設定またはストーリー ボードの状態と更新プログラムのイベントのハンドラーを解放します。  
  
```  
virtual BOOL EnableStoryboardEventHandler(
    UINT32 nGroupID,  
    BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 グループ ID を指定します  
  
 `bEnable`  
 設定またはのハンドラーを解除するかどうかを指定します。  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、ハンドラーが正常に設定またはリリースです。指定したアニメーション グループがあるようになりましたまたは指定されたグループのアニメーションが開始されていないと、内部のストーリー ボードが NULL の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 ハンドラーが設定されている場合 (有効) Windows Animation API は OnStoryboardStatusChanges と OnStoryboardUpdated の仮想メソッドを呼び出します。 ハンドラー設定しなければなりません CAnimationController::Animate を呼び出した後は、指定したアニメーション グループをカプセル化された IUIAnimationStoryboard オブジェクトを作成するため。  
  
##  <a name="findanimationgroup"></a>  CAnimationController::FindAnimationGroup  
 検索、アニメーション グループによってそのグループ id です。  
  
```  
CAnimationGroup* FindAnimationGroup(UINT32 nGroupID);  
CAnimationGroup* FindAnimationGroup(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 GroupID を指定します。  
  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
### <a name="return-value"></a>戻り値  
 アニメーション グループまたは指定した ID を持つグループが見つからない場合は NULL へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、実行時に、アニメーション グループを検索できます。 グループが作成され、特定 GroupID で最初のアニメーション オブジェクトがアニメーション コント ローラーに追加されるときにアニメーション グループの内部リストに追加します。  
  
##  <a name="findanimationobject"></a>  CAnimationController::FindAnimationObject  
 指定したアニメーションの変数を持つアニメーション オブジェクトを検索します。  
  
```  
BOOL FindAnimationObject(
    IUIAnimationVariable* pVariable,  
    CAnimationBaseObject** ppObject,  
    CAnimationGroup** ppGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `pVariable`  
 アニメーション変数へのポインター。  
  
 `ppObject`  
 出力です。 アニメーション オブジェクトまたは NULL へのポインターが含まれています。  
  
 `ppGroup`  
 出力です。 アニメーション オブジェクト、または NULL を保持するアニメーション グループへのポインターが含まれています。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが見つかった場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 入力方向のアニメーション変数からのアニメーション オブジェクトを見つけることが必要なときに、イベント ハンドラーから呼び出されます。  
  
##  <a name="g_keyframestoryboardstart"></a>  CAnimationController::gkeyframeStoryboardStart  
 ストーリー ボードの開始を表すキーフレームです。  
  
```  
static CBaseKeyFrame gkeyframeStoryboardStart;  
```  
  
##  <a name="getkeyframestoryboardstart"></a>  CAnimationController::GetKeyframeStoryboardStart  
 ストーリー ボードの開始を識別するキーフレームを返します。  
  
```  
static CBaseKeyFrame* GetKeyframeStoryboardStart();
```  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボードの開始を識別する、基準キーフレームへのポインター。  
  
### <a name="remarks"></a>コメント  
 このキーフレームを基に、他のキーフレームや遷移ストーリー ボードが開始された時刻の時点を取得します。  
  
##  <a name="getuianimationmanager"></a>  CAnimationController::GetUIAnimationManager  
 カプセル化された IUIAnimationManager オブジェクトへのアクセスを提供します。  
  
```  
IUIAnimationManager* GetUIAnimationManager();
```  
  
### <a name="return-value"></a>戻り値  
 アニメーション マネージャーの作成に失敗する場合は NULL IUIAnimationManager インターフェイスへのポインター。  
  
### <a name="remarks"></a>コメント  
 現在の OS が Windows Animation API をサポートしていない場合は、このメソッドは NULL を返し、その後、CAnimationController::IsValid 上のすべての後続の呼び出しでは FALSE を返します。 します。 アニメーション コント ローラーによってラップされていない、そのインターフェイス メソッドを呼び出すために IUIAnimationManager にアクセスする必要があります。  
  
##  <a name="getuianimationtimer"></a>  CAnimationController::GetUIAnimationTimer  
 カプセル化された IUIAnimationTimer オブジェクトへのアクセスを提供します。  
  
```  
IUIAnimationTimer* GetUIAnimationTimer();
```  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationTimer インターフェイスまたはアニメーション タイマーの作成に失敗した場合は NULL へのポインター。  
  
### <a name="remarks"></a>コメント  
 現在の OS が Windows Animation API をサポートしていない場合は、このメソッドは NULL を返し、その後、CAnimationController::IsValid 上のすべての後続の呼び出しでは FALSE を返します。 します。  
  
##  <a name="getuitransitionfactory"></a>  CAnimationController::GetUITransitionFactory  
 IUIAnimationTransitionFactory インターフェイスまたは遷移ライブラリの作成に失敗した場合は NULL へのポインター。  
  
```  
IUIAnimationTransitionFactory* GetUITransitionFactory();
```  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationTransitionFactory または遷移ファクトリの作成に失敗した場合は NULL へのポインター。  
  
### <a name="remarks"></a>コメント  
 現在の OS が Windows Animation API をサポートしていない場合は、このメソッドは NULL を返し、その後、CAnimationController::IsValid 上のすべての後続の呼び出しでは FALSE を返します。 します。  
  
##  <a name="getuitransitionlibrary"></a>  CAnimationController::GetUITransitionLibrary  
 カプセル化された IUIAnimationTransitionLibrary オブジェクトへのアクセスを提供します。  
  
```  
IUIAnimationTransitionLibrary* GetUITransitionLibrary();
```  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationTransitionLibrary インターフェイスまたは遷移ライブラリの作成に失敗した場合は NULL へのポインター。  
  
### <a name="remarks"></a>コメント  
 現在の OS が Windows Animation API をサポートしていない場合は、このメソッドは NULL を返し、その後、CAnimationController::IsValid 上のすべての後続の呼び出しでは FALSE を返します。 します。  
  
##  <a name="isanimationinprogress"></a>  CAnimationController::IsAnimationInProgress  
 少なくとも 1 つのグループがアニメーションを再生しているかどうかを指示します。  
  
```  
virtual BOOL IsAnimationInProgress();
```  
  
### <a name="return-value"></a>戻り値  
 このアニメーション コント ローラーに対して進行中のアニメーションがある場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 アニメーション マネージャーのステータスを確認し、状態が UI_ANIMATION_MANAGER_BUSY 場合に TRUE を返します。  
  
##  <a name="isvalid"></a>  CAnimationController::IsValid  
 アニメーション コント ローラーが有効かどうかを指示します。  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、アニメーション コント ローラーが無効です。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、Windows Animation API は、現在の OS とアニメーション マネージャーの作成ではサポートされていない場合にのみ、FALSE を返します。 は、登録されていないために失敗しました。 このフラグの設定が発生する COM ライブラリの初期化後に 1 回以上 GetUIAnimationManager を呼び出す必要があります。  
  
##  <a name="m_bisvalid"></a>  CAnimationController::m_bIsValid  
 アニメーションのコント ローラーが有効かどうかどうかを指定します。 現在の OS では、Windows Animation API をサポートしていない場合、このメンバーは FALSE に設定します。  
  
```  
BOOL m_bIsValid;  
```  
  
##  <a name="m_lstanimationgroups"></a>  CAnimationController::m_lstAnimationGroups  
 このアニメーション コント ローラーに属するアニメーション グループの一覧。  
  
```  
CList<CAnimationGroup*, CAnimationGroup*> m_lstAnimationGroups;  
```  
  
##  <a name="m_panimationmanager"></a>  CAnimationController::m_pAnimationManager  
 アニメーション マネージャーの COM オブジェクトへのポインターを格納します。  
  
```  
ATL::CComPtr<IUIAnimationManager> m_pAnimationManager;  
```  
  
##  <a name="m_panimationtimer"></a>  CAnimationController::m_pAnimationTimer  
 アニメーションのタイマーの COM オブジェクトへのポインターを格納します。  
  
```  
ATL::CComPtr<IUIAnimationTimer> m_pAnimationTimer;  
```  
  
##  <a name="m_prelatedwnd"></a>  CAnimationController::m_pRelatedWnd  
 アニメーション マネージャーの状態が変更された、または post 更新イベントが発生したときに自動的に描画できる関連の CWnd オブジェクトへのポインター。 NULL にすることができます。  
  
```  
CWnd* m_pRelatedWnd;  
```  
  
##  <a name="m_ptransitionfactory"></a>  CAnimationController::m_pTransitionFactory  
 遷移工場出荷時の COM オブジェクトへのポインターを格納します。  
  
```  
ATL::CComPtr<IUIAnimationTransitionFactory> m_pTransitionFactory;  
```  
  
##  <a name="m_ptransitionlibrary"></a>  CAnimationController::m_pTransitionLibrary  
 遷移ライブラリ COM オブジェクトへのポインターを格納します。  
  
```  
ATL::CComPtr<IUIAnimationTransitionLibrary> m_pTransitionLibrary;  
```  
  
##  <a name="onafterschedule"></a>  CAnimationController::OnAfterSchedule  
 指定されたグループのアニメーションがスケジュールされているだけときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnAfterSchedule(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroup`  
 スケジュールされているアニメーション グループへのポインター。  
  
### <a name="remarks"></a>コメント  
 既定の実装では、キーフレームを指定されたグループから削除し、指定されたグループに属するアニメーション変数から遷移します。 アニメーションのスケジュール時に追加のアクションを実行する派生クラスでオーバーライドできます。  
  
##  <a name="onanimationintegervaluechanged"></a>  CAnimationController::OnAnimationIntegerValueChanged  
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
 `pGroup`  
 値を持つアニメーション オブジェクトを保持するアニメーション グループへのポインターが変更されました。  
  
 `pObject`  
 値が変更されたアニメーション変数を格納しているアニメーション オブジェクトへのポインター。  
  
 `variable`  
 アニメーション変数へのポインター。  
  
 `newValue`  
 新しい値を指定します。  
  
 `prevValue`  
 前の値を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、特定のアニメーションの変数またはアニメーション オブジェクトと呼ばれる EnableIntegerValueChangedEvent でアニメーション変数のイベントを有効にした場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。  
  
##  <a name="onanimationmanagerstatuschanged"></a>  CAnimationController::OnAnimationManagerStatusChanged  
 アニメーション マネージャーからメイル イベントに応答フレームワークによって呼び出されます。  
  
```  
virtual void OnAnimationManagerStatusChanged(
    UI_ANIMATION_MANAGER_STATUS newStatus,  
    UI_ANIMATION_MANAGER_STATUS previousStatus);
```  
  
### <a name="parameters"></a>パラメーター  
 `newStatus`  
 新しいアニメーション マネージャーの状態です。  
  
 `previousStatus`  
 以前のアニメーション マネージャーの状態です。  
  
### <a name="remarks"></a>コメント  
 アニメーション マネージャー イベント EnableAnimationManagerEvent を有効にした場合は、このメソッドが呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 SetRelatedWnd に設定されている場合、既定の実装は、関連するウィンドウを更新します。  
  
##  <a name="onanimationtimerpostupdate"></a>  CAnimationController::OnAnimationTimerPostUpdate  
 アニメーションの更新プログラムの完了後に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAnimationTimerPostUpdate();
```  
  
### <a name="remarks"></a>コメント  
 EnableAnimationTimerEventHandler を使用して、タイマー イベント ハンドラーを有効にした場合は、このメソッドが呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。  
  
##  <a name="onanimationtimerpreupdate"></a>  CAnimationController::OnAnimationTimerPreUpdate  
 アニメーションの更新プログラムの開始前に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAnimationTimerPreUpdate();
```  
  
### <a name="remarks"></a>コメント  
 EnableAnimationTimerEventHandler を使用して、タイマー イベント ハンドラーを有効にした場合は、このメソッドが呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。  
  
##  <a name="onanimationtimerrenderingtooslow"></a>  CAnimationController::OnAnimationTimerRenderingTooSlow  
 アニメーションのレンダリングのフレーム レートが最低限の適切なフレーム レートを下回った場合に、フレームワークによって呼び出されます。  
  
```  
virtual void OnAnimationTimerRenderingTooSlow(UINT32 fps);
```  
  
### <a name="parameters"></a>パラメーター  
 `fps`  
 1 秒あたりのフレームで現在のフレーム レートです。  
  
### <a name="remarks"></a>コメント  
 EnableAnimationTimerEventHandler を使用して、タイマー イベント ハンドラーを有効にした場合は、このメソッドが呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 最小の適切なフレーム レートは、IUIAnimationTimer::SetFrameRateThreshold を呼び出すことによって指定されます。  
  
##  <a name="onanimationvaluechanged"></a>  CAnimationController::OnAnimationValueChanged  
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
 `pGroup`  
 値を持つアニメーション オブジェクトを保持するアニメーション グループへのポインターが変更されました。  
  
 `pObject`  
 値が変更されたアニメーション変数を格納しているアニメーション オブジェクトへのポインター。  
  
 `variable`  
 アニメーション変数へのポインター。  
  
 `newValue`  
 新しい値を指定します。  
  
 `prevValue`  
 前の値を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、特定のアニメーションの変数またはアニメーション オブジェクトと呼ばれる EnableValueChangedEvent でアニメーション変数のイベントを有効にした場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。  
  
##  <a name="onbeforeanimationstart"></a>  CAnimationController::OnBeforeAnimationStart  
 フレームワークによって呼び出されます、右、アニメーションをスケジュールする前にします。  
  
```  
virtual void OnBeforeAnimationStart(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroup`  
 アニメーションが開始されようアニメーション グループへのポインター。  
  
### <a name="remarks"></a>コメント  
 この呼び出しを使用して、関連 CWnd にルーティングされ、指定されたグループのアニメーションの開始前に付加的な処理を実行する派生クラスでオーバーライドされることができます。  
  
##  <a name="onhasprioritycancel"></a>  CAnimationController::OnHasPriorityCancel  
 スケジュールの競合を解決するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnHasPriorityCancel(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroupScheduled`  
 現在スケジュールされているストーリーボードを所有しているグループ。  
  
 `pGroupNew`  
 pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。  
  
 `priorityEffect`  
 pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。  
  
### <a name="return-value"></a>戻り値  
 pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_CANCEL を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 競合の管理の詳細については、Windows Animation API ドキュメント (http://msdn.microsoft.com/library/dd371759(VS.85).aspx)です。  
  
##  <a name="onhasprioritycompress"></a>  CAnimationController::OnHasPriorityCompress  
 スケジュールの競合を解決するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnHasPriorityCompress(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroupScheduled`  
 現在スケジュールされているストーリーボードを所有しているグループ。  
  
 `pGroupNew`  
 pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。  
  
 `priorityEffect`  
 pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。  
  
### <a name="return-value"></a>戻り値  
 pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_COMPRESS を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 競合の管理の詳細については、Windows Animation API ドキュメント (http://msdn.microsoft.com/library/dd371759(VS.85).aspx)です。  
  
##  <a name="onhaspriorityconclude"></a>  CAnimationController::OnHasPriorityConclude  
 スケジュールの競合を解決するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnHasPriorityConclude(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroupScheduled`  
 現在スケジュールされているストーリーボードを所有しているグループ。  
  
 `pGroupNew`  
 pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。  
  
 `priorityEffect`  
 pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。  
  
### <a name="return-value"></a>戻り値  
 pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_CONCLUDE を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 競合の管理の詳細については、Windows Animation API ドキュメント (http://msdn.microsoft.com/library/dd371759(VS.85).aspx)です。  
  
##  <a name="onhasprioritytrim"></a>  CAnimationController::OnHasPriorityTrim  
 スケジュールの競合を解決するために、フレームワークによって呼び出されます。  
  
```  
virtual BOOL OnHasPriorityTrim(
    CAnimationGroup* pGroupScheduled,  
    CAnimationGroup* pGroupNew,  
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroupScheduled`  
 現在スケジュールされているストーリーボードを所有しているグループ。  
  
 `pGroupNew`  
 pGroupScheduled が所有するスケジュール済みのストーリーボードとスケジュールが競合している新しいストーリーボードを所有しているグループ。  
  
 `priorityEffect`  
 pGroupScheduled の優先度がより高い場合に予想される pGroupNew への影響。  
  
### <a name="return-value"></a>戻り値  
 pGroupNew が所有するストーリーボードの優先度が高い場合は TRUE を返します。 pGroupScheduled が所有するストーリーボードの優先度が高い場合は FALSE を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、CAnimationController::EnablePriorityComparisonHandler を使用して優先度比較イベントを有効にし、UI_ANIMATION_PHT_TRIM を指定した場合に呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。 競合の管理の詳細については、Windows Animation API ドキュメント (http://msdn.microsoft.com/library/dd371759(VS.85).aspx)です。  
  
##  <a name="onstoryboardstatuschanged"></a>  CAnimationController::OnStoryboardStatusChanged  
 ストーリー ボードの状態が変更されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnStoryboardStatusChanged(
    CAnimationGroup* pGroup,  
    UI_ANIMATION_STORYBOARD_STATUS newStatus,  
    UI_ANIMATION_STORYBOARD_STATUS previousStatus);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroup`  
 ステータスがストーリー ボードを所有しているアニメーション グループへのポインターが変更されました。  
  
 `newStatus`  
 新しいステータスを指定します。  
  
 `previousStatus`  
 以前の状態を指定します。  
  
### <a name="remarks"></a>コメント  
 CAnimationController::EnableStoryboardEventHandler を使用してストーリー ボード イベントを有効にした場合は、このメソッドが呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。  
  
##  <a name="onstoryboardupdated"></a>  CAnimationController::OnStoryboardUpdated  
 ストーリー ボードが更新されたときに、フレームワークによって呼び出されます。  
  
```  
virtual void OnStoryboardUpdated(CAnimationGroup* pGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `pGroup`  
 ストーリー ボードを所有しているグループへのポインター。  
  
### <a name="remarks"></a>コメント  
 CAnimationController::EnableStoryboardEventHandler を使用してストーリー ボード イベントを有効にした場合は、このメソッドが呼び出されます。 派生クラスでオーバーライドして、アプリケーション固有のアクションを実行できます。  
  
##  <a name="removeallanimationgroups"></a>  CAnimationController::RemoveAllAnimationGroups  
 アニメーションのすべてのグループは、アニメーション コント ローラーから削除します。  
  
```  
void RemoveAllAnimationGroups();
```  
  
### <a name="remarks"></a>コメント  
 れるすべてのグループが削除されると、そのポインターでは、アプリケーション レベルで格納されている場合必要があります無効になります。 削除対象のグループの CAnimationGroup::m_bAutodestroyAnimationObjects が TRUE の場合は、そのグループに属しているすべてのアニメーション オブジェクトが削除されます。それ以外の場合親アニメーション コント ローラーへの参照は NULL に設定して、それらを別のコント ローラーに追加することができます。  
  
##  <a name="removeanimationgroup"></a>  CAnimationController::RemoveAnimationGroup  
 アニメーション コント ローラーから、指定した ID を持つ、アニメーション グループを削除します。  
  
```  
void RemoveAnimationGroup(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 アニメーション グループ ID を指定します  
  
### <a name="remarks"></a>コメント  
 このメソッドは、内部グループの一覧から、アニメーション グループを削除し、これを削除、したがってそのアニメーション グループへのポインターが格納されている場合にする必要があります無効になります。 CAnimationGroup::m_bAutodestroyAnimationObjects が TRUE の場合は、そのグループに属しているすべてのアニメーション オブジェクトが削除されます。それ以外の場合親アニメーション コント ローラーへの参照は NULL に設定して、それらを別のコント ローラーに追加することができます。  
  
##  <a name="removeanimationobject"></a>  CAnimationController::RemoveAnimationObject  
 アニメーション オブジェクトは、アニメーション コント ローラーから削除します。  
  
```  
void RemoveAnimationObject(
    CAnimationBaseObject* pObject,  
    BOOL bNoDelete = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pObject`  
 アニメーション オブジェクトへのポインター。  
  
 `bNoDelete`  
 このパラメーターが TRUE の場合、オブジェクトは削除時に削除されません。  
  
### <a name="remarks"></a>コメント  
 アニメーション オブジェクトは、アニメーション コント ローラーとアニメーション グループから削除します。 特定のオブジェクトをされなくなりますアニメーション化する必要がありますいない場合、またはオブジェクトを別のアニメーション コント ローラーに移動する必要がある場合は、この関数を呼び出します。 最後の case bNoDelete は TRUE をする必要があります。  
  
##  <a name="removetransitions"></a>  CAnimationController::RemoveTransitions  
 指定されたグループに属するアニメーション オブジェクトから遷移を削除します。  
  
```  
void RemoveTransitions(UINT32 nGroupID);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 グループ ID を指定します  
  
### <a name="remarks"></a>コメント  
 グループは、そのアニメーション オブジェクトをループ処理し、アニメーション オブジェクトごとに ClearTransitions(FALSE) を呼び出します。 このメソッドはアニメーションがスケジュールされている後に、フレームワークによって呼び出されます。  
  
##  <a name="schedulegroup"></a>  CAnimationController::ScheduleGroup  
 アニメーションをスケジュールします。  
  
```  
BOOL ScheduleGroup(
    UINT32 nGroupID,  
    UI_ANIMATION_SECONDS time = 0.0);
```  
  
### <a name="parameters"></a>パラメーター  
 `nGroupID`  
 アニメーションをスケジュールするグループの ID を指定します。  
  
 `time`  
 スケジュールを設定する時刻を指定します。  
  
### <a name="return-value"></a>戻り値  
 アニメーションが正常にスケジュールされている場合は TRUE。 ストーリー ボードが作成されていない、またはその他のエラーが発生した場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 AnimateGroup 以前 ScheduleGroup を FALSE に設定するパラメーター bScheduleNow で呼び出す必要があります。 IUIAnimationTimer::GetTime から取得した目的のアニメーションの時間を指定することができます。 時間パラメーターが 0.0 の場合は、アニメーションは現在の時刻にスケジュールされます。  
  
##  <a name="setrelatedwnd"></a>  CAnimationController::SetRelatedWnd  
 アニメーション コント ローラーと、ウィンドウ間のリレーションシップを確立します。  
  
```  
void SetRelatedWnd(CWnd* pWnd);
```  
  
### <a name="parameters"></a>パラメーター  
 `pWnd`  
 設定するウィンドウのオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 場合関連 CWnd オブジェクトを設定すると、アニメーション コント ローラーに自動的に更新できます (WM_PAINT メッセージを送信する) ときにアニメーション マネージャーの状態が変更されたか、タイマー post 更新イベントが発生しました。  
  
##  <a name="updateanimationmanager"></a>  CAnimationController::UpdateAnimationManager  
 アニメーション マネージャーのすべてのアニメーション変数の値を更新するように指示します。  
  
```  
virtual void UpdateAnimationManager();
```  
  
### <a name="remarks"></a>コメント  
 呼び出すこのメソッドは、現在の時刻に、アニメーション マネージャーを進めます、必要に応じて、ストーリー ボードのステータスを変更して、アニメーション変数に適切な更新は、値を補間します。 内部的にこのメソッドは IUIAnimationTimer::GetTime(timeNow) と IUIAnimationManager::Update(timeNow) を呼び出します。 この動作をカスタマイズする派生クラスでこのメソッドをオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
