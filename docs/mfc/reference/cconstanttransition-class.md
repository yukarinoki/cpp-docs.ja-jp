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
ms.openlocfilehash: 0d5d92f02cc3b56268966f1cd79451578a5cc390
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369406"
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
|[定数トランジション::定数トランジション](#cconstanttransition)|遷移オブジェクトを構築し、その期間を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[定数トランジション::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[定数トランジション::m_duration](#m_duration)|トランジションの期間。|

## <a name="remarks"></a>解説

一定の遷移中、アニメーション変数の値は、遷移の間、初期値のままです。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

`CConstantTransition`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cconstanttransitioncconstanttransition"></a><a name="cconstanttransition"></a>定数トランジション::定数トランジション

遷移オブジェクトを構築し、その期間を初期化します。

```
CConstantTransition (UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
トランジションの期間。

## <a name="cconstanttransitioncreate"></a><a name="create"></a>定数トランジション::作成

カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

### <a name="parameters"></a>パラメーター

*pライブラリ*<br/>
標準遷移のライブラリを定義する[IUIAnimationTransitionLibrary インターフェイス](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)へのポインター。

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cconstanttransitionm_duration"></a><a name="m_duration"></a>定数トランジション::m_duration

トランジションの期間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
