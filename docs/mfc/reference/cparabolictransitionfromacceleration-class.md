---
title: CParabolicTransitionFromAcceleration クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::Create
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblAcceleration
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CParabolicTransitionFromAcceleration::m_dblFinalVelocity
dev_langs:
- C++
helpviewer_keywords:
- CParabolicTransitionFromAcceleration [MFC], CParabolicTransitionFromAcceleration
- CParabolicTransitionFromAcceleration [MFC], Create
- CParabolicTransitionFromAcceleration [MFC], m_dblAcceleration
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalValue
- CParabolicTransitionFromAcceleration [MFC], m_dblFinalVelocity
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e4db0932b2a2171e47c1b8e6c42a84fa100c9e9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389357"
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
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](#cparabolictransitionfromacceleration)|放物線加速遷移を構築し、指定されたパラメーターで初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CParabolicTransitionFromAcceleration::m_dblAcceleration](#m_dblacceleration)|移行中にアニメーション変数の加速します。|
|[CParabolicTransitionFromAcceleration::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|
|[CParabolicTransitionFromAcceleration::m_dblFinalVelocity](#m_dblfinalvelocity)|遷移の終点のアニメーション変数の速度。|

## <a name="remarks"></a>Remarks

アニメーション変数の値は、放物線加速遷移では中、指定した速度で終了する最終的な値に初期値から変更します。 変数が最終的な値に達するの高速化の速度を指定することでどの程度の速度を制御できます。 すべての遷移が自動的にクリアされますが、お勧めするそれらに割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、null を指定し、まで、CAnimationController::AnimateGroup によって作成されます。 影響を与えませんこの COM オブジェクトの作成後は、メンバー変数を変更します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

##  <a name="cparabolictransitionfromacceleration"></a>  CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration

放物線加速遷移を構築し、指定されたパラメーターで初期化します。

```
CParabolicTransitionFromAcceleration(
    DOUBLE dblFinalValue,
    DOUBLE dblFinalVelocity,
    DOUBLE dblAcceleration);
```

### <a name="parameters"></a>パラメーター

*dblFinalValue*<br/>
移行の最後にアニメーション変数の値。

*dblFinalVelocity*<br/>
遷移の終点のアニメーション変数の速度。

*dblAcceleration*<br/>
移行中にアニメーション変数の加速します。

##  <a name="create"></a>  CParabolicTransitionFromAcceleration::Create

カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* /* not used */);
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
標準的な遷移の作成を担当する遷移ライブラリへのポインター。

### <a name="return-value"></a>戻り値

移行が正常に作成された場合は TRUE。それ以外の場合は FALSE です。

##  <a name="m_dblacceleration"></a>  CParabolicTransitionFromAcceleration::m_dblAcceleration

移行中にアニメーション変数の加速します。

```
DOUBLE m_dblAcceleration;
```

##  <a name="m_dblfinalvalue"></a>  CParabolicTransitionFromAcceleration::m_dblFinalValue

移行の最後にアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_dblfinalvelocity"></a>  CParabolicTransitionFromAcceleration::m_dblFinalVelocity

遷移の終点のアニメーション変数の速度。

```
DOUBLE m_dblFinalVelocity;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
