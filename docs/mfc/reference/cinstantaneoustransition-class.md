---
title: CInstantaneousTransition クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::CInstantaneousTransition
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::Create
- AFXANIMATIONCONTROLLER/CInstantaneousTransition::m_dblFinalValue
dev_langs:
- C++
helpviewer_keywords:
- CInstantaneousTransition [MFC], CInstantaneousTransition
- CInstantaneousTransition [MFC], Create
- CInstantaneousTransition [MFC], m_dblFinalValue
ms.assetid: c3d5121f-2c6b-4221-9e57-10e082a31120
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46fe01c3382f5f3667cbe909a5fb796bbb8ccc6f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062458"
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
|[CInstantaneousTransition::CInstantaneousTransition](#cinstantaneoustransition)|遷移オブジェクトを構築し、最終的な値を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CInstantaneousTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移ライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[CInstantaneousTransition::m_dblFinalValue](#m_dblfinalvalue)|移行の最後にアニメーション変数の値。|

## <a name="remarks"></a>Remarks

即時遷移では中、は、アニメーション変数の値は現在の値から指定の最終的な値をすぐに変更します。 この遷移の期間は、常に 0 です。 すべての遷移が自動的にクリアされますが、お勧めするそれらに割り当てられている新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、null を指定し、まで、CAnimationController::AnimateGroup によって作成されます。 影響を与えませんこの COM オブジェクトの作成後は、メンバー変数を変更します。

## <a name="inheritance-hierarchy"></a>継承階層

[CObject](../../mfc/reference/cobject-class.md)

[CBaseTransition](../../mfc/reference/cbasetransition-class.md)

[CInstantaneousTransition](../../mfc/reference/cinstantaneoustransition-class.md)

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

##  <a name="cinstantaneoustransition"></a>  CInstantaneousTransition::CInstantaneousTransition

遷移オブジェクトを構築し、最終的な値を初期化します。

```
CInstantaneousTransition(DOUBLE dblFinalValue);
```

### <a name="parameters"></a>パラメーター

*dblFinalValue*<br/>
移行の最後にアニメーション変数の値。

##  <a name="create"></a>  CInstantaneousTransition::Create

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

##  <a name="m_dblfinalvalue"></a>  CInstantaneousTransition::m_dblFinalValue

移行の最後にアニメーション変数の値。

```
DOUBLE m_dblFinalValue;
```

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
