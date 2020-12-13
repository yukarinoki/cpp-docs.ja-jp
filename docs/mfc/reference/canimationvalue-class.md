---
description: '詳細情報: CAnimationValue クラス'
title: CAnimationValue クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: d704e83d286b4078af90d09edef35e8445d149d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336749"
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
|[CAnimationValue:: CAnimationValue](#canimationvalue)|オーバーロードされます。 CAnimationValue オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationValue:: AddTransition](#addtransition)|値に適用される遷移を追加します。|
|[CAnimationValue:: GetValue](#getvalue)|オーバーロードされます。 現在の値を取得します。|
|[CAnimationValue:: GetVariable](#getvariable)|カプセル化されたアニメーション変数へのアクセスを提供します。|
|[CAnimationValue:: SetDefaultValue](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[CAnimationValue:: Getアニメーション変数の一覧](#getanimationvariablelist)|カプセル化されたアニメーション変数をリストに配置します。 ( [Canimationbaseobject:: Getmenu変数 list](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします)。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[CAnimationValue:: operator DOUBLE](#operator_double)|CAnimationValue と DOUBLE の間の変換を提供します。|
|[CAnimationValue:: operator INT32](#operator_int32)|CAnimationValue と INT32 の間の変換を提供します。|
|[CAnimationValue:: operator =](#operator_eq)|オーバーロードされます。 CAnimationValue に INT32 値を割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CAnimationValue:: m_value](#m_value)|アニメーション値を表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

CAnimationValue クラスは、1つの Canimationvalue オブジェクトをカプセル化し、アプリケーション内で1つのアニメーション値を表すことができます。 たとえば、このクラスは、アニメーションの透明度 (フェード効果)、角度 (オブジェクトの回転)、またはアニメーションを1つのアニメーション化された値に応じて作成する必要がある場合に使用できます。 このクラスをアプリケーションで使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController:: Addanimation Object を使用してアニメーションコントローラーに追加し、値に適用される遷移ごとに AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a> CAnimationValue:: AddTransition

値に適用される遷移を追加します。

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>パラメーター

*pTransition*<br/>
遷移オブジェクトへのポインター。

### <a name="remarks"></a>解説

アニメーション変数に適用される遷移の内部リストに切り替え効果を追加するには、この関数を呼び出します。 切り替え効果を追加すると、すぐには適用されず、内部リストに格納されます。 CAnimationController:: AnimateGroup を呼び出すと、遷移が適用されます (特定の値のストーリーボードに追加されます)。

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a> CAnimationValue:: CAnimationValue

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

*dblDefaultValue*<br/>
既定値を指定します。

*nGroupID*<br/>
グループ ID を指定します。

*nObjectID*<br/>
オブジェクト ID を指定します。

*dwUserData*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

既定のプロパティを使用して CAnimationValue オブジェクトを構築します。既定値、グループ ID、およびオブジェクト ID は0に設定されます。

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationValue:: Getアニメーション変数の一覧

カプセル化されたアニメーション変数をリストに配置します。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*.lst*<br/>
関数から制御が戻るときに、アニメーション化された値を表す CAnimationVariable へのポインターが含まれています。

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a> CAnimationValue:: GetValue

現在の値を取得します。

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>パラメーター

*dblValue*<br/>
出力。 関数から制御が戻ったときに、アニメーション変数の現在の値が含まれています。

*N 値*<br/>
出力。 関数から制御が戻ったときに、アニメーション変数の現在の値が含まれています。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

現在の値を取得するには、この関数を呼び出します。 この実装は、カプセル化された COM オブジェクトを呼び出します。呼び出しが失敗した場合、このメソッドは、以前にコンストラクターまたは SetDefaultValue で設定された既定値を返します。

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a> CAnimationValue:: GetVariable

カプセル化されたアニメーション変数へのアクセスを提供します。

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>戻り値

カプセル化されたアニメーション変数への参照。

### <a name="remarks"></a>解説

このメソッドを使用して、カプセル化されたアニメーション変数にアクセスします。 CAnimationVariable から、基になる Iuianimation Variable オブジェクトにアクセスできます。アニメーション変数が作成されていない場合は、ポインターが NULL になることがあります。

## <a name="canimationvaluem_value"></a><a name="m_value"></a> CAnimationValue:: m_value

アニメーション値を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a> CAnimationValue:: operator DOUBLE

CAnimationValue と DOUBLE の間の変換を提供します。

```
operator DOUBLE();
```

### <a name="return-value"></a>戻り値

アニメーション値の現在の値。

### <a name="remarks"></a>解説

CAnimationValue と DOUBLE の間の変換を提供します。 このメソッドは、内部的に GetValue を呼び出し、エラーをチェックしません。 GetValue が失敗した場合、戻り値には、コンストラクターまたは SetDefaultValue で以前に設定した既定値が含まれます。

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a> CAnimationValue:: operator INT32

CAnimationValue と INT32 の間の変換を提供します。

```
operator INT32();
```

### <a name="return-value"></a>戻り値

アニメーション値の現在の値を整数として指定します。

### <a name="remarks"></a>解説

CAnimationValue と INT32 の間の変換を提供します。 このメソッドは、内部的に GetValue を呼び出し、エラーをチェックしません。 GetValue が失敗した場合、戻り値には、コンストラクターまたは SetDefaultValue で以前に設定した既定値が含まれます。

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a> CAnimationValue:: operator =

CAnimationValue に DOUBLE 値を割り当てます。

```cpp
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>パラメーター

*dblVal*<br/>
アニメーション値に割り当てる値を指定します。

*nVal*<br/>
アニメーション値に割り当てる値を指定します。

### <a name="remarks"></a>解説

CAnimationValue に DOUBLE 値を割り当てます。 この値は、カプセル化されたアニメーション変数の既定値として設定されます。 このアニメーションオブジェクトをイベント (ValueChanged または IntegerValueChanged) にサブスクライブしている場合は、これらのイベントを再度有効にする必要があります。

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationValue:: SetDefaultValue

既定値を設定します。

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>パラメーター

*dblDefaultValue*<br/>
既定値を指定します。

### <a name="remarks"></a>解説

既定値を設定するには、このメソッドを使用します。 アニメーションが開始されていない場合や、基になる COM オブジェクトが作成されていない場合は、アプリケーションに既定値が返されます。 基になる COM オブジェクトが既に作成されている場合、このメソッドはそれを再作成するため、EnableValueChanged/EnableIntegerValueChanged メソッドをもう一度呼び出す必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
