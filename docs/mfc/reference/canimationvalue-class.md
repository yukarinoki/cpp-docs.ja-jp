---
title: CAnimationValue クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
dev_langs:
- C++
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 923b1b74a50fd13a57c1d9c7696f81acb28453e3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="canimationvalue-class"></a>CAnimationValue クラス
1 つの値を持つアニメーション オブジェクトの機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](#canimationvalue)|オーバーロードされます。 CAnimationValue オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](#addtransition)|値に適用するへの遷移を追加します。|  
|[CAnimationValue::GetValue](#getvalue)|オーバーロードされます。 現在の値を取得します。|  
|[CAnimationValue::GetVariable](#getvariable)|アニメーションをカプセル化された変数へのアクセスを提供します。|  
|[CAnimationValue::SetDefaultValue](#setdefaultvalue)|既定値を設定します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](#getanimationvariablelist)|一覧にカプセル化されたアニメーション変数を追加します。 (上書き[CAnimationBaseObject::GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist))。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationValue::operator 倍](#operator_double)|CAnimationValue と DOUBLE との間の変換を提供します。|  
|[CAnimationValue::operator INT32](#operator_int32)|CAnimationValue と INT32 との間の変換を提供します。|  
|[CAnimationValue::operator =](#operator_eq)|オーバーロードされます。 CAnimationValue に INT32 値を割り当てます。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAnimationValue::m_value](#m_value)|アニメーションの値を表すアニメーションをカプセル化された変数です。|  
  
## <a name="remarks"></a>コメント  
 CAnimationValue クラスは、1 つの CAnimationVariable オブジェクトをカプセル化して、1 つのアニメーション化された値をアプリケーションで表すことができます。 アニメーションの透明度 (フェード効果) の角度 (オブジェクトの回転) のこのクラスを使用するなど、それ以外の場合、1 つのアニメーション化された値に応じてアニメーションを作成する必要がある場合。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化、CAnimationController::AddAnimationObject を使用してアニメーション コント ローラーに追加してだけ値に適用される各移行につき AddTransition の呼び出しです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 `CAnimationValue`
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="addtransition"></a>  CAnimationValue::AddTransition  
 値に適用するへの遷移を追加します。  
  
```  
void AddTransition(CBaseTransition* pTransition);
```  
  
### <a name="parameters"></a>パラメーター  
 `pTransition`  
 移行のオブジェクトへのポインター。  
  
### <a name="remarks"></a>コメント  
 アニメーション変数に適用する遷移の内部リストに遷移を追加するには、この関数を呼び出します。 切り替え効果を追加すると、いないすぐに適用されるとなり、内部の一覧に格納されています。 遷移を (特定の値のストーリー ボードへの追加) に適用されます CAnimationController::AnimateGroup を呼び出すとします。  
  
##  <a name="canimationvalue"></a>  CAnimationValue::CAnimationValue  
 CAnimationValue オブジェクトを構築します。  
  
```  
CAnimationValue();

 
CAnimationValue(
    DOUBLE dblDefaultValue,  
    UINT32 nGroupID,  
    UINT32 nObjectID = (UINT32)-1,  
    DWORD dwUserData = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblDefaultValue`  
 既定値を指定します。  
  
 `nGroupID`  
 グループ ID を指定します  
  
 `nObjectID`  
 オブジェクト ID を指定します  
  
 `dwUserData`  
 ユーザー定義データを指定します。  
  
### <a name="remarks"></a>コメント  
 既定のプロパティを持つ CAnimationValue オブジェクトを構築します。 グループ ID とオブジェクト ID の既定値は 0 に設定されます。  
  
##  <a name="getanimationvariablelist"></a>  CAnimationValue::GetAnimationVariableList  
 一覧にカプセル化されたアニメーション変数を追加します。  
  
```  
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*, 
    CAnimationVariable*>& lst);
```  
  
### <a name="parameters"></a>パラメーター  
 `lst`  
 関数から返されたときに、アニメーションの値を表す CAnimationVariable へのポインターを格納します。  
  
##  <a name="getvalue"></a>  CAnimationValue::GetValue  
 現在の値を取得します。  
  
```  
BOOL GetValue(DOUBLE& dblValue);  
BOOL GetValue(INT32& nValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblValue`  
 出力です。 関数が戻るときに、アニメーション変数の現在の値が含まれています。  
  
 `nValue`  
 出力です。 関数が戻るときに、アニメーション変数の現在の値が含まれています。  
  
### <a name="return-value"></a>戻り値  
 現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。  
  
### <a name="remarks"></a>コメント  
 現在の値を取得するには、この関数を呼び出します。 この実装は、カプセル化された COM オブジェクトを呼び出すし、呼び出しが失敗した場合、このメソッドはコンス トラクター、または SetDefaultValue で設定されている既定値を返します。  
  
##  <a name="getvariable"></a>  CAnimationValue::GetVariable  
 アニメーションをカプセル化された変数へのアクセスを提供します。  
  
```  
CAnimationVariable& GetVariable();
```  
  
### <a name="return-value"></a>戻り値  
 アニメーションをカプセル化された変数への参照。  
  
### <a name="remarks"></a>コメント  
 アニメーションをカプセル化された変数にアクセスするのにには、このメソッドを使用します。 CAnimationVariable からポインターが NULL でもかまいませんアニメーション変数が作成されていない場合、基になる IUIAnimationVariable オブジェクトへのアクセスを取得します。  
  
##  <a name="m_value"></a>  CAnimationValue::m_value  
 アニメーションの値を表すアニメーションをカプセル化された変数です。  
  
```  
CAnimationVariable m_value;  
```  
  
##  <a name="operator_double"></a>  CAnimationValue::operator 倍  
 CAnimationValue と DOUBLE との間の変換を提供します。  
  
```  
operator DOUBLE();
```   
  
### <a name="return-value"></a>戻り値  
 アニメーションの値の現在の値。  
  
### <a name="remarks"></a>コメント  
 CAnimationValue と DOUBLE との間の変換を提供します。 このメソッドは内部的に GetValue を呼び出して、エラーをチェックしません。 GetValue が失敗した場合、返される値は、コンス トラクター、または SetDefaultValue で設定した既定値が含まれます。  
  
##  <a name="operator_int32"></a>  CAnimationValue::operator INT32  
 CAnimationValue と INT32 との間の変換を提供します。  
  
```  
operator INT32();
```   
  
### <a name="return-value"></a>戻り値  
 整数値として値をアニメーションの現在の値。  
  
### <a name="remarks"></a>コメント  
 CAnimationValue と INT32 との間の変換を提供します。 このメソッドは内部的に GetValue を呼び出して、エラーをチェックしません。 GetValue が失敗した場合、返される値は、コンス トラクター、または SetDefaultValue で設定した既定値が含まれます。  
  
##  <a name="operator_eq"></a>  CAnimationValue::operator =  
 CAnimationValue に double 型の値を割り当てます。  
  
```  
void operator=(DOUBLE dblVal);  
void operator=(INT32 nVal);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblVal`  
 アニメーションの値に割り当てられる値を指定します。  
  
 `nVal`  
 アニメーションの値に割り当てられる値を指定します。  
  
### <a name="remarks"></a>コメント  
 CAnimationValue に double 型の値を割り当てます。 この値は、カプセル化されたアニメーション変数の既定値として設定されます。 このアニメーション オブジェクト (ValueChanged または IntegerValueChanged) イベントをサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。  
  
##  <a name="setdefaultvalue"></a>  CAnimationValue::SetDefaultValue  
 既定値を設定します。  
  
```  
void SetDefaultValue(DOUBLE dblDefaultValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblDefaultValue`  
 既定値を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用すると、既定値を設定できます。 既定値は、アニメーションが開始されていない、基になる COM オブジェクトが作成されていないときに、アプリケーションに返されます。 CAnimationVarible にカプセル化された基になる COM オブジェクトが既に作成されて場合、は、このメソッドで再作成、したがって、もう一度 EnableValueChanged/EnableIntegerValueChanged メソッドの呼び出しにする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
