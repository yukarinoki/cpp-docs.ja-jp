---
title: CLinearTransitionFromSpeed クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::Create
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblFinalValue
- AFXANIMATIONCONTROLLER/CLinearTransitionFromSpeed::m_dblSpeed
dev_langs:
- C++
helpviewer_keywords:
- CLinearTransitionFromSpeed [MFC], CLinearTransitionFromSpeed
- CLinearTransitionFromSpeed [MFC], Create
- CLinearTransitionFromSpeed [MFC], m_dblFinalValue
- CLinearTransitionFromSpeed [MFC], m_dblSpeed
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64c8829336378e24759bc26e306fb7b43ab226bc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
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
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](#clineartransitionfromspeed)|直線速度遷移オブジェクトを構築しの速度と最終的な値で初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::m_dblFinalValue](#m_dblfinalvalue)|遷移の終了時、アニメーション変数の値。|  
|[CLinearTransitionFromSpeed::m_dblSpeed](#m_dblspeed)|変数のベロシティの絶対値。|  
  
## <a name="remarks"></a>コメント  
 直線速度遷移中に指定したレートでアニメーション変数の値を変更します。 移行の期間は、初期値と指定した最終的な値の違いによって決まります。 すべての遷移が自動的にクリアされますをお勧めして割り当てられた新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL を指定してから、まで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成も何も起こりません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="clineartransitionfromspeed"></a>  CLinearTransitionFromSpeed::CLinearTransitionFromSpeed  
 直線速度遷移オブジェクトを構築しの速度と最終的な値で初期化します。  
  
```  
CLinearTransitionFromSpeed(
    DOUBLE dblSpeed,  
    DOUBLE dblFinalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `dblSpeed`  
 変数のベロシティの絶対値。  
  
 `dblFinalValue`  
 遷移の終了時、アニメーション変数の値。  
  
##  <a name="create"></a>  CLinearTransitionFromSpeed::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
`pLibrary`  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準的な遷移のライブラリを定義します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_dblfinalvalue"></a>  CLinearTransitionFromSpeed::m_dblFinalValue  
 遷移の終了時、アニメーション変数の値。  
  
```  
DOUBLE m_dblFinalValue;  
```  
  
##  <a name="m_dblspeed"></a>  CLinearTransitionFromSpeed::m_dblSpeed  
 変数のベロシティの絶対値。  
  
```  
DOUBLE m_dblSpeed;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
