---
title: CLinearTransitionFromSpeed クラス
ms.date: 11/04/2016
f1_keywords:
- CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::Create
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblSpeed
helpviewer_keywords:
- CLinearTransitionFromSpeed [MFC], CLinearTransitionFromSpeed
- CLinearTransitionFromSpeed [MFC], Create
- CLinearTransitionFromSpeed [MFC], m_dblFinalValue
- CLinearTransitionFromSpeed [MFC], m_dblSpeed
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
ms.openlocfilehash: 31c04c303e7e253ec4de41bf076130d19232aac0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372266"
---
# <a name="clineartransitionfromspeed-class"></a>CLinearTransitionFromSpeed クラス

直線速度遷移をカプセル化します。

## <a name="syntax"></a>構文

```
class CLinearTransitionFromSpeed : public CBaseTransition;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[速度からCリニアトランジション::C線形トランジションフロプスピード](#clineartransitionfromspeed)|線形速度遷移オブジェクトを構築し、速度と最終値で初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[速度からC線状トランジション::作成](#create)|カプセル化された遷移 COM オブジェクトを作成する遷移ライブラリを呼び出します。 [(CBase トランジションをオーバーライドします。:作成](../../mfc/reference/cbasetransition-class.md#create).)|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[速度::m_dblFinalValue](#m_dblfinalvalue)|トランジションの終了時のアニメーション変数の値。|
|[速度から::m_dblSpeed](#m_dblspeed)|変数の速度の絶対値。|

## <a name="remarks"></a>解説

直線速度遷移中に、アニメーション変数の値は指定された速度で変化します。 遷移の期間は、初期値と指定された最終値の差によって決まります。 すべてのトランジションは自動的にクリアされるため、演算子 new を使用して割り当てることをお勧めします。 カプセル化された IUIAnimationTransition COM オブジェクトは、それまでは NULL になるまで CAnimationController::AnimateGroup によって作成されます。 この COM オブジェクトの作成後にメンバー変数を変更しても、何も影響しません。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[Cベーストランジション](../../mfc/reference/cbasetransition-class.md)

[速度から遷移](../../mfc/reference/clineartransitionfromspeed-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="clineartransitionfromspeedclineartransitionfromspeed"></a><a name="clineartransitionfromspeed"></a>速度からCリニアトランジション::C線形トランジションフロプスピード

線形速度遷移オブジェクトを構築し、速度と最終値で初期化します。

```
CLinearTransitionFromSpeed(
    DOUBLE dblSpeed,
    DOUBLE dblFinalValue);
```

### <a name="parameters"></a>パラメーター

*dblスピード*<br/>
変数の速度の絶対値。

*最終価値*<br/>
トランジションの終了時のアニメーション変数の値。

## <a name="clineartransitionfromspeedcreate"></a><a name="create"></a>速度からC線状トランジション::作成

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

## <a name="clineartransitionfromspeedm_dblfinalvalue"></a><a name="m_dblfinalvalue"></a>速度::m_dblFinalValue

トランジションの終了時のアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="clineartransitionfromspeedm_dblspeed"></a><a name="m_dblspeed"></a>速度から::m_dblSpeed

変数の速度の絶対値。

```
DOUBLE m_dblSpeed;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
