---
description: '詳細情報: CReversalTransition クラス'
title: CReversalTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::CReversalTransition
- AFXANIMATIONCONTROLLER/CReversalTransition::Create
- AFXANIMATIONCONTROLLER/CReversalTransition::m_duration
helpviewer_keywords:
- CReversalTransition [MFC], CReversalTransition
- CReversalTransition [MFC], Create
- CReversalTransition [MFC], m_duration
ms.assetid: e89516be-2d07-4885-95a8-fc278f46e3ad
ms.openlocfilehash: f1d16562751e93ccf6df7ca3f70dac08bda8423d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343008"
---
# <a name="creversaltransition-class"></a>CReversalTransition クラス

逆遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CReversalTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[CReversalTransition:: CReversalTransition](#creversaltransition)|反転遷移オブジェクトを構築し、その継続時間を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CReversalTransition:: Create](#create)|遷移ライブラリを呼び出して、カプセル化された遷移 COM オブジェクトを作成します。 ( [Cbasetransition:: Create](../../mfc/reference/cbasetransition-class.md#create)をオーバーライドします)。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CReversalTransition:: m_duration](#m_duration)|遷移の継続時間。|

## <a name="remarks"></a>解説

反転遷移では、指定された期間にわたって方向が滑らかに変化します。 最終的な値は初期値と同じになり、最終的なベロシティは初期速度の負の値になります。 すべての遷移は自動的にクリアされるため、operator new を使用して割り当てることをお勧めします。 カプセル化された IuiAnimateGroup 遷移 COM オブジェクトは、次に NULL になるまで、CAnimationController:: によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても効果はありません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CReversalTransition](../../mfc/reference/creversaltransition-class.md)

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="creversaltransitioncreate"></a><a name="create"></a> CReversalTransition:: Create

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

## <a name="creversaltransitioncreversaltransition"></a><a name="creversaltransition"></a> CReversalTransition:: CReversalTransition

反転遷移オブジェクトを構築し、その継続時間を初期化します。

```
CReversalTransition(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
遷移の継続時間。

## <a name="creversaltransitionm_duration"></a><a name="m_duration"></a> CReversalTransition:: m_duration

遷移の継続時間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
