---
title: CAnimationVariable クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::CAnimationVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationVariable::ApplyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::ClearTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::Create
- AFXANIMATIONCONTROLLER/CAnimationVariable::CreateTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableIntegerValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::EnableValueChangedEvent
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::SetParentAnimationObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_bAutodestroyTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_dblDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_lstTransitions
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_pParentObject
- AFXANIMATIONCONTROLLER/CAnimationVariable::m_variable
dev_langs:
- C++
helpviewer_keywords:
- CAnimationVariable [MFC], CAnimationVariable
- CAnimationVariable [MFC], AddTransition
- CAnimationVariable [MFC], ApplyTransitions
- CAnimationVariable [MFC], ClearTransitions
- CAnimationVariable [MFC], Create
- CAnimationVariable [MFC], CreateTransitions
- CAnimationVariable [MFC], EnableIntegerValueChangedEvent
- CAnimationVariable [MFC], EnableValueChangedEvent
- CAnimationVariable [MFC], GetDefaultValue
- CAnimationVariable [MFC], GetParentAnimationObject
- CAnimationVariable [MFC], GetValue
- CAnimationVariable [MFC], GetVariable
- CAnimationVariable [MFC], SetDefaultValue
- CAnimationVariable [MFC], SetParentAnimationObject
- CAnimationVariable [MFC], m_bAutodestroyTransitions
- CAnimationVariable [MFC], m_dblDefaultValue
- CAnimationVariable [MFC], m_lstTransitions
- CAnimationVariable [MFC], m_pParentObject
- CAnimationVariable [MFC], m_variable
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: efaf47ef434e4f6c63b937d1f360851fa9826e3d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355955"
---
# <a name="canimationvariable-class"></a>CAnimationVariable クラス
アニメーション変数を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationVariable;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](#canimationvariable)|アニメーション変数のオブジェクトを構築します。|  
|[CAnimationVariable:: ~ CAnimationVariable](#canimationvariable__~canimationvariable)|デストラクターです。 CAnimationVariable オブジェクトが破棄されるときに呼び出されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](#addtransition)|遷移を追加します。|  
|[CAnimationVariable::ApplyTransitions](#applytransitions)|ストーリー ボードには、内部のリストから、切り替え効果を追加します。|  
|[CAnimationVariable::ClearTransitions](#cleartransitions)|遷移をクリアします。|  
|[CAnimationVariable::Create](#create)|基になるアニメーション変数 COM オブジェクトを作成します。|  
|[CAnimationVariable::CreateTransitions](#createtransitions)|このアニメーションの変数に適用されるすべての遷移を作成します。|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](#enableintegervaluechangedevent)|有効または IntegerValueChanged イベントを無効にします。|  
|[CAnimationVariable::EnableValueChangedEvent](#enablevaluechangedevent)|有効または ValueChanged イベントを無効にします。|  
|[CAnimationVariable::GetDefaultValue](#getdefaultvalue)|既定値を返します。|  
|[CAnimationVariable::GetParentAnimationObject](#getparentanimationobject)|親を返しますのアニメーション オブジェクト。|  
|[CAnimationVariable::GetValue](#getvalue)|オーバーロードされます。 アニメーション変数の現在の値を返します。|  
|[CAnimationVariable::GetVariable](#getvariable)|IUIAnimationVariable COM オブジェクトへのポインターを返します。|  
|[CAnimationVariable::SetDefaultValue](#setdefaultvalue)|既定値を設定し、IUIAnimationVariable COM オブジェクトを解放します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](#setparentanimationobject)|アニメーション変数とアニメーション オブジェクト間のリレーションシップを設定します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::m_bAutodestroyTransitions](#m_bautodestroytransitions)|関連する transition オブジェクトを削除するかどうかを指定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationVariable::m_dblDefaultValue](#m_dbldefaultvalue)|IUIAnimationVariable に反映される既定の値を指定します。|  
|[CAnimationVariable::m_lstTransitions](#m_lsttransitions)|このアニメーション変数をアニメーション化する遷移の一覧が含まれています。|  
|[CAnimationVariable::m_pParentObject](#m_pparentobject)|このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。|  
|[CAnimationVariable::m_variable](#m_variable)|IUIAnimationVariable COM オブジェクトへのポインターを格納します。 COM オブジェクトは、まだ作成されていない場合、または作成に失敗した場合は NULL です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationVariable クラスは、IUIAnimationVariable COM オブジェクトをカプセル化します。 ストーリー ボードのアニメーションの変数に適用する遷移の一覧も保持します。 CAnimationVariable オブジェクトは、アプリケーション アニメーション化された値、ポイント、サイズ、色、および四角形で表すことができるアニメーション オブジェクトに埋め込まれます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CAnimationVariable`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="_dtorcanimationvariable"></a>  CAnimationVariable:: ~ CAnimationVariable  
 デストラクターです。 CAnimationVariable オブジェクトが破棄されるときに呼び出されます。  
  
```  
virtual ~CAnimationVariable();
```  
  
##  <a name="addtransition"></a>  CAnimationVariable::AddTransition  
 遷移を追加します。  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTransition`  
 追加する遷移へのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは切り替え効果をアニメーション変数に適用する遷移の内部リストに追加します。 アニメーションがスケジュールされているときに、この一覧をクリアする必要があります。  
  
##  <a name="applytransitions"></a>  CAnimationVariable::ApplyTransitions  
 ストーリー ボードには、内部のリストから、切り替え効果を追加します。  
  
```  
void ApplyTransitions(
    CAnimationController* pController,  
    IUIAnimationStoryboard* pStoryboard,  
    BOOL bDependOnKeyframes);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親アニメーション コント ローラーへのポインター。  
  
 `pStoryboard`  
 ストーリー ボードへのポインター。  
  
 `bDependOnKeyframes`  
 場合は TRUE、このメソッドは、キーフレームに依存する切り替えを追加する必要があります。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、ストーリー ボードには、内部のリストから、切り替え効果を追加します。 呼び出されます、最上位レベルのコードから複数回せずキーフレームに依存してキーフレームに依存する切り替え効果を追加する切り替えを追加します。 基になるアニメーション変数の COM オブジェクトが作成されていない場合、このメソッドをこの段階で作成します。  
  
##  <a name="canimationvariable"></a>  CAnimationVariable::CAnimationVariable  
 アニメーション変数のオブジェクトを構築します。  
  
```  
CAnimationVariable(DOUBLE dblDefaultValue = 0.0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblDefaultValue`  
 既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数オブジェクトを構築し、その既定値を設定します。 既定値は、変数がアニメーション化されていないか、またはアニメーション化することはできませんとに使用されます。  
  
##  <a name="cleartransitions"></a>  CAnimationVariable::ClearTransitions  
 遷移をクリアします。  
  
```  
void ClearTransitions(BOOL bAutodestroy);
```  
  
### <a name="parameters"></a>パラメーター  
 `bAutodestroy`  
 このメソッドが transition オブジェクトを削除するかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、すべての遷移を遷移の内部の一覧から削除します。 BAutodestroy が true の場合、または、m_bAutodestroyTransitions が TRUE の場合、遷移は削除されます。 それ以外の場合、呼び出し元は、transition オブジェクトを解放する必要があります。  
  
##  <a name="create"></a>  CAnimationVariable::Create  
 基になるアニメーション変数 COM オブジェクトを作成します。  
  
```  
virtual BOOL Create(IUIAnimationManager* pManager);
```  
  
### <a name="parameters"></a>パラメーター  
 `pManager`  
 アニメーション マネージャーへのポインター。  
  
### <a name="return-value"></a>戻り値  
 アニメーション変数が作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、基になるアニメーション変数の COM オブジェクトを作成し、その既定値を設定します。  
  
##  <a name="createtransitions"></a>  CAnimationVariable::CreateTransitions  
 このアニメーションの変数に適用されるすべての遷移を作成します。  
  
```  
BOOL CreateTransitions(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準的な遷移のライブラリを定義します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 このメソッドは遷移の変数の内部リストに追加されている遷移を作成する必要があるときにフレームワークによって呼び出されます。  
  
##  <a name="enableintegervaluechangedevent"></a>  CAnimationVariable::EnableIntegerValueChangedEvent  
 有効または IntegerValueChanged イベントを無効にします。  
  
```  
void EnableIntegerValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親のコント ローラーへのポインター。  
  
 `bEnable`  
 TRUE - 有効にするイベントを FALSE には、イベントを無効にします。  
  
### <a name="remarks"></a>コメント  
 ValueChanged イベントを有効にすると、フレームワークは CAnimationController::OnAnimationIntegerValueChanged 仮想メソッドを呼び出します。 このイベントを処理するために CAnimationController から派生したクラスでオーバーライドする必要があります。 アニメーション変数の整数値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="enablevaluechangedevent"></a>  CAnimationVariable::EnableValueChangedEvent  
 有効または ValueChanged イベントを無効にします。  
  
```  
void EnableValueChangedEvent (
    CAnimationController* pController,  
    BOOL bEnable);
```  
  
### <a name="parameters"></a>パラメーター  
 `pController`  
 親のコント ローラーへのポインター。  
  
 `bEnable`  
 TRUE - 有効にするイベントを FALSE には、イベントを無効にします。  
  
### <a name="remarks"></a>コメント  
 ValueChanged イベントを有効にすると、フレームワークは CAnimationController::OnAnimationValueChanged 仮想メソッドを呼び出します。 このイベントを処理するために CAnimationController から派生したクラスでオーバーライドする必要があります。 アニメーション変数の値が変更されるたびに、このメソッドが呼び出されます。  
  
##  <a name="getdefaultvalue"></a>  CAnimationVariable::GetDefaultValue  
 既定値を返します。  
  
```  
DOUBLE GetDefaultValue() const;  
```  
  
### <a name="return-value"></a>戻り値  
 既定値。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数の既定値を取得するのにには、この関数を使用します。 コンス トラクターまたは SetDefaultValue メソッドによって、既定値を設定できます。  
  
##  <a name="getparentanimationobject"></a>  CAnimationVariable::GetParentAnimationObject  
 親を返しますのアニメーション オブジェクト。  
  
```  
CAnimationBaseObject* GetParentAnimationObject();
```  
  
### <a name="return-value"></a>戻り値  
 それ以外の場合のリレーションシップが確立された場合に、親アニメーション オブジェクトへのポインターが NULL です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、親のアニメーション オブジェクト (コンテナー) へのポインターを取得する呼び出すことができます。  
  
##  <a name="getvalue"></a>  CAnimationVariable::GetValue  
 アニメーション変数の現在の値を返します。  
  
```  
HRESULT GetValue(DOUBLE& dblValue);  
HRESULT GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblValue`  
 アニメーション変数の現在の値。  
  
 `nValue`  
 アニメーション変数の現在の値。  
  
### <a name="return-value"></a>戻り値  
 値が正常に取得された、またはアニメーションの基になる変数が作成されていない場合は S_OK です。 それ以外の場合の HRESULT エラー コード。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数の現在の値を取得するこのメソッドを呼び出すことができます。 基になる COM オブジェクトが作成されていない場合 dblValue で関数が戻るときに、既定値が含まれます。  
  
##  <a name="getvariable"></a>  CAnimationVariable::GetVariable  
 IUIAnimationVariable COM オブジェクトへのポインターを返します。  
  
```  
IUIAnimationVariable* GetVariable();
```  
  
### <a name="return-value"></a>戻り値  
 IUIAnimationVariable COM オブジェクト、またはアニメーション変数が作成されていないまたは作成できない場合は NULL に有効なポインター。  
  
### <a name="remarks"></a>コメント  
 基になる IUIAnimationVariable COM オブジェクトにアクセスし、必要な場合は、そのメソッドを直接呼び出すには、この関数を使用します。  
  
##  <a name="m_bautodestroytransitions"></a>  CAnimationVariable::m_bAutodestroyTransitions  
 関連する transition オブジェクトを削除するかどうかを指定します。  
  
```  
BOOL m_bAutodestroyTransitions;  
```  
  
### <a name="remarks"></a>コメント  
 遷移の内部の一覧からが削除されるときに、transition オブジェクトの削除を強制する場合は true には、この値を設定します。 この値が FALSE の場合は、アプリケーションを呼び出すことにより、遷移を削除してください。 遷移の一覧が常に、アニメーションがスケジュールされている後にクリアされます。 既定値は FALSE です。  
  
##  <a name="m_dbldefaultvalue"></a>  CAnimationVariable::m_dblDefaultValue  
 IUIAnimationVariable に反映される既定の値を指定します。  
  
```  
DOUBLE m_dblDefaultValue;  
```  
  
##  <a name="m_lsttransitions"></a>  CAnimationVariable::m_lstTransitions  
 このアニメーション変数をアニメーション化する遷移の一覧が含まれています。  
  
```  
CObList m_lstTransitions;  
```  
  
##  <a name="m_pparentobject"></a>  CAnimationVariable::m_pParentObject  
 このアニメーション変数をカプセル化するアニメーション オブジェクトへのポインター。  
  
```  
CAnimationBaseObject* m_pParentObject;  
```  
  
##  <a name="m_variable"></a>  CAnimationVariable::m_variable  
 IUIAnimationVariable COM オブジェクトへのポインターを格納します。 COM オブジェクトは、まだ作成されていない場合、または作成に失敗した場合は NULL です。  
  
```  
ATL::CComPtr<IUIAnimationVariable> m_variable;  
```  
  
##  <a name="setdefaultvalue"></a>  CAnimationVariable::SetDefaultValue  
 既定値を設定し、IUIAnimationVariable COM オブジェクトを解放します。  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblDefaultValue`  
 新しい既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 既定値にリセットするのにには、このメソッドを使用します。 このメソッドは、解放、内部 IUIAnimationVariable COM オブジェクト、したがってアニメーション変数を作成し直すときに、基になる COM オブジェクトは、新しい既定値を取得します。 アニメーション変数を表す COM オブジェクトを作成していない場合、または変数がアニメーション化されていない場合、GetValue によって既定値が返されます。  
  
##  <a name="setparentanimationobject"></a>  CAnimationVariable::SetParentAnimationObject  
 アニメーション変数とアニメーション オブジェクト間のリレーションシップを設定します。  
  
```  
void SetParentAnimationObject(CAnimationBaseObject* pParentObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `pParentObject`  
 この変数を格納しているアニメーション オブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、アニメーション変数とそれをカプセル化するアニメーション オブジェクトの間の一対一のリレーションシップを確立するために内部的に呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
