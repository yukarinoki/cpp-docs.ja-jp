---
title: CAnimationBaseObject クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CAnimationBaseObject
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::ContainsVariable
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::DetachFromController
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::SetParentAnimationObjects
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_dwUserData
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nGroupID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_nObjectID
- AFXANIMATIONCONTROLLER/CAnimationBaseObject::m_pParentController
dev_langs:
- C++
helpviewer_keywords:
- CAnimationBaseObject [MFC], CAnimationBaseObject
- CAnimationBaseObject [MFC], ApplyTransitions
- CAnimationBaseObject [MFC], ClearTransitions
- CAnimationBaseObject [MFC], ContainsVariable
- CAnimationBaseObject [MFC], CreateTransitions
- CAnimationBaseObject [MFC], DetachFromController
- CAnimationBaseObject [MFC], EnableIntegerValueChangedEvent
- CAnimationBaseObject [MFC], EnableValueChangedEvent
- CAnimationBaseObject [MFC], GetAutodestroyTransitions
- CAnimationBaseObject [MFC], GetGroupID
- CAnimationBaseObject [MFC], GetObjectID
- CAnimationBaseObject [MFC], GetUserData
- CAnimationBaseObject [MFC], SetAutodestroyTransitions
- CAnimationBaseObject [MFC], SetID
- CAnimationBaseObject [MFC], SetUserData
- CAnimationBaseObject [MFC], GetAnimationVariableList
- CAnimationBaseObject [MFC], SetParentAnimationObjects
- CAnimationBaseObject [MFC], m_bAutodestroyTransitions
- CAnimationBaseObject [MFC], m_dwUserData
- CAnimationBaseObject [MFC], m_nGroupID
- CAnimationBaseObject [MFC], m_nObjectID
- CAnimationBaseObject [MFC], m_pParentController
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 135bb279daf4c000c025ac6f8fa51a6b023e2d1e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952545"
---
# <a name="canimationbaseobject-class"></a>CAnimationBaseObject クラス
すべてのアニメーション オブジェクトの基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](#canimationbaseobject)|オーバーロードされます。 アニメーション オブジェクトを構築します。|  
|[CAnimationBaseObject:: ~ CAnimationBaseObject](#canimationbaseobject__~canimationbaseobject)|デストラクターです。 アニメーション オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](#applytransitions)|カプセル化されたアニメーション変数のストーリー ボードへの切り替えを追加します。|  
|[CAnimationBaseObject::ClearTransitions](#cleartransitions)|すべての関連する遷移を削除します。|  
|[CAnimationBaseObject::ContainsVariable](#containsvariable)|アニメーション オブジェクトが特定のアニメーション変数を含めるかどうかを判断します。|  
|[CAnimationBaseObject::CreateTransitions](#createtransitions)|アニメーション オブジェクトに関連付けられている遷移を作成します。|  
|[CAnimationBaseObject::DetachFromController](#detachfromcontroller)|親アニメーション コント ローラーからのアニメーション オブジェクトをデタッチします。|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|整数値が変更されたイベント ハンドラーを設定します。|  
|[CAnimationBaseObject::EnableValueChangedEvent](#enablevaluechangedevent)|イベント ハンドラーの値が変更を設定します。|  
|[CAnimationBaseObject::GetAutodestroyTransitions](#getautodestroytransitions)|関連する遷移が自動的に破棄されるかどうかを指示します。|  
|[CAnimationBaseObject::GetGroupID](#getgroupid)|現在のグループ ID を返します。|  
|[CAnimationBaseObject::GetObjectID](#getobjectid)|現在のオブジェクト ID を返します。|  
|[CAnimationBaseObject::GetUserData](#getuserdata)|ユーザー定義データを返します。|  
|[CAnimationBaseObject::SetAutodestroyTransitions](#setautodestroytransitions)|切り替え効果を自動的に破棄する順序付けをするフラグを設定します。|  
|[CAnimationBaseObject::SetID](#setid)|新しい Id を設定します。|  
|[CAnimationBaseObject::SetUserData](#setuserdata)|ユーザー定義データを設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](#getanimationvariablelist)|アニメーションが含まれている変数へのポインターを収集します。|  
|[CAnimationBaseObject::SetParentAnimationObjects](#setparentanimationobjects)|アニメーション変数、アニメーション オブジェクト、およびそのコンテナーに含まれている間のリレーションシップを確立します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[CAnimationBaseObject::m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連する遷移が自動的に破棄する必要があるかどうかを指定します。|  
|[CAnimationBaseObject::m_dwUserData](#m_dwuserdata)|ユーザー定義データを格納します。|  
|[CAnimationBaseObject::m_nGroupID](#m_ngroupid)|アニメーション オブジェクトのグループ ID を指定します。|  
|[CAnimationBaseObject::m_nObjectID](#m_nobjectid)|アニメーション オブジェクトのオブジェクト ID を指定します。|  
|[CAnimationBaseObject::m_pParentController](#m_pparentcontroller)|親アニメーション コント ローラーへのポインター。|  
  
## <a name="remarks"></a>Remarks  
 このクラスは、すべてのアニメーション オブジェクトの基本的なメソッドを実装します。 アニメーション オブジェクトでは、値、ポイント、サイズ、四角形を表すしたり、色のカスタム エンティティと同様に、アプリケーションですることができます。 アニメーション オブジェクトは、アニメーション グループ (CAnimationGroup を参照してください) に格納されます。 各グループは、個別にアニメーション化できるし、ストーリー ボードの類似性として扱うことができます。 アニメーション オブジェクトでは、1 つまたは複数アニメーション変数 (CAnimationVariable を参照してください)、その論理表現によってカプセル化します。 たとえば、CAnimationRect には、4 つのアニメーション変数四角形の各辺に 1 つの変数にはが含まれています。 各アニメーション オブジェクトのクラスは、遷移をカプセル化されたアニメーション変数に適用するために使用する必要があります、オーバー ロードされた AddTransition メソッドを公開します。 アニメーション オブジェクトを特定するのにオブジェクト ID (必要に応じて)、グループ id。 グループ ID は、正しいグループにアニメーション オブジェクトを配置するために必要ですが、既定のグループ ID が 0 のオブジェクトを配置するグループ ID が指定されていない場合。 さまざまな GroupID で SetID を呼び出す場合は、アニメーション オブジェクトは (新しいグループは必要な場合に作成された) 別のグループに移動されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CAnimationBaseObject`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationbaseobject"></a>  CAnimationBaseObject:: ~ CAnimationBaseObject  
 デストラクターです。 アニメーション オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CAnimationBaseObject();
```  
  
##  <a name="applytransitions"></a>  CAnimationBaseObject::ApplyTransitions  
 カプセル化されたアニメーション変数のストーリー ボードへの切り替えを追加します。  
  
```  
virtual BOOL ApplyTransitions(
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>パラメーター  
 *pStoryboard*  
 ストーリー ボードへのポインター。  
  
 *bDependOnKeyframes*  
 FALSE には、このメソッドは、キーフレームに依存しない遷移のみを追加します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に追加された場合は TRUE。  
  
### <a name="remarks"></a>Remarks  
 AddTransition (派生クラスではオーバー ロードされたメソッド) に、ストーリー ボードに追加されている、関連する遷移を追加します。  
  
##  <a name="canimationbaseobject"></a>  CAnimationBaseObject::CAnimationBaseObject  
 アニメーション オブジェクトを構築します。  
  
```  
CAnimationBaseObject();

 
CAnimationBaseObject(
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *nGroupID*  
 グループ ID を指定します  
  
 *nObjectID*  
 オブジェクト ID を指定します  
  
 *dwUserData*  
 ユーザー定義のデータ、アニメーション オブジェクトに関連付けられている、実行時に後で取得できます。  
  
### <a name="remarks"></a>Remarks  
 アニメーション オブジェクトを構築し、既定のオブジェクト ID (0) とグループ ID (0) を割り当てます。  
  
##  <a name="cleartransitions"></a>  CAnimationBaseObject::ClearTransitions  
 すべての関連する遷移を削除します。  
  
```  
virtual void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>パラメーター  
 *bAutodestroy*  
 自動的には、transition オブジェクトを破棄またはだけ関連一覧から削除するかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 関連するすべての遷移を削除し、bAutodestroy または m_bAutodestroyTransitions フラグが TRUE の場合は、それらを破棄します。 遷移は、スタックにない割り当てられている場合にのみ、自動的に破棄する必要があります。 上記のフラグが FALSE の場合は、遷移のみ関連する遷移の内部リストから削除されます。  
  
##  <a name="containsvariable"></a>  CAnimationBaseObject::ContainsVariable  
 アニメーション オブジェクトが特定のアニメーション変数を含めるかどうかを判断します。  
  
```  
virtual BOOL ContainsVariable(IUIAnimationVariable* pVariable);
```  
  
### <a name="parameters"></a>パラメーター  
 *pVariable*  
 アニメーション変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 アニメーション変数がアニメーション オブジェクトに含まれている場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、pVariable で指定されたアニメーション変数がアニメーション オブジェクト内に含まれるかどうかを決定する使用できます。 種類に応じて、アニメーション オブジェクトは、いくつかのアニメーション変数を含めることがあります。 たとえば、CAnimationColor には、3 つの変数が各色要素 (赤、緑、および青) のいずれかが含まれています。 アニメーション変数の値が変更されたときに、Windows Animation API は ValueChanged または IntegerValueChanged イベント (有効な場合)、および、このイベントのパラメーターはアニメーション変数の IUIAnimationVariable インターフェイスへのポインターを送信します。 このメソッドは、格納されている COM オブジェクトへのポインターからアニメーションへのポインターを取得するのに役立ちます。  
  
##  <a name="createtransitions"></a>  CAnimationBaseObject::CreateTransitions  
 アニメーション オブジェクトに関連付けられている遷移を作成します。  
  
```  
BOOL CreateTransitions();
```  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>Remarks  
 アニメーションの派生オブジェクトにカプセル化されたアニメーション変数の一覧をループ処理し、アニメーションの各変数に関連付けられている遷移を作成します。  
  
##  <a name="detachfromcontroller"></a>  CAnimationBaseObject::DetachFromController  
 親アニメーション コント ローラーからのアニメーション オブジェクトをデタッチします。  
  
```  
void DetachFromController();
```  
  
### <a name="remarks"></a>Remarks  
 このメソッドは内部的に使用されます。  
  
##  <a name="enableintegervaluechangedevent"></a>  CAnimationBaseObject::EnableIntegerValueChangedEvent  
 整数値が変更されたイベント ハンドラーを設定します。  
  
```  
virtual void EnableIntegerValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *pController*  
 親のコント ローラーへのポインター。  
  
 *bEnable*  
 有効、または整数値の変更イベントを無効にするかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 整数値が変更されたイベント ハンドラーが有効になっている場合は、CAnimationController 派生クラスでオーバーライドする必要がある CAnimationController::OnAnimationIntegerValueChanged メソッドでは、このイベントを処理できます。 アニメーションの整数値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationBaseObject::EnableValueChangedEvent  
 イベント ハンドラーの値が変更を設定します。  
  
```  
virtual void EnableValueChangedEvent(
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 *pController*  
 親のコント ローラーへのポインター。  
  
 *bEnable*  
 有効、または値の変更イベントを無効にするかどうかを指定します。  
  
### <a name="remarks"></a>Remarks  
 値が変更されたイベント ハンドラーが有効になっている場合は、CAnimationController 派生クラスでオーバーライドする必要がある CAnimationController::OnAnimationValueChanged メソッドでは、このイベントを処理できます。 アニメーションの値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="getanimationvariablelist"></a>  CAnimationBaseObject::GetAnimationVariableList  
 アニメーションが含まれている変数へのポインターを収集します。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst) = 0;  
```  
  
### <a name="parameters"></a>パラメーター  
 *lst*  
 一連のアニメーション オブジェクトに含まれるアニメーション変数を格納する必要があります。  
  
### <a name="remarks"></a>Remarks  
 これは、派生クラスでオーバーライドされる必要がある純粋仮想メソッドです。 種類に応じて、アニメーション オブジェクトには、1 つまたは複数のアニメーション変数が含まれています。 たとえば、CAnimationPoint は、X 座標と Y 座標はそれぞれの 2 つの変数を格納します。 基底クラス CAnimationBaseObject、アニメーション変数の一覧で操作を実行する一部のジェネリック メソッドの実装: ApplyTransitions、ClearTransitions、EnableValueChangedEvent、EnableIntegerValueChangedEvent です。 これらのメソッドは GetAnimationVariableList で、特定のアニメーション オブジェクトに含まれる実際のアニメーションの変数が派生クラスに入力されますを呼び出して一覧をループし、必要なアクションを実行します。 アニメーション オブジェクトを作成する場合は、そのオブジェクトに含まれるすべてのアニメーション変数を lst を追加する必要があります。  
  
##  <a name="getautodestroytransitions"></a>  CAnimationBaseObject::GetAutodestroyTransitions  
 関連する遷移が自動的に破棄されるかどうかを指示します。  
  
```  
BOOL GetAutodestroyTransitions() const;  
```  
  
### <a name="return-value"></a>戻り値  
 TRUE の場合、関連する遷移を自動的に破棄します。FALSE の場合、transition オブジェクトにアプリケーションを呼び出すことによって割り当てを解除する必要があります。  
  
### <a name="remarks"></a>Remarks  
 既定ではこのフラグは TRUE です。 呼び出し元アプリケーションによって遷移の割り当てを解除する必要があります、スタック上のトランジションを割り当てられている場合のみ、このフラグを設定します。  
  
##  <a name="getgroupid"></a>  CAnimationBaseObject::GetGroupID  
 現在のグループ ID を返します。  
  
```  
UINT32 GetGroupID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のグループの id。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、グループ ID を取得するには グループ ID が設定されていない明示的にコンス トラクターや SetID の場合は 0 の。  
  
##  <a name="getobjectid"></a>  CAnimationBaseObject::GetObjectID  
 現在のオブジェクト ID を返します。  
  
```  
UINT32 GetObjectID() const;  
```  
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクト id です。  
  
### <a name="remarks"></a>Remarks  
 このメソッドを使用して、オブジェクト ID を取得するには オブジェクト ID が設定されていない明示的にコンス トラクターや SetID の場合は 0 の。  
  
##  <a name="getuserdata"></a>  CAnimationBaseObject::GetUserData  
 ユーザー定義データを返します。  
  
```  
DWORD GetUserData() const;  
```  
  
### <a name="return-value"></a>戻り値  
 カスタム データの値です。  
  
### <a name="remarks"></a>Remarks  
 実行時にカスタム データを取得するには、このメソッドを呼び出します。 明示的にコンス トラクター、または SetUserData で初期化されてがいない場合は、返された値を 0 になります。  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationBaseObject::m_bAutodestroyTransitions  
 関連する遷移が自動的に破棄する必要があるかどうかを指定します。  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
##  <a name="m_dwuserdata"></a>  CAnimationBaseObject::m_dwUserData  
 ユーザー定義データを格納します。  
  
```  
DWORD m_dwUserData;  
```  
  
##  <a name="m_ngroupid"></a>  CAnimationBaseObject::m_nGroupID  
 アニメーション オブジェクトのグループ ID を指定します。  
  
```  
UINT32 m_nGroupID;  
```  
  
##  <a name="m_nobjectid"></a>  CAnimationBaseObject::m_nObjectID  
 アニメーション オブジェクトのオブジェクト ID を指定します。  
  
```  
UINT32 m_nObjectID;  
```  
  
##  <a name="m_pparentcontroller"></a>  CAnimationBaseObject::m_pParentController  
 親アニメーション コント ローラーへのポインター。  
  
```  
CAnimationController* m_pParentController;  
```  
  
##  <a name="setautodestroytransitions"></a>  CAnimationBaseObject::SetAutodestroyTransitions  
 切り替え効果を自動的に破棄する順序付けをするフラグを設定します。  
  
```  
void SetAutodestroyTransitions(BOOL bValue);
```  
  
### <a name="parameters"></a>パラメーター  
 *bValue*  
 自動破棄フラグを指定します。  
  
### <a name="remarks"></a>Remarks  
 新しい演算子を使用して transition オブジェクトに割り当てている場合にのみ、このフラグを設定します。 自動の破棄、何らかの理由 transition オブジェクトは、スタックに割り当てられたフラグが FALSE にする必要があります。 既定ではこのフラグは TRUE です。  
  
##  <a name="setid"></a>  CAnimationBaseObject::SetID  
 新しい Id を設定します。  
  
```  
void SetID(
    UINT32 nObjectID,  
    UINT32 nGroupID = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *nObjectID*  
 新しいオブジェクトの ID を指定します  
  
 *nGroupID*  
 新しいグループの ID を指定します  
  
### <a name="remarks"></a>Remarks  
 オブジェクト ID とグループ ID を変更するのには、します。 新しいグループの ID と異なる場合、現在の ID、アニメーション オブジェクトは、別のグループ (新しいグループは作成されません、必要な場合) に移動されます。  
  
##  <a name="setparentanimationobjects"></a>  CAnimationBaseObject::SetParentAnimationObjects  
 アニメーション変数、アニメーション オブジェクト、およびそのコンテナーに含まれている間のリレーションシップを確立します。  
  
```  
virtual void SetParentAnimationObjects();
```  
  
### <a name="remarks"></a>Remarks  
 これは、アニメーション オブジェクト、およびそのコンテナーに含まれている、アニメーション変数の間のリレーションシップを確立するために使用できるヘルパーです。 アニメーション変数をループ処理し、各アニメーション変数の親アニメーション オブジェクトへのバック ポインターを設定します。 CAnimationBaseObject::ApplyTransitions で実際の関係が確立された現在の実装、したがってバック ポインターは設定されません CAnimationGroup::Animate が呼び出されるまで。 CAnimationVariable (使用 CAnimationVariable::GetParentAnimationObject) からオブジェクトのイベントと親アニメーションを取得する必要性を処理するときに、リレーションシップを知ることが便利な場合がありますに。  
  
##  <a name="setuserdata"></a>  CAnimationBaseObject::SetUserData  
 ユーザー定義データを設定します。  
  
```  
void SetUserData (DWORD dwUserData);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwUserData*  
 カスタム データを指定します。  
  
### <a name="remarks"></a>Remarks  
 アニメーション オブジェクトとカスタム データを関連付けるには、このメソッドを使用します。 このデータを取得できます後で実行時に GetUserData で。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
