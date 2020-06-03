---
title: CSmoothStopTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
ms.openlocfilehash: 0ba550b4a0b9443d0681e17195687fb94c207ace
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318202"
---
# <a name="csmoothstoptransition-class"></a>CSmoothStopTransition クラス

スムーズ停止遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CSmoothStopTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[遷移移行::スムースストップトランジション](#csmoothstoptransition)|スムーズストップ遷移を構築し、その最大継続時間と最終値を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[スムージングストップトランジション::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[スムージングストップトランジション::m_dblFinalValue](#m_dblfinalvalue)|トランジションの終了時のアニメーション変数の値。|
|[スムージングストップトランジション::m_maximumDuration](#m_maximumduration)|トランジションの最大期間。|

## <a name="remarks"></a>解説

スムーズストップトランジションは、指定された最終値に近づくと遅くなり、速度がゼロで到達します。 遷移の持続時間は、初期速度、初期値と最終値の差、および指定された最大期間によって決まります。 単一の放物線円弧から成る解がない場合、この方法は立方切りトランジションを作成します。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[トランジションを滑らかに](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="csmoothstoptransitioncreate"></a><a name="create"></a>スムージングストップトランジション::作成

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

## <a name="csmoothstoptransitioncsmoothstoptransition"></a><a name="csmoothstoptransition"></a>遷移移行::スムースストップトランジション

スムーズストップ遷移を構築し、その最大継続時間と最終値を初期化します。

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>パラメーター

*最大期間*<br/>
トランジションの最大期間。

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

## <a name="csmoothstoptransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>スムージングストップトランジション::m_dblFinalValue

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="csmoothstoptransitionm_maximumduration"></a><a name="m_maximumduration"></a>スムージングストップトランジション::m_maximumDuration

トランジションの最大期間。

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
