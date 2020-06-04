---
title: CInstantaneousTransition クラス
ms.date: 11/04/2016
f1_keywords:
- CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::Create
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::m_dblFinalValue
helpviewer_keywords:
- CInstantaneousTransition [MFC], CInstantaneousTransition
- CInstantaneousTransition [MFC], Create
- CInstantaneousTransition [MFC], m_dblFinalValue
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
ms.openlocfilehash: 15c471d64309cc1358c9c5b0b33577261dd877f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372438"
---
# <a name="cinstantaneoustransition-class"></a>CInstantaneousTransition クラス

即時遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CInstantaneousTransition : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[Cインスタントアトランジション::Cインスタントアトランジション](#cinstantaneoustransition)|遷移オブジェクトを構築し、その最終的な値を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Cインスタント移行::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[瞬間的なトランジション::m_dblFinalValue](#m_dblfinalvalue)|トランジションの終了時のアニメーション変数の値。|

## <a name="remarks"></a>解説

瞬間的な遷移の間に、アニメーション変数の値は、現在の値から指定された最終値に瞬時に変化します。 この遷移の期間は常にゼロです。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[C瞬時トランジション](../../mfc/reference/cinstantaneoustransition-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cinstantaneoustransitioncinstantaneoustransition"></a><a name="cinstantaneoustransition"></a>Cインスタントアトランジション::Cインスタントアトランジション

遷移オブジェクトを構築し、その最終的な値を初期化します。

```
CInstantaneousTransition(DOUBLE dblFinalValue);
```

### <a name="parameters"></a>パラメーター

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

## <a name="cinstantaneoustransitioncreate"></a><a name="create"></a>Cインスタント移行::作成

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

## <a name="cinstantaneoustransitionm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>瞬間的なトランジション::m_dblFinalValue

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
