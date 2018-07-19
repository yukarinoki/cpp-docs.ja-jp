---
title: CBaseTransition クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::CBaseTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboard
- AFXANIMATIONCONTROLLER/CBaseTransition::AddToStoryboardAtKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::Clear
- AFXANIMATIONCONTROLLER/CBaseTransition::Create
- AFXANIMATIONCONTROLLER/CBaseTransition::GetEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::GetStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::GetTransition
- AFXANIMATIONCONTROLLER/CBaseTransition::GetType
- AFXANIMATIONCONTROLLER/CBaseTransition::IsAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::SetKeyframes
- AFXANIMATIONCONTROLLER/CBaseTransition::SetRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_bAdded
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pEndKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pRelatedVariable
- AFXANIMATIONCONTROLLER/CBaseTransition::m_pStartKeyframe
- AFXANIMATIONCONTROLLER/CBaseTransition::m_transition
- AFXANIMATIONCONTROLLER/CBaseTransition::m_type
dev_langs:
- C++
helpviewer_keywords:
- CBaseTransition [MFC], CBaseTransition
- CBaseTransition [MFC], AddToStoryboard
- CBaseTransition [MFC], AddToStoryboardAtKeyframes
- CBaseTransition [MFC], Clear
- CBaseTransition [MFC], Create
- CBaseTransition [MFC], GetEndKeyframe
- CBaseTransition [MFC], GetRelatedVariable
- CBaseTransition [MFC], GetStartKeyframe
- CBaseTransition [MFC], GetTransition
- CBaseTransition [MFC], GetType
- CBaseTransition [MFC], IsAdded
- CBaseTransition [MFC], SetKeyframes
- CBaseTransition [MFC], SetRelatedVariable
- CBaseTransition [MFC], m_bAdded
- CBaseTransition [MFC], m_pEndKeyframe
- CBaseTransition [MFC], m_pRelatedVariable
- CBaseTransition [MFC], m_pStartKeyframe
- CBaseTransition [MFC], m_transition
- CBaseTransition [MFC], m_type
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c7cdd8f527b8df8ae80896bbb17fab1b15684180
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953571"
---
# <a name="cbasetransition-class"></a>CBaseTransition クラス
基本遷移を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CBaseTransition : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-enumerations"></a>パブリック列挙型  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::TRANSITION_TYPE 列挙型](#transition_type_enumeration)|現時点では、Windows Animation API の MFC 実装によって遷移タイプを定義します。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](#cbasetransition)|切り替え効果の基本オブジェクトを構築します。|  
|[CBaseTransition:: ~ CBaseTransition](#cbasetransition__~cbasetransition)|デストラクターです。 移行のオブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](#addtostoryboard)|ストーリー ボードへの遷移を追加します。|  
|[CBaseTransition::AddToStoryboardAtKeyframes](#addtostoryboardatkeyframes)|ストーリー ボードへの遷移を追加します。|  
|[CBaseTransition::Clear](#clear)|リリースは、IUIAnimationTransition COM オブジェクトをカプセル化されます。|  
|[CBaseTransition::Create](#create)|COM の遷移を作成します。|  
|[CBaseTransition::GetEndKeyframe](#getendkeyframe)|返しますでは、キーフレームを開始します。|  
|[CBaseTransition::GetRelatedVariable](#getrelatedvariable)|関連する変数へのポインターを返します。|  
|[CBaseTransition::GetStartKeyframe](#getstartkeyframe)|返しますでは、キーフレームを開始します。|  
|[CBaseTransition::GetTransition](#gettransition)|オーバーロードされます。 基になる COM 遷移オブジェクトへのポインターを返します。|  
|[CBaseTransition::GetType](#gettype)|返しますでは、型を移行します。|  
|[CBaseTransition::IsAdded](#isadded)|ストーリー ボードへの遷移が追加されているかどうかを指示します。|  
|[:Setkeyframes](#setkeyframes)|遷移のキーフレームを設定します。|  
|[CBaseTransition::SetRelatedVariable](#setrelatedvariable)|アニメーション変数と切り替えの間にリレーションシップを確立します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CBaseTransition::m_bAdded](#m_badded)|ストーリー ボードへの遷移が追加されているかどうかを指定します。|  
|[CBaseTransition::m_pEndKeyframe](#m_pendkeyframe)|遷移の終わりを指定するキーフレームへのポインターを格納します。|  
|[CBaseTransition::m_pRelatedVariable](#m_prelatedvariable)|M_transition に格納されている遷移にアニメーション化する、アニメーション変数へのポインター。|  
|[CBaseTransition::m_pStartKeyframe](#m_pstartkeyframe)|遷移の始まりを指定するキーフレームへのポインターを格納します。|  
|[CBaseTransition::m_transition](#m_transition)|IUIAnimationTransition へのポインターを格納します。 COM 遷移オブジェクトが作成されていない場合は NULL です。|  
|[CBaseTransition::m_type](#m_type)|移行型を格納します。|  
  
## <a name="remarks"></a>Remarks  
 このクラスは、IUIAnimationTransition インターフェイスをカプセル化し、すべての遷移の基底クラスとして機能します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CBaseTransition`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="_dtorcbasetransition"></a>  CBaseTransition:: ~ CBaseTransition  
 デストラクターです。 移行のオブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CBaseTransition();
```  
  
##  <a name="addtostoryboard"></a>  CBaseTransition::AddToStoryboard  
 ストーリー ボードへの遷移を追加します。  
  
```  
BOOL AddToStoryboard(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStoryboard*  
 関連する変数をアニメーション化されますが、ストーリー ボードへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボードへの移行を正常に追加する場合は TRUE。  
  
### <a name="remarks"></a>Remarks  
 ストーリー ボードに関連する変数への移行を適用します。 このストーリー ボードでこの変数に適用される最初の遷移の場合は、ストーリー ボードの開始時に、移行を開始します。 それ以外の場合、遷移は、変数に最近追加された遷移に追加されます。  
  
##  <a name="addtostoryboardatkeyframes"></a>  CBaseTransition::AddToStoryboardAtKeyframes  
 ストーリー ボードへの遷移を追加します。  
  
```  
BOOL AddToStoryboardAtKeyframes(IUIAnimationStoryboard* pStoryboard);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStoryboard*  
 関連する変数をアニメーション化されますが、ストーリー ボードへのポインター。  
  
### <a name="return-value"></a>戻り値  
 ストーリー ボードへの移行を正常に追加する場合は TRUE。  
  
### <a name="remarks"></a>Remarks  
 ストーリー ボードに関連する変数への移行を適用します。 開始キーフレームが指定されている場合そのキーフレームで遷移を開始します。 開始キーフレームで遷移を開始終了キーフレームが指定されている場合、終了キーフレームで停止します。 Duration パラメーターを指定、遷移が作成されている場合は、その期間が開始および終了のキーフレームまでの時間で上書きされます。 キーフレームが指定されていない場合は、変数に最近追加された遷移を遷移が追加されます。  
  
##  <a name="cbasetransition"></a>  CBaseTransition::CBaseTransition  
 切り替え効果の基本オブジェクトを構築します。  
  
```  
CBaseTransition();
```  
  
##  <a name="clear"></a>  CBaseTransition::Clear  
 リリースは、IUIAnimationTransition COM オブジェクトをカプセル化されます。  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、IUITransition インターフェイスのリークを防ぐために、派生クラスの Create メソッドから呼び出す必要があります。  
  
##  <a name="create"></a>  CBaseTransition::Create  
 COM の遷移を作成します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *pLibrary*  
 作成する標準的な遷移遷移ライブラリへのポインター。 カスタム遷移は、NULL にすることできます。  
  
 *pFactory*  
 カスタム遷移を作成する遷移ファクトリへのポインター。 標準的な遷移の NULL を設定することできます。  
  
### <a name="return-value"></a>戻り値  
 遷移 COM オブジェクトが正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 これは、派生クラスでオーバーライドされる必要がある純粋仮想関数です。 基になる COM 遷移オブジェクトをインスタンス化するためにフレームワークによって呼び出されます。  
  
##  <a name="getendkeyframe"></a>  CBaseTransition::GetEndKeyframe  
 返しますでは、キーフレームを開始します。  
  
```  
CBaseKeyFrame* GetEndKeyframe();
```  
  
### <a name="return-value"></a>戻り値  
 キーフレームや遷移をキーフレーム間で挿入できない場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、以前 SetKeyframes によって設定されたキーフレーム オブジェクトへのアクセスに使用できます。 切り替え効果をストーリー ボードに追加されているときに、最上位のコードによって呼び出されます。  
  
##  <a name="getrelatedvariable"></a>  CBaseTransition::GetRelatedVariable  
 関連する変数へのポインターを返します。  
  
```  
CAnimationVariable* GetRelatedVariable();
```  
  
### <a name="return-value"></a>戻り値  
 アニメーション変数、または NULL SetRelatedVariable によってアニメーション変数が設定されていない場合に有効なポインター。  
  
### <a name="remarks"></a>Remarks  
 これは、関連するアニメーション変数をアクセサーです。  
  
##  <a name="getstartkeyframe"></a>  CBaseTransition::GetStartKeyframe  
 返しますでは、キーフレームを開始します。  
  
```  
CBaseKeyFrame* GetStartKeyframe();
```  
  
### <a name="return-value"></a>戻り値  
 キーフレームや遷移始めることはできませんのキーフレームに続く場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、以前 SetKeyframes によって設定されたキーフレーム オブジェクトへのアクセスに使用できます。 切り替え効果をストーリー ボードに追加されているときに、最上位のコードによって呼び出されます。  
  
##  <a name="gettransition"></a>  CBaseTransition::GetTransition  
 基になる COM 遷移オブジェクトへのポインターを返します。  
  
```  
IUIAnimationTransition* GetTransition(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* pFactory);  
  
IUIAnimationTransition* GetTransition();
```  
  
### <a name="parameters"></a>パラメーター  
 *pLibrary*  
 作成する標準的な遷移遷移ライブラリへのポインター。 カスタム遷移は、NULL にすることできます。  
  
 *pFactory*  
 カスタム遷移を作成する遷移ファクトリへのポインター。 標準的な遷移の NULL を設定することできます。  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationTransition または遷移の基になる場合は NULL に有効なポインターを作成することはできません。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、基になる COM 遷移オブジェクトへのポインターを返し、必要に応じて作成します。  
  
##  <a name="gettype"></a>  CBaseTransition::GetType  
 返しますでは、型を移行します。  
  
```  
TRANSITION_TYPE GetType() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRANSITION_TYPE の 1 つは列挙値です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、その型によって遷移オブジェクトの識別に使用できます。 種類は、派生クラスでコンス トラクターで設定されます。  
  
##  <a name="isadded"></a>  CBaseTransition::IsAdded  
 ストーリー ボードへの遷移が追加されているかどうかを指示します。  
  
```  
BOOL IsAdded();
```  
  
### <a name="return-value"></a>戻り値  
 遷移が FALSE の場合は、ストーリー ボードに追加されたかどうかに TRUE を返します。  
  
### <a name="remarks"></a>Remarks  
 このフラグは、最上位レベルのコードは、ストーリー ボードへの切り替えを追加したときに内部的に設定されます。  
  
##  <a name="m_badded"></a>  CBaseTransition::m_bAdded  
 ストーリー ボードへの遷移が追加されているかどうかを指定します。  
  
```  
BOOL m_bAdded;  
```  
  
##  <a name="m_pendkeyframe"></a>  CBaseTransition::m_pEndKeyframe  
 遷移の終わりを指定するキーフレームへのポインターを格納します。  
  
```  
CBaseKeyFrame* m_pEndKeyframe;  
```  
  
##  <a name="m_prelatedvariable"></a>  CBaseTransition::m_pRelatedVariable  
 M_transition に格納されている遷移にアニメーション化する、アニメーション変数へのポインター。  
  
```  
CAnimationVariable* m_pRelatedVariable;  
```  
  
##  <a name="m_pstartkeyframe"></a>  CBaseTransition::m_pStartKeyframe  
 遷移の始まりを指定するキーフレームへのポインターを格納します。  
  
```  
CBaseKeyFrame* m_pStartKeyframe;  
```  
  
##  <a name="m_transition"></a>  CBaseTransition::m_transition  
 IUIAnimationTransition へのポインターを格納します。 COM 遷移オブジェクトが作成されていない場合は NULL です。  
  
```  
ATL::CComPtr<IUIAnimationTransition> m_transition;  
```  
  
##  <a name="m_type"></a>  CBaseTransition::m_type  
 移行型を格納します。  
  
```  
TRANSITION_TYPE m_type;  
```  
  
##  <a name="setkeyframes"></a>  :Setkeyframes  
 遷移のキーフレームを設定します。  
  
```  
void SetKeyframes(
    CBaseKeyFrame* pStart = NULL,  
    CBaseKeyFrame* pEnd = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStart*  
 遷移の始まりを指定するキーフレームです。  
  
 *保留*  
 遷移の終わりを指定するキーフレームです。  
  
### <a name="remarks"></a>Remarks  
 この方法で指定されたキーフレームの後に起動し、保留が NULL でない場合を終了する必要に応じて、遷移は、指定されたキーフレームの前にします。 Duration パラメーターを指定、遷移が作成されている場合は、その期間が開始および終了のキーフレームまでの時間で上書きされます。  
  
##  <a name="setrelatedvariable"></a>  CBaseTransition::SetRelatedVariable  
 アニメーション変数と切り替えの間にリレーションシップを確立します。  
  
```  
void SetRelatedVariable(CAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>パラメーター  
 *pVariable*  
 関連するアニメーション変数へのポインター。  
  
### <a name="remarks"></a>Remarks  
 アニメーション変数と切り替えの間にリレーションシップを確立します。 遷移は、1 つの変数にのみ適用できます。  
  
##  <a name="transition_type_enumeration"></a>  CBaseTransition::TRANSITION_TYPE 列挙型  
 現時点では、Windows Animation API の MFC 実装によって遷移タイプを定義します。  
  
```  
enum TRANSITION_TYPE;  
```  
  
### <a name="remarks"></a>Remarks  
 移行型では、特定の遷移のコンス トラクターで設定されています。 たとえば、CSinusoidalTransitionFromRange は SINUSOIDAL_FROM_RANGE をその型を設定します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
