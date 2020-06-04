---
title: CAccelerateDecelerateTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
ms.openlocfilehash: 356ba30e6d9a638672d2c356676735ebfaed8f3e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371149"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition クラス

加速減速遷移を実装します。

## <a name="syntax"></a>構文

```
class CAccelerateDecelerateTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[遷移の加速:C加速減速トランジション](#cacceleratedeceleratetransition)|遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[C加速減速トランジション::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[加速減速トランジション::m_accelerationRatio](#m_accelerationratio)|継続時間に対して加速に費やされた時間の比率。|
|[加速減速トランジション::m_decelerationRatio](#m_decelerationratio)|期間に対する減速に費やした時間の比率。|
|[加速減速トランジション::m_duration](#m_duration)|トランジションの期間。|
|[加速減速トランジション::m_finalValue](#m_finalvalue)|トランジションの終了時のアニメーション変数の値。|

## <a name="remarks"></a>解説

加速/減速の遷移の間、アニメーション変数は、遷移の間は速度を上げて、指定された値で終わる速度を低下させます。 異なる加速と減速の比率を指定することで、変数が個別に加速および減速する速度を制御できます。 初期速度がゼロの場合、加速比は変数が加速に費やす持続時間の割合です。同様に、減速比と同様に。 初期速度がゼロ以外の場合は、ゼロに達する速度と遷移の終了までの時間の割合です。 加速度比と減速比は、最大 1.0 に合計する必要があります。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cacceleratedeceleratetransitioncacceleratedeceleratetransition"></a><a name="cacceleratedeceleratetransition"></a>遷移の加速:C加速減速トランジション

遷移オブジェクトを構築します。

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
トランジションの期間。

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

*加速比率*<br/>
継続時間に対して加速に費やされた時間の比率。

*減速比率*<br/>
期間に対する減速に費やした時間の比率。

## <a name="cacceleratedeceleratetransitioncreate"></a><a name="create"></a>C加速減速トランジション::作成

カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移のライブラリを定義する[IUIAnimationTransitionLibrary インターフェイス](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)へのポインター。

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cacceleratedeceleratetransitionm_accelerationratio"></a><a name="m_accelerationratio"></a>加速減速トランジション::m_accelerationRatio

継続時間に対して加速に費やされた時間の比率。

```
DOUBLE m_accelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_decelerationratio"></a><a name="m_decelerationratio"></a>加速減速トランジション::m_decelerationRatio

期間に対する減速に費やした時間の比率。

```
DOUBLE m_decelerationRatio;
```

## <a name="cacceleratedeceleratetransitionm_duration"></a><a name="m_duration"></a>加速減速トランジション::m_duration

トランジションの期間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="cacceleratedeceleratetransitionm_finalvalue"></a><a name="m_finalvalue"></a>加速減速トランジション::m_finalValue

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
