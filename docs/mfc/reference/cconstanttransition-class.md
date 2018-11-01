---
title: CConstantTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::CConstantTransition
- AFXANIMATIONCONTROLLER/CConstantTransition::Create
- AFXANIMATIONCONTROLLER/CConstantTransition::m_duration
helpviewer_keywords:
- CConstantTransition [MFC], CConstantTransition
- CConstantTransition [MFC], Create
- CConstantTransition [MFC], m_duration
ms.assetid: f6fa4780-a71b-4cd6-80aa-d4792ace36c2
ms.openlocfilehash: 2ec8ec36e59a0d4dc0e00f5e379bfbef492ce4db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662021"
---
# <a name="cconstanttransition-class"></a>CConstantTransition クラス

連続的遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CConstantTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CConstantTransition::CConstantTransition](#cconstanttransition)|移行のオブジェクトを構築し、その継続時間を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CConstantTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CConstantTransition::m_duration](#m_duration)|移行の期間です。|

## <a name="remarks"></a>Remarks

アニメーション変数の値は、一定の遷移中に、遷移の期間にわたって初期値のままです。 すべての遷移が自動的にクリアされますが、お勧めするそれらに割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、null を指定し、まで、CAnimationController::AnimateGroup によって作成されます。 影響を与えませんこの COM オブジェクトの作成後は、メンバー変数を変更します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

##  <a name="cconstanttransition"></a>  CConstantTransition::CConstantTransition

移行のオブジェクトを構築し、その継続時間を初期化します。

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
移行の期間です。

##  <a name="create"></a>  CConstantTransition::Create

カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
ポインター、 [IUIAnimationTransitionLibrary インターフェイス](/windows/desktop/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)、標準的な遷移のライブラリを定義します。

### <a name="return-value"></a>戻り値

移行が正常に作成された場合は TRUE。それ以外の場合は FALSE です。

##  <a name="m_duration"></a>  CConstantTransition::m_duration

移行の期間です。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
