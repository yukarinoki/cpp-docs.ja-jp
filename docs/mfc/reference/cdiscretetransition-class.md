---
title: CDiscreteTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::CDiscreteTransition
- AFXANIMATIONCONTROLLER/CDiscreteTransition::Create
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_delay
- AFXANIMATIONCONTROLLER/CDiscreteTransition::m_hold
helpviewer_keywords:
- CDiscreteTransition [MFC], CDiscreteTransition
- CDiscreteTransition [MFC], Create
- CDiscreteTransition [MFC], m_dblFinalValue
- CDiscreteTransition [MFC], m_delay
- CDiscreteTransition [MFC], m_hold
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
ms.openlocfilehash: 2a32ee7921e927e25a5196d38c8f5ae350ab2b8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375653"
---
# <a name="cdiscretetransition-class"></a>CDiscreteTransition クラス

不連続遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CDiscreteTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[離散遷移::離散転換](#cdiscretetransition)|離散遷移オブジェクトを構築し、そのパラメーターを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[離散遷移::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[離散遷移::m_dblFinalValue](#m_dblfinalvalue)|トランジションの終了時のアニメーション変数の値。|
|[離散遷移::m_delay](#m_delay)|瞬間的な切り替えを最終値に遅延させる時間。|
|[離散遷移::m_hold](#m_hold)|変数を最後の値で保持する時間。|

## <a name="remarks"></a>解説

離散遷移中、アニメーション変数は指定された遅延時間の初期値のまま、指定された最終値に瞬時に切り替えられ、特定の保留時間の間はその値にとどまります。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[離散転換](../../mfc/reference/cdiscretetransition-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cdiscretetransitioncdiscretetransition"></a><a name="cdiscretetransition"></a>離散遷移::離散転換

離散遷移オブジェクトを構築し、そのパラメーターを初期化します。

```
CDiscreteTransition(
    UI_ANIMATION_SECONDS delay,
    DOUBLE dblFinalValue,
    UI_ANIMATION_SECONDS hold);
```

### <a name="parameters"></a>パラメーター

*遅延*<br/>
瞬間的な切り替えを最終値に遅延させる時間。

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

*保持*<br/>
変数を最後の値で保持する時間。

## <a name="cdiscretetransitioncreate"></a><a name="create"></a>離散遷移::作成

カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。

```
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,
    IUIAnimationTransitionFactory* \*not used*\);
```

*pライブラリ*<br/>
標準遷移のライブラリを定義する[IUIAnimationTransitionLibrary インターフェイス](/windows/win32/api/uianimation/nn-uianimation-iuianimationtransitionlibrary)へのポインター。

### <a name="return-value"></a>戻り値

遷移が正常に作成された場合は TRUE。それ以外の場合は FALSE。

## <a name="cdiscretetransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>離散遷移::m_dblFinalValue

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="cdiscretetransitionm_delay"></a><a name="m_delay"></a>離散遷移::m_delay

瞬間的な切り替えを最終値に遅延させる時間。

```
UI_ANIMATION_SECONDS m_delay;
```

## <a name="cdiscretetransitionm_hold"></a><a name="m_hold"></a>離散遷移::m_hold

変数を最後の値で保持する時間。

```
UI_ANIMATION_SECONDS m_hold;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
