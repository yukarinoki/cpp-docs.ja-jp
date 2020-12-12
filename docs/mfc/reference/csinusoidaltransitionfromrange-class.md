---
description: '詳細情報: CSinusoidalTransitionFromRange クラス'
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
ms.openlocfilehash: 5d00b1cbfb8fe9b76a5a69bd1c9f10316ddf8141
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264571"
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
|[CSinusoidalTransitionFromRange:: CSinusoidalTransitionFromRange](#csinusoidaltransitionfromrange)|遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSinusoidalTransitionFromRange:: Create](#create)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します。 ( [Cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create)をオーバーライドします)。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CSinusoidalTransitionFromRange:: m_dblMaximumValue](#m_dblmaximumvalue)|決まる正弦波 wave のピーク時のアニメーション変数の値。|
|[CSinusoidalTransitionFromRange:: m_dblMinimumValue](#m_dblminimumvalue)|決まる正弦波 wave の trough にあるアニメーション変数の値。|
|[CSinusoidalTransitionFromRange:: m_duration](#m_duration)|遷移の継続時間。|
|[CSinusoidalTransitionFromRange:: m_period](#m_period)|決まる正弦波波の振幅の期間 (秒単位)。|
|[CSinusoidalTransitionFromRange:: m_slope](#m_slope)|遷移の開始時の傾斜。|

## <a name="remarks"></a>解説

アニメーション変数の値は、決まる正弦波範囲遷移の全期間において、指定された最小値と最大値の間で変動します。 傾きパラメーターは、他のパラメーターで指定されている2つの正弦波を明確に区別するために使用されます。 すべての遷移は自動的にクリアされるため、operator new を使用して割り当てることをお勧めします。 カプセル化された IuiAnimateGroup 遷移 COM オブジェクトは、次に NULL になるまで、CAnimationController:: によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても効果はありません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromRange](../../mfc/reference/csinusoidaltransitionfromrange-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromrangecreate"></a><a name="create"></a> CSinusoidalTransitionFromRange:: Create

遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
遷移ライブラリへのポインター。これは、標準遷移の作成を担当します。

### <a name="return-value"></a>戻り値

移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="csinusoidaltransitionfromrangecsinusoidaltransitionfromrange"></a><a name="csinusoidaltransitionfromrange"></a> CSinusoidalTransitionFromRange:: CSinusoidalTransitionFromRange

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

*duration*<br/>
遷移の継続時間。

*dblMinimumValue*<br/>
決まる正弦波 wave の trough にあるアニメーション変数の値。

*dblMaximumValue*<br/>
決まる正弦波 wave のピーク時のアニメーション変数の値。

*前期*<br/>
決まる正弦波波の振幅の期間 (秒単位)。

*傾斜*<br/>
遷移の開始時の傾斜。

## <a name="csinusoidaltransitionfromrangem_dblmaximumvalue"></a><a name="m_dblmaximumvalue"></a> CSinusoidalTransitionFromRange:: m_dblMaximumValue

決まる正弦波 wave のピーク時のアニメーション変数の値。

```
DOUBLE m_dblMaximumValue;
```

## <a name="csinusoidaltransitionfromrangem_dblminimumvalue"></a><a name="m_dblminimumvalue"></a> CSinusoidalTransitionFromRange:: m_dblMinimumValue

決まる正弦波 wave の trough にあるアニメーション変数の値。

```
DOUBLE m_dblMinimumValue;
```

## <a name="csinusoidaltransitionfromrangem_duration"></a><a name="m_duration"></a> CSinusoidalTransitionFromRange:: m_duration

遷移の継続時間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromrangem_period"></a><a name="m_period"></a> CSinusoidalTransitionFromRange:: m_period

決まる正弦波波の振幅の期間 (秒単位)。

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="csinusoidaltransitionfromrangem_slope"></a><a name="m_slope"></a> CSinusoidalTransitionFromRange:: m_slope

遷移の開始時の傾斜。

```
UI_ANIMATION_SLOPE m_slope;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
