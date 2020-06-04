---
title: CSinusoidalTransitionFromRange クラス
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::CSinusoidalTransitionFromRange
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMaximumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_dblMinimumValue
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_period
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromRange::m_slope
helpviewer_keywords:
- CSinusoidalTransitionFromRange [MFC], CSinusoidalTransitionFromRange
- CSinusoidalTransitionFromRange [MFC], Create
- CSinusoidalTransitionFromRange [MFC], m_dblMaximumValue
- CSinusoidalTransitionFromRange [MFC], m_dblMinimumValue
- CSinusoidalTransitionFromRange [MFC], m_duration
- CSinusoidalTransitionFromRange [MFC], m_period
- CSinusoidalTransitionFromRange [MFC], m_slope
ms.assetid: 8b66a729-5f10-431a-b055-e3600d0065da
ms.openlocfilehash: 0612a4b365b928d3c9be6d76168a76b4ee1caa85
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318256"
---
# <a name="csinusoidaltransitionfromrange-class"></a>CSinusoidalTransitionFromRange クラス

振幅が指定の範囲である正弦波範囲遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CSinusoidalTransitionFromRange : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cシヌイダルトランジションから範囲::Cシヌイダルトランジションから範囲](#csinusoidaltransitionfromrange)|遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cシヌイダルトランジションから範囲::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cシヌオイドアルトランジションから範囲::m_dblMaximumValue](#m_dblmaximumvalue)|正弦波のピークにおけるアニメーション変数の値。|
|[Cシヌイダルトランジションから範囲::m_dblMinimumValue](#m_dblminimumvalue)|正弦波の谷におけるアニメーション変数の値。|
|[Cシヌイダルトランジションから範囲::m_duration](#m_duration)|トランジションの期間。|
|[Cシヌイダルトランジションから範囲::m_period](#m_period)|正弦波の振動の秒単位の周期。|
|[Cシヌイダルトランジションから範囲::m_slope](#m_slope)|遷移の開始時の傾斜。|

## <a name="remarks"></a>解説

アニメーション変数の値は、指定された最小値と最大値の間で、指定された終弦波範囲遷移の全期間にわたって変動します。 勾配パラメータは、他のパラメータで指定された 2 つの正音波の間であいまいさを解消するために使用されます。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[シヌイオダルトランジションフロルレンジ](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a>Cシヌイダルトランジションから範囲::作成

カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移の作成を担当する遷移ライブラリへのポインター。

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a>Cシヌイダルトランジションから範囲::Cシヌイダルトランジションから範囲

遷移オブジェクトを構築します。

```
CSinusoidalTransitionFromRange(
    UI_ANIMATION_SECONDS duration,
    DOUBLE dblMinimumValue,
    DOUBLE dblMaximumValue,
    UI_ANIMATION_SECONDS period,
    UI_ANIMATION_SLOPE slope);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
トランジションの期間。

*最小値*<br/>
正弦波の谷におけるアニメーション変数の値。

*最大値*<br/>
正弦波のピークにおけるアニメーション変数の値。

*期間*<br/>
正弦波の振動の秒単位の周期。

*斜面*<br/>
遷移の開始時の傾斜。

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a>Cシヌオイドアルトランジションから範囲::m_dblMaximumValue

正弦波のピークにおけるアニメーション変数の値。

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a>Cシヌイダルトランジションから範囲::m_dblMinimumValue

正弦波の谷におけるアニメーション変数の値。

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a>Cシヌイダルトランジションから範囲::m_duration

トランジションの期間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a>Cシヌイダルトランジションから範囲::m_period

正弦波の振動の秒単位の周期。

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a>Cシヌイダルトランジションから範囲::m_slope

遷移の開始時の傾斜。

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
