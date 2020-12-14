---
description: '詳細情報: CSinusoidalTransitionFromVelocity クラス'
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
ms.openlocfilehash: 96f4a4c6343f3635f3b60480f49c5af6e6f1e089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342755"
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
|[CSinusoidalTransitionFromVelocity:: CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|遷移オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity:: Create](#create)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します。 ( [Cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create)をオーバーライドします)。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CSinusoidalTransitionFromVelocity:: m_duration](#m_duration)|遷移の継続時間。|
|[CSinusoidalTransitionFromVelocity:: m_period](#m_period)|決まる正弦波波の振幅の期間 (秒単位)。|

## <a name="remarks"></a>解説

アニメーション変数の値は、決まる正弦波範囲の遷移の期間全体の初期値を oscillates します。 振幅の振幅は、遷移の開始時にアニメーション変数の速度によって決まります。 すべての遷移は自動的にクリアされるため、operator new を使用して割り当てることをお勧めします。 カプセル化された IuiAnimateGroup 遷移 COM オブジェクトは、次に NULL になるまで、CAnimationController:: によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても効果はありません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="csinusoidaltransitionfromvelocitycreate"></a><a name="create"></a> CSinusoidalTransitionFromVelocity:: Create

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

## <a name="csinusoidaltransitionfromvelocitycsinusoidaltransitionfromvelocity"></a><a name="csinusoidaltransitionfromvelocity"></a> CSinusoidalTransitionFromVelocity:: CSinusoidalTransitionFromVelocity

遷移オブジェクトを構築します。

```
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,
    UI_ANIMATION_SECONDS period);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
遷移の継続時間。

*前期*<br/>
決まる正弦波波の振幅の期間 (秒単位)。

## <a name="csinusoidaltransitionfromvelocitym_duration"></a><a name="m_duration"></a> CSinusoidalTransitionFromVelocity:: m_duration

遷移の継続時間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="csinusoidaltransitionfromvelocitym_period"></a><a name="m_period"></a> CSinusoidalTransitionFromVelocity:: m_period

決まる正弦波波の振幅の期間 (秒単位)。

```
UI_ANIMATION_SECONDS m_period;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
