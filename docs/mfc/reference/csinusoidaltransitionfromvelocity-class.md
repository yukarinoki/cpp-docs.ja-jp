---
title: CSinusoidalTransitionFromVelocity クラス
ms.date: 11/04/2016
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
ms.openlocfilehash: 0df9ca6d140cb9e3ec85be3ce32760a66599c5d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318249"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity クラス

アニメーション変数の初期ベロシティによって振幅が決まる正弦波ベロシティ遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CSinusoidalTransitionFromVelocity : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cシヌイダルトランジションフロプ速度::Cシヌイダルトランジションフロプ速度](#csinusoidaltransitionfromvelocity)|遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cシヌイダルトランジションフロプ速度::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[Cシヌイダルトランジションフロプ速度::m_duration](#m_duration)|トランジションの期間。|
|[Cシヌイダルトランジションフロプ速度::m_period](#m_period)|正弦波の振動の秒単位の周期。|

## <a name="remarks"></a>解説

アニメーション変数の値は、中弦波範囲遷移の全期間にわたって初期値を中心に振動します。 振動の振幅は、遷移が始まるアニメーション変数の速度によって決まります。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[Cシヌイダルトランジションフロプ速度](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromvelocitycreate"></a><a name="create"></a>Cシヌイダルトランジションフロプ速度::作成

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

## <a name="csinusoidaltransitionfromvelocitycsinusoidaltransitionfromvelocity"></a><a name="csinusoidaltransitionfromvelocity"></a>Cシヌイダルトランジションフロプ速度::Cシヌイダルトランジションフロプ速度

遷移オブジェクトを構築します。

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
トランジションの期間。

*期間*<br/>
正弦波の振動の秒単位の周期。

## <a name="csinusoidaltransitionfromvelocitym_duration"></a><a name="m_duration"></a>Cシヌイダルトランジションフロプ速度::m_duration

トランジションの期間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromvelocitym_period"></a><a name="m_period"></a>Cシヌイダルトランジションフロプ速度::m_period

正弦波の振動の秒単位の周期。

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
