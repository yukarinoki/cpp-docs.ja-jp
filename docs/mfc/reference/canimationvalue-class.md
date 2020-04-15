---
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
ms.openlocfilehash: 0437f0fc66f64ccb99157330154bf5aa4b5666b3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321971"
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
|[C アニメーション値::C アニメーション値](#canimationvalue)|オーバーロードされます。 オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cアニメーション値::トランジションの追加](#addtransition)|値に適用する遷移を追加します。|
|[値を取得します。](#getvalue)|オーバーロードされます。 現在の値を取得します。|
|[値を取得します。](#getvariable)|カプセル化されたアニメーション変数へのアクセスを提供します。|
|[値::デフォルト値を設定します。](#setdefaultvalue)|既定値を設定します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[アニメーション値::アニメーション変数リスト](#getanimationvariablelist)|カプセル化されたアニメーション変数をリストに入れます。 (C[アニメーションベースオブジェクト](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)をオーバーライドします。.|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[2 つの演算子を使用します。](#operator_double)|C アニメーション値と倍精度浮動小数点数型の間の変換を提供します。|
|[値::オペレーター INT32](#operator_int32)|C アニメーション値と INT32 の間の変換を提供します。|
|[値::演算子=](#operator_eq)|オーバーロードされます。 C アニメーション値に INT32 値を割り当てます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[アニメーション値::m_value](#m_value)|アニメーション値を表すカプセル化されたアニメーション変数。|

## <a name="remarks"></a>解説

クラスは、単一の CAnimationVariable オブジェクトをカプセル化し、アプリケーションで 1 つのアニメーション値を表すことができます。 たとえば、このクラスは、アニメーション化された透明度(フェード効果)、角度(オブジェクトを回転する場合)、またはアニメーション化された単一の値に応じてアニメーションを作成する必要がある場合に使用できます。 アプリケーションでこのクラスを使用するには、このクラスのオブジェクトをインスタンス化し、CAnimationController::AddAnimationObject を使用してアニメーション コントローラに追加し、値に適用される各遷移の AddTransition を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[オブジェクト](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a>Cアニメーション値::トランジションの追加

値に適用する遷移を追加します。

```
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>パラメーター

*移行*<br/>
遷移オブジェクトへのポインター。

### <a name="remarks"></a>解説

アニメーション変数に適用する遷移の内部リストに遷移を追加します。 遷移を追加しても、すぐには適用されず、内部リストに保存されます。 CAnimationController::AnimateGroup を呼び出すと、トランジションが適用されます (特定の値のストーリーボードに追加されます)。

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a>C アニメーション値::C アニメーション値

オブジェクトを構築します。

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>パラメーター

*既定の値*<br/>
既定値を指定します。

*グループ ID*<br/>
グループ ID を指定します。

*オブジェクト ID*<br/>
オブジェクト ID を指定します。

*データ*<br/>
ユーザー定義データを指定します。

### <a name="remarks"></a>解説

既定のプロパティを持つ CAnimationValue オブジェクトを構築します: 既定値、グループ ID とオブジェクト ID は 0 に設定されます。

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a>アニメーション値::アニメーション変数リスト

カプセル化されたアニメーション変数をリストに入れます。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>パラメーター

*Lst*<br/>
関数が返されるときに、アニメーション化された値を表す CAnimationVariable へのポインターが含まれています。

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a>値を取得します。

現在の値を取得します。

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>パラメーター

*値上げ*<br/>
出力。 関数が返す場合、その関数にはアニメーション変数の現在の値が含まれます。

*n値*<br/>
出力。 関数が返す場合、その関数にはアニメーション変数の現在の値が含まれます。

### <a name="return-value"></a>戻り値

現在の値が正常に取得された場合は TRUE。それ以外の場合は FALSE。

### <a name="remarks"></a>解説

現在の値を取得します。 この実装は、カプセル化された COM オブジェクトを呼び出し、呼び出しが失敗した場合、このメソッドは、以前にコンストラクターまたは SetDefaultValue で設定された既定値を返します。

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a>値を取得します。

カプセル化されたアニメーション変数へのアクセスを提供します。

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>戻り値

カプセル化されたアニメーション変数への参照。

### <a name="remarks"></a>解説

このメソッドは、カプセル化されたアニメーション変数にアクセスするために使います。 CAnimationVariable から、基になる IUIAnimationVariable オブジェクトにアクセスできます。

## <a name="canimationvaluem_value"></a><a name="m_value"></a>アニメーション値::m_value

アニメーション値を表すカプセル化されたアニメーション変数。

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a>2 つの演算子を使用します。

C アニメーション値と倍精度浮動小数点数型の間の変換を提供します。

```
operator DOUBLE();
```

### <a name="return-value"></a>戻り値

アニメーション値の現在の値。

### <a name="remarks"></a>解説

C アニメーション値と倍精度浮動小数点数型の間の変換を提供します。 このメソッドは、内部的に GetValue を呼び出し、エラーをチェックしません。 GetValue が失敗した場合、戻り値には、以前にコンストラクターまたは SetDefaultValue で設定された既定値が含まれます。

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a>値::オペレーター INT32

C アニメーション値と INT32 の間の変換を提供します。

```
operator INT32();
```

### <a name="return-value"></a>戻り値

アニメーション値の現在の値を整数で指定します。

### <a name="remarks"></a>解説

C アニメーション値と INT32 の間の変換を提供します。 このメソッドは、内部的に GetValue を呼び出し、エラーをチェックしません。 GetValue が失敗した場合、戻り値には、以前にコンストラクターまたは SetDefaultValue で設定された既定値が含まれます。

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a>値::演算子=

ダブル値を C アニメーション値に割り当てます。

```
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>パラメーター

*ドブルヴァル*<br/>
アニメーション値に割り当てる値を指定します。

*nVal*<br/>
アニメーション値に割り当てる値を指定します。

### <a name="remarks"></a>解説

ダブル値を C アニメーション値に割り当てます。 この値は、カプセル化されたアニメーション変数の既定値として設定されます。 このアニメーション オブジェクトをイベントにサブスクライブした場合 (ValueChanged または整数値変更)、これらのイベントを再度有効にする必要があります。

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a>値::デフォルト値を設定します。

既定値を設定します。

```
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>パラメーター

*既定の値*<br/>
既定値を指定します。

### <a name="remarks"></a>解説

このメソッドは、既定値を設定するために使います。 アニメーションが開始されていない場合や、基になる COM オブジェクトが作成されていない場合は、既定値がアプリケーションに返されます。 CAnimationVarible にカプセル化された基になる COM オブジェクトが既に作成されている場合、このメソッドはそれを再作成するため、再びメソッドを呼び出す必要があります。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
