---
title: CParabolicTransitionFromAcceleration クラス
ms.date: 11/04/2016
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
ms.openlocfilehash: 0aa5831e2262602ee46bd69031e5927a86b978e1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364089"
---
# <a name="cparabolictransitionfromacceleration-class"></a>CParabolicTransitionFromAcceleration クラス

放物線加速遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CParabolicTransitionFromAcceleration : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[加速から切り離す遷移::加速からのCPar同化トランジション](#cparabolictransitionfromacceleration)|放物線加速遷移を構築し、指定したパラメータで初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[加速から切り離す::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[加速から切り離す::m_dblAcceleration](#m_dblacceleration)|トランジション中のアニメーション変数の加速度。|
|[加速から切り離 m_dblFinalValueす](#m_dblfinalvalue)|トランジションの終了時のアニメーション変数の値。|
|[加速から切り離す::m_dblFinalVelocity](#m_dblfinalvelocity)|トランジションの最後のアニメーション変数の速度。|

## <a name="remarks"></a>解説

放物線加速の遷移中に、アニメーション変数の値が初期値から指定された速度で終わる最終値に変化します。 加速の速度を指定することで、変数が最終的な値に達する速さを制御できます。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[加速から切り離す](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cparabolictransitionfromaccelerationcparabolictransitionfromacceleration"></a><a name="cparabolictransitionfromacceleration"></a>加速から切り離す遷移::加速からのCPar同化トランジション

放物線加速遷移を構築し、指定したパラメータで初期化します。

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>パラメーター

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

*dbl最終速度*<br/>
トランジションの最後のアニメーション変数の速度。

*dblアクセラレーション*<br/>
トランジション中のアニメーション変数の加速度。

## <a name="cparabolictransitionfromaccelerationcreate"></a><a name="create"></a>加速から切り離す::作成

カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移の作成を担当する遷移ライブラリへのポインター。

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cparabolictransitionfromaccelerationm_dblacceleration"></a><a name="m_dblacceleration"></a>加速から切り離す::m_dblAcceleration

トランジション中のアニメーション変数の加速度。

```
DOUBLE m_dblAcceleration;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>加速から切り離 m_dblFinalValueす

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="cparabolictransitionfromaccelerationm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>加速から切り離す::m_dblFinalVelocity

トランジションの最後のアニメーション変数の速度。

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
