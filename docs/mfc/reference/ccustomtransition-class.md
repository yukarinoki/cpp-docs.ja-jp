---
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
ms.openlocfilehash: 8bdd0ebab0a6e4138e24edff38da9b444745f83a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369327"
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
|[カスタムトランジション::カスタムトランジション](#ccustomtransition)|カスタム遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カスタムトランジション::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|
|[を設定します。](#setinitialvalue)|このトランジションに関連付けられたアニメーション変数に適用される初期値を設定します。|
|[カスタムトランジション::セットイニシャルベロシティ](#setinitialvelocity)|この遷移に関連付けられたアニメーション変数に適用される初期速度を設定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[カスタムトランジション::m_bInitialValueSpecified](#m_binitialvaluespecified)|初期値が SetInitialValue で指定されたかどうかを指定します。|
|[カスタムトランジション::m_bInitialVelocitySpecified](#m_binitialvelocityspecified)|初期速度が SetInitialVelocity で指定されたかどうかを指定します。|
|[カスタムトランジション::m_initialValue](#m_initialvalue)|初期値を格納します。|
|[カスタムトランジション::m_initialVelocity](#m_initialvelocity)|初期速度を格納します。|
|[カスタムトランジション::m_pInterpolator](#m_pinterpolator)|カスタム補間器へのポインターを格納します。|

## <a name="remarks"></a>解説

CCustomTransitions クラスを使用すると、開発者はカスタム遷移を実装できます。 これは標準遷移として作成され使用されますが、コンストラクターはカスタム補間ツールへのポインターをパラメーターとして受け取ります。 カスタムトランジションを使用するには、次の手順を実行します。 CCustom 内挿器からクラスを派生し、少なくとも InterpolateValue メソッドを実装します。 2. カスタム補間オブジェクトの有効期間は、使用するアニメーションの継続時間よりも長くする必要があります。 3. CCustomTransition オブジェクトをインスタンス化 (演算子 new) し、コンストラクター内のカスタム補間にポインターを渡します。 4. これらのパラメーターがカスタム補間に必要な場合は、CCustomTransition::SetInitialValue と CCustomTransition::SetInitialVelocity を呼び出します。 5. カスタム の遷移へのポインターを、アニメーション オブジェクトの AddTransition メソッドに渡します。 6. アニメーション オブジェクトの値が変更される場合 Windows アニメーション API は、CCustom Interpolator でインターポレート値 (およびその他の関連するメソッド) を呼び出します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

`CCustomTransition`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="ccustomtransitionccustomtransition"></a><a name="ccustomtransition"></a>カスタムトランジション::カスタムトランジション

カスタム遷移オブジェクトを構築します。

```
CCustomTransition(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>パラメーター

*pインターポレーター*<br/>
カスタム補間器へのポインター。

## <a name="ccustomtransitioncreate"></a><a name="create"></a>カスタムトランジション::作成

カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。

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

このメソッドは、この遷移に関連付けられているアニメーション変数に適用される初期値と初期速度を設定することもできます。 このためには、フレームワークがカプセル化された遷移 COM オブジェクトを作成する前に SetInitialValue と SetInitialVelocity を呼び出す必要があります (CAnimationController::AnimateGroup を呼び出すと発生します)。

## <a name="ccustomtransitionm_binitialvaluespecified"></a><a name="m_binitialvaluespecified"></a>カスタムトランジション::m_bInitialValueSpecified

初期値が SetInitialValue で指定されたかどうかを指定します。

```
BOOL m_bInitialValueSpecified;
```

## <a name="ccustomtransitionm_binitialvelocityspecified"></a><a name="m_binitialvelocityspecified"></a>カスタムトランジション::m_bInitialVelocitySpecified

初期速度が SetInitialVelocity で指定されたかどうかを指定します。

```
BOOL m_bInitialVelocitySpecified;
```

## <a name="ccustomtransitionm_initialvalue"></a><a name="m_initialvalue"></a>カスタムトランジション::m_initialValue

初期値を格納します。

```
DOUBLE m_initialValue;
```

## <a name="ccustomtransitionm_initialvelocity"></a><a name="m_initialvelocity"></a>カスタムトランジション::m_initialVelocity

初期速度を格納します。

```
DOUBLE m_initialVelocity;
```

## <a name="ccustomtransitionm_pinterpolator"></a><a name="m_pinterpolator"></a>カスタムトランジション::m_pInterpolator

カスタム補間器へのポインターを格納します。

```
CCustomInterpolator* m_pInterpolator;
```

## <a name="ccustomtransitionsetinitialvalue"></a><a name="setinitialvalue"></a>を設定します。

このトランジションに関連付けられたアニメーション変数に適用される初期値を設定します。

```
void SetInitialValue(DOUBLE initialValue);
```

### <a name="parameters"></a>パラメーター

*初期値*

## <a name="ccustomtransitionsetinitialvelocity"></a><a name="setinitialvelocity"></a>カスタムトランジション::セットイニシャルベロシティ

この遷移に関連付けられたアニメーション変数に適用される初期速度を設定します。

```
void SetInitialVelocity(DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*初期速度*

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
