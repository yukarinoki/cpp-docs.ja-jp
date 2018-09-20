---
title: CAccelerateDecelerateTransition Class1 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d548a87b7d02130e4a926fd33490223f0070c74c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445036"
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
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|移行のオブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CAccelerateDecelerateTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|実行中に加速に費やされた時間の比率。|
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|期間に減速する場合に費やした時間の比率です。|
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|移行の期間です。|
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|移行の最後にアニメーション変数の値。|

## <a name="remarks"></a>Remarks

加速中に、/減速の遷移、アニメーション変数の高速化と、指定した値で終わる、遷移の期間にわたって速度が低下します。 変数がどの程度の速度を短縮し、さまざまな加速と減速の比率を指定することで、独立してに減速を制御できます。 高速化は加速; 変数に要する時間の割合、初期速度が 0 の場合同様を減速比。 初期速度がゼロ以外の場合は、ベロシティを 0 と遷移の終了に達するまでの時間の割合。 高速化比率と減速の比率を合計すると 1.0 の最大数。 すべての遷移が自動的にクリアされますが、お勧めするそれらに割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、null を指定し、まで、CAnimationController::AnimateGroup によって作成されます。 影響を与えませんこの COM オブジェクトの作成後は、メンバー変数を変更します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CAccelerateDecelerateTransition`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition

移行のオブジェクトを構築します。

```
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE accelerationRatio = 0.3,
    DOUBLE decelerationRatio = 0.3);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
移行の期間です。

*finalValue*<br/>
移行の最後にアニメーション変数の値。

*accelerationRatio*<br/>
実行中に加速に費やされた時間の比率。

*decelerationRatio*<br/>
期間に減速する場合に費やした時間の比率です。

##  <a name="create"></a>  CAccelerateDecelerateTransition::Create

カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* *\not used*\);
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
ポインター、 [IUIAnimationTransitionLibrary インターフェイス](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)、標準的な遷移のライブラリを定義します。

### <a name="return-value"></a>戻り値

移行が正常に作成された場合は TRUE。それ以外の場合は FALSE です。

##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio

実行中に加速に費やされた時間の比率。

```
DOUBLE m_accelerationRatio;
```

##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio

期間に減速する場合に費やした時間の比率です。

```
DOUBLE m_decelerationRatio;
```

##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration

移行の期間です。

```
UI_ANIMATION_SECONDS m_duration;
```

##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue

移行の最後にアニメーション変数の値。

```
DOUBLE m_finalValue;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
