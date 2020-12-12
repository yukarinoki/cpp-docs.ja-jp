---
description: '詳細情報: CCustomTransition クラス'
title: CCustomTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::CCustomTransition
- AFXANIMATIONCONTROLLER/CCustomTransition::Create
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::SetInitialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialValueSpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_bInitialVelocitySpecified
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomTransition::m_initialVelocity
- AFXANIMATIONCONTROLLER/CCustomTransition::m_pInterpolator
helpviewer_keywords:
- CCustomTransition [MFC], CCustomTransition
- CCustomTransition [MFC], Create
- CCustomTransition [MFC], SetInitialValue
- CCustomTransition [MFC], SetInitialVelocity
- CCustomTransition [MFC], m_bInitialValueSpecified
- CCustomTransition [MFC], m_bInitialVelocitySpecified
- CCustomTransition [MFC], m_initialValue
- CCustomTransition [MFC], m_initialVelocity
- CCustomTransition [MFC], m_pInterpolator
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
ms.openlocfilehash: 22c08cdcedc3a7cbdbe824ac1d98d62cfe810772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227664"
---
# <a name="ccustomtransition-class"></a>CCustomTransition クラス

カスタム遷移を実装します。

## <a name="syntax"></a>構文

```
class CCustomTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CCustomTransition:: CCustomTransition](#ccustomtransition)|カスタム遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCustomTransition:: Create](#create)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します。 ( [Cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create)をオーバーライドします)。|
|[CCustomTransition:: SetInitialValue](#setinitialvalue)|初期値を設定します。この値は、この遷移に関連付けられているアニメーション変数に適用されます。|
|[CCustomTransition:: SetInitialVelocity](#setinitialvelocity)|初期速度を設定します。これは、この遷移に関連付けられているアニメーション変数に適用されます。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CCustomTransition:: m_bInitialValueSpecified](#m_binitialvaluespecified)|SetInitialValue で初期値が指定されたかどうかを指定します。|
|[CCustomTransition:: m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|初期速度が SetInitialVelocity と共に指定されたかどうかを指定します。|
|[CCustomTransition:: m_initialValue](#m_initialvalue)|初期値を格納します。|
|[CCustomTransition:: m_initialVelocity](#m_initialvelocity)|初期速度を格納します。|
|[CCustomTransition:: m_pInterpolator](#m_pinterpolator)|カスタム interpolator へのポインターを格納します。|

## <a name="remarks"></a>解説

CCustomTransitions クラスを使用すると、開発者はカスタム遷移を実装できます。 これは標準の遷移として作成されて使用されますが、そのコンストラクターはカスタム interpolator へのポインターをパラメーターとして受け入れます。 カスタム遷移を使用するには、次の手順を実行します。 1. CCustomInterpolator からクラスを派生させ、少なくとも InterpolateValue メソッドを実装します。 2. カスタム interpolator オブジェクトの有効期間が、使用されるアニメーションの期間より長くなければならないことを確認します。 3. CCustomTransition オブジェクトを (operator new を使用して) インスタンス化し、コンストラクター内のカスタム interpolator へのポインターを渡します。 4. カスタム補間にこれらのパラメーターが必要な場合は、CCustomTransition:: SetInitialValue と CCustomTransition:: Setinitialvalue を呼び出します。 5. アニメーションオブジェクトの AddTransition メソッドにポインターを渡して、その値をカスタムアルゴリズムでアニメーション化する必要があります。 6. アニメーションオブジェクトの値が変更する必要がある場合、Windows アニメーション API は CCustomInterpolator で InterpolateValue (およびその他の関連するメソッド) を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a> CCustomTransition:: CCustomTransition

カスタム遷移オブジェクトを構築します。

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>パラメーター

*pInterpolator*<br/>
カスタム interpolator へのポインター。

## <a name="ccustomtransitioncreate"></a><a name="create"></a> CCustomTransition:: Create

遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* */,
    IUIAnimationTransitionFactory* pFactory);
```

### <a name="parameters"></a>パラメーター

*pFactory*<br/>
カスタム遷移の作成を担当する遷移ファクトリへのポインター。

### <a name="return-value"></a>戻り値

### <a name="remarks"></a>解説

また、このメソッドは、初期値と初期速度を、この遷移に関連付けられているアニメーション変数に適用するように設定することもできます。 このためには、フレームワークがカプセル化された遷移 COM オブジェクトを作成する前に SetInitialValue と Setinitialvalue を呼び出す必要があります (CAnimationController:: AnimateGroup を呼び出すと発生します)。

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a> CCustomTransition:: m_bInitialValueSpecified

SetInitialValue で初期値が指定されたかどうかを指定します。

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a> CCustomTransition:: m_bInitialVelocitySpecified

初期速度が SetInitialVelocity と共に指定されたかどうかを指定します。

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a> CCustomTransition:: m_initialValue

初期値を格納します。

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomTransition:: m_initialVelocity

初期速度を格納します。

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a> CCustomTransition:: m_pInterpolator

カスタム interpolator へのポインターを格納します。

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a> CCustomTransition:: SetInitialValue

初期値を設定します。この値は、この遷移に関連付けられているアニメーション変数に適用されます。

```cpp
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>パラメーター

*initialValue*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a> CCustomTransition:: SetInitialVelocity

初期速度を設定します。これは、この遷移に関連付けられているアニメーション変数に適用されます。

```cpp
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*初期速度*

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
