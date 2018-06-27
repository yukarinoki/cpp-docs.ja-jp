---
title: CAccelerateDecelerateTransition Class1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CAccelerateDecelerateTransition
- afxanimationcontroller/CAccelerateDecelerateTransition
dev_langs:
- C++
helpviewer_keywords:
- CAccelerateDecelerateTransition class [MFC]
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4342ed03991317bd030d308dbac9945734dcbd9e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954709"
---
# <a name="cacceleratedeceleratetransition-class"></a>CAccelerateDecelerateTransition クラス
加速減速遷移を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](#cacceleratedeceleratetransition)|移行のオブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](#create)|カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。 (上書き[CBaseTransition::Create](../../mfc/reference/cbasetransition-class.md#create))。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m_accelerationRatio](#m_accelerationratio)|までの期間を短縮に費やされた時間の比率です。|  
|[CAccelerateDecelerateTransition::m_decelerationRatio](#m_decelerationratio)|期間に減速費やされた時間の比率です。|  
|[CAccelerateDecelerateTransition::m_duration](#m_duration)|移行の期間です。|  
|[CAccelerateDecelerateTransition::m_finalValue](#m_finalvalue)|遷移の終了時、アニメーション変数の値。|  
  
## <a name="remarks"></a>Remarks  
 加速中-減速遷移は、アニメーション変数を高速化し、速度が低下し、指定した値で終わる、切り替え効果の期間にわたっています。 変数がどの程度の速度を短縮し、異なるアクセラレータと減速率を指定することで、独立してに減速を制御できます。 アクセラレータの比率に加速する場合は、変数に要する時間の割合は、初期ベロシティが 0 の場合同様に、減速比でします。 初期ベロシティがゼロ以外の場合は、ベロシティ 0 と遷移の末尾に到達するまでの時間の割合を勧めします。 アクセラレータとの比率、減速率は、1.0 の最大合計を計算します。 すべての遷移が自動的にクリアされますをお勧めして割り当てられた新しい演算子を使用します。 カプセル化された IUIAnimationTransition COM オブジェクトは、NULL を指定してから、まで CAnimationController::AnimateGroup、によって作成されます。 この COM オブジェクトの作成も何も起こりません後は、メンバー変数を変更します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 `CAccelerateDecelerateTransition`   
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="cacceleratedeceleratetransition"></a>  CAccelerateDecelerateTransition::CAccelerateDecelerateTransition  
 移行のオブジェクトを構築します。  
  
```  
CAccelerateDecelerateTransition(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue,  
    DOUBLE accelerationRatio = 0.3,  
    DOUBLE decelerationRatio = 0.3);
```  
  
### <a name="parameters"></a>パラメーター  
 *duration*  
 移行の期間です。  
  
 *finalValue*  
 遷移の終了時、アニメーション変数の値。  
  
 *accelerationRatio*  
 までの期間を短縮に費やされた時間の比率です。  
  
 *decelerationRatio*  
 期間に減速費やされた時間の比率です。  
  
##  <a name="create"></a>  CAccelerateDecelerateTransition::Create  
 カプセル化された移行 COM オブジェクトを作成する遷移のライブラリを呼び出します。  
  
```  
virtual BOOL Create(
    IUIAnimationTransitionLibrary* pLibrary,  
    IUIAnimationTransitionFactory* *\not used*\);
```  
  
### <a name="parameters"></a>パラメーター  
*pLibrary*  
 ポインター、 [IUIAnimationTransitionLibrary インターフェイス](https://msdn.microsoft.com/library/windows/desktop/dd371897)、標準的な遷移のライブラリを定義します。  
  
### <a name="return-value"></a>戻り値  
 移行が正常に作成された場合は TRUE。それ以外の場合は FALSE。  
  
##  <a name="m_accelerationratio"></a>  CAccelerateDecelerateTransition::m_accelerationRatio  
 までの期間を短縮に費やされた時間の比率です。  
  
```  
DOUBLE m_accelerationRatio;  
```  
  
##  <a name="m_decelerationratio"></a>  CAccelerateDecelerateTransition::m_decelerationRatio  
 期間に減速費やされた時間の比率です。  
  
```  
DOUBLE m_decelerationRatio;  
```  
  
##  <a name="m_duration"></a>  CAccelerateDecelerateTransition::m_duration  
 移行の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>  CAccelerateDecelerateTransition::m_finalValue  
 遷移の終了時、アニメーション変数の値。  
  
```  
DOUBLE m_finalValue;  
```  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
