---
title: CCubicTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::CCubicTransition
- AFXANIMATIONCONTROLLER/CCubicTransition::Create
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CCubicTransition::m_dblFinalVelocity
- AFXANIMATIONCONTROLLER/CCubicTransition::m_duration
helpviewer_keywords:
- CCubicTransition [MFC], CCubicTransition
- CCubicTransition [MFC], Create
- CCubicTransition [MFC], m_dblFinalValue
- CCubicTransition [MFC], m_dblFinalVelocity
- CCubicTransition [MFC], m_duration
ms.assetid: 4fc30e9c-160c-45e1-bdbe-51adf8fee9c5
ms.openlocfilehash: de376503111dab157ca34744863fb1d35a58785e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81369344"
---
# <a name="ccubictransition-class"></a>CCubicTransition クラス

3 次遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CCubicTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cキュービックトランジション::Cキュービックトランジション](#ccubictransition)|遷移オブジェクトを構築し、そのパラメーターを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cキュービックトランジション::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[キューキュージトランジション::m_dblFinalValue](#m_dblfinalvalue)|トランジションの終了時のアニメーション変数の値。|
|[キューキュージトランジション::m_dblFinalVelocity](#m_dblfinalvelocity)|遷移の最後の変数の速度。|
|[キューキュージトランジション::m_duration](#m_duration)|トランジションの期間。|

## <a name="remarks"></a>解説

3 次遷の間、アニメーション変数の値は、遷移の間に初期値から指定された最終値に変化し、指定された速度で終了します。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

`CCubicTransition`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="ccubictransitionccubictransition"></a><a name="ccubictransition"></a>Cキュービックトランジション::Cキュービックトランジション

遷移オブジェクトを構築し、そのパラメーターを初期化します。

```
CCubicTransition(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue,
    DOUBLE finalVelocity);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
トランジションの期間。

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

*最終速度*<br/>
遷移の最後の変数の速度。

## <a name="ccubictransitioncreate"></a><a name="create"></a>Cキュービックトランジション::作成

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

## <a name="ccubictransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>キューキュージトランジション::m_dblFinalValue

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="ccubictransitionm_dblfinalvelocity"></a><a name="m_dblfinalvelocity"></a>キューキュージトランジション::m_dblFinalVelocity

遷移の最後の変数の速度。

```
DOUBLE m_dblFinalVelocity;
```

## <a name="ccubictransitionm_duration"></a><a name="m_duration"></a>キューキュージトランジション::m_duration

トランジションの期間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
