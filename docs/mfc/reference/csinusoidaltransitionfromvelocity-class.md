---
title: CSinusoidalTransitionFromVelocity クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::Create
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_duration
- AFXANIMATIONCONTROLLER/CSinusoidalTransitionFromVelocity::m_period
dev_langs:
- C++
helpviewer_keywords:
- CSinusoidalTransitionFromVelocity [MFC], CSinusoidalTransitionFromVelocity
- CSinusoidalTransitionFromVelocity [MFC], Create
- CSinusoidalTransitionFromVelocity [MFC], m_duration
- CSinusoidalTransitionFromVelocity [MFC], m_period
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9f5cc55adac2bf5900d9891635a025716b9c1f3
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2018
ms.locfileid: "37078580"
---
# <a name="csinusoidaltransitionfromvelocity-class"></a>CSinusoidalTransitionFromVelocity クラス
アニメーション変数の初期ベロシティによって振幅が決まる正弦波ベロシティ遷移をカプセル化します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](#csinusoidaltransitionfromvelocity)|移行のオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::m_duration](#m_duration)|移行の期間です。|  
|[CSinusoidalTransitionFromVelocity::m_period](#m_period)|秒単位で正弦波の振幅の期間。|  
  
## <a name="remarks"></a>Remarks  
 アニメーション変数の値は、初期値を囲む正弦波範囲遷移の期間全体にわたって振動です。 移行の開始時に、振幅の振幅をアニメーション変数の速度によって決まります。 すべての遷移が自動的にクリアされますをお勧めして割り当てられた新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL を指定してから、まで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成も何も起こりません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="create"></a>  CSinusoidalTransitionFromVelocity::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* \*not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
 *pLibrary*  
 これは標準的な遷移の作成を担当する遷移ライブラリへのポインター。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="csinusoidaltransitionfromvelocity"></a>  CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity  
 移行のオブジェクトを構築します。  
  
```  
CSinusoidalTransitionFromVelocity(
    UI_ANIMATION_SECONDS duration,  
    UI_ANIMATION_SECONDS period);
```  
  
### <a name="parameters"></a>パラメーター  
 *duration*  
 移行の期間です。  
  
 *期間*  
 秒単位で正弦波の振幅の期間。  
  
##  <a name="m_duration"></a>  CSinusoidalTransitionFromVelocity::m_duration  
 移行の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_period"></a>  CSinusoidalTransitionFromVelocity::m_period  
 秒単位で正弦波の振幅の期間。  
  
```  
UI_ANIMATION_SECONDS m_period;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
