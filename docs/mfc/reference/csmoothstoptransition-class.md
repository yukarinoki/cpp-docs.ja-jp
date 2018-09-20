---
title: CSmoothStopTransition クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::CSmoothStopTransition
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::Create
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CSmoothStopTransition::m_maximumDuration
dev_langs:
- C++
helpviewer_keywords:
- CSmoothStopTransition [MFC], CSmoothStopTransition
- CSmoothStopTransition [MFC], Create
- CSmoothStopTransition [MFC], m_dblFinalValue
- CSmoothStopTransition [MFC], m_maximumDuration
ms.assetid: e1a4b476-6f96-43dd-90db-870a64406b85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db43e550b38778dbbdc34fb6e696129ca767d28f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377759"
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
|[CSmoothStopTransition::CSmoothStopTransition](#csmoothstoptransition)|スムーズ停止遷移を構築し、その最大期間と最終的な値を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSmoothStopTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CSmoothStopTransition::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|
|[CSmoothStopTransition::m_maximumDuration](#m_maximumduration)|移行の最大期間です。|

## <a name="remarks"></a>Remarks

特定の最終的な値に近づくし、0 という速度で到達、スムーズ停止遷移が低下します。 遷移の期間は、初期の速度は、最初と最後の値と指定した最大実行時間の違いによって決定されます。 1 つの放物線を描く遷移円弧から成るソリューションがない場合は、このメソッドは、3 次遷移を作成します。 すべての遷移が自動的にクリアされますが、お勧めするそれらに割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、null を指定し、まで、CAnimationController::AnimateGroup によって作成されます。 影響を与えませんこの COM オブジェクトの作成後は、メンバー変数を変更します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CSmoothStopTransition](../../mfc/reference/csmoothstoptransition-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

##  <a name="create"></a>  CSmoothStopTransition::Create

カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>パラメーター

*pLibrary*<br/>
標準的な遷移の作成を担当する遷移ライブラリへのポインター。

### <a name="return-value"></a>戻り値

移行が正常に作成された場合は TRUE。それ以外の場合は FALSE です。

##  <a name="csmoothstoptransition"></a>  CSmoothStopTransition::CSmoothStopTransition

スムーズ停止遷移を構築し、その最大期間と最終的な値を初期化します。

```
CSmoothStopTransition(
    UI_ANIMATION_SECONDS maximumDuration,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>パラメーター

*maximumDuration*<br/>
移行の最大期間です。

*dblFinalValue*<br/>
移行の最後にアニメーション変数の値。

##  <a name="m_dblfinalvalue"></a>  CSmoothStopTransition::m_dblFinalValue

移行の最後にアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

##  <a name="m_maximumduration"></a>  CSmoothStopTransition::m_maximumDuration

移行の最大期間です。

```
UI_ANIMATION_SECONDS m_maximumDuration;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
