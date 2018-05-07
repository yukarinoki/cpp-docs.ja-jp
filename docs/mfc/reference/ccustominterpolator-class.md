---
title: CCustomInterpolator クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::CCustomInterpolator
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDependencies
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::GetFinalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::Init
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetDuration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::SetInitialValueAndVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_currentVelocity
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_duration
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_finalValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialValue
- AFXANIMATIONCONTROLLER/CCustomInterpolator::m_initialVelocity
dev_langs:
- C++
helpviewer_keywords:
- CCustomInterpolator [MFC], CCustomInterpolator
- CCustomInterpolator [MFC], GetDependencies
- CCustomInterpolator [MFC], GetDuration
- CCustomInterpolator [MFC], GetFinalValue
- CCustomInterpolator [MFC], Init
- CCustomInterpolator [MFC], InterpolateValue
- CCustomInterpolator [MFC], InterpolateVelocity
- CCustomInterpolator [MFC], SetDuration
- CCustomInterpolator [MFC], SetInitialValueAndVelocity
- CCustomInterpolator [MFC], m_currentValue
- CCustomInterpolator [MFC], m_currentVelocity
- CCustomInterpolator [MFC], m_duration
- CCustomInterpolator [MFC], m_finalValue
- CCustomInterpolator [MFC], m_initialValue
- CCustomInterpolator [MFC], m_initialVelocity
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b093ff87d7f2c8c52b6745be4e2a31580fce0fce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ccustominterpolator-class"></a>CCustomInterpolator クラス
基本のインターポレータを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CCustomInterpolator;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomInterpolator::CCustomInterpolator](#ccustominterpolator)|オーバーロードされます。 Interpolator のカスタム オブジェクトを構築して、期間と指定した値にベロシティを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomInterpolator::GetDependencies](#getdependencies)|Interpolator の依存関係を取得します。|  
|[CCustomInterpolator::GetDuration](#getduration)|Interpolator の期間を取得します。|  
|[CCustomInterpolator::GetFinalValue](#getfinalvalue)|Interpolator が潜在顧客の最終的な値を取得します。|  
|[CCustomInterpolator::Init](#init)|期間および最終的な値を初期化します。|  
|[CCustomInterpolator::InterpolateValue](#interpolatevalue)|指定されたオフセット値を補間します。|  
|[CCustomInterpolator::InterpolateVelocity](#interpolatevelocity)|指定されたオフセット ベロシティを補間します。|  
|[CCustomInterpolator::SetDuration](#setduration)|Interpolator の期間を設定します。|  
|[CCustomInterpolator::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Interpolator の初期値と速度を設定します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCustomInterpolator::m_currentValue](#m_currentvalue)|補間値です。|  
|[CCustomInterpolator::m_currentVelocity](#m_currentvelocity)|補間された速度。|  
|[CCustomInterpolator::m_duration](#m_duration)|移行の期間です。|  
|[CCustomInterpolator::m_finalValue](#m_finalvalue)|移行の最後に変数の最終的な値。|  
|[CCustomInterpolator::m_initialValue](#m_initialvalue)|移行の開始時に変数の値。|  
|[CCustomInterpolator::m_initialVelocity](#m_initialvelocity)|移行の開始時に変数の速度です。|  
  
## <a name="remarks"></a>コメント  
 CCustomInterpolator からクラスを派生し、カスタムの補間アルゴリズムを実装するために必要なすべてのメソッドをオーバーライドします。 このクラスへのポインターは、CCustomTransition をパラメーターとして渡されます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CCustomInterpolator`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="ccustominterpolator"></a>  CCustomInterpolator::CCustomInterpolator  
 Interpolator のカスタム オブジェクトを構築し、0 を既定値にすべての値を設定します。  
  
```  
CCustomInterpolator();

 
CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 移行の期間です。  
  
 `finalValue`  
  
### <a name="remarks"></a>コメント  
 CCustomInterpolator::Init を使用して、期間と、コードの後で最終的な値を初期化します。  
  
##  <a name="getdependencies"></a>  CCustomInterpolator::GetDependencies  
 Interpolator の依存関係を取得します。  
  
```  
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,  
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,  
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValueDependencies`  
 出力です。 Interpolator の初期値に依存する要素は、SetInitialValueAndVelocity に渡されます。  
  
 `initialVelocityDependencies`  
 出力です。 Interpolator の初期速度に依存する要素は、SetInitialValueAndVelocity に渡されます。  
  
 `durationDependencies`  
 出力です。 Interpolator の期間に依存する要素は、SetDuration に渡されます。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
##  <a name="getduration"></a>  CCustomInterpolator::GetDuration  
 Interpolator の期間を取得します。  
  
```  
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 出力です。 秒単位で、移行の期間です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
##  <a name="getfinalvalue"></a>  CCustomInterpolator::GetFinalValue  
 Interpolator が潜在顧客の最終的な値を取得します。  
  
```  
virtual BOOL GetFinalValue(DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 出力です。 移行の最後に変数の最終的な値。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
##  <a name="init"></a>  CCustomInterpolator::Init  
 期間および最終的な値を初期化します。  
  
```  
void Init(
    UI_ANIMATION_SECONDS duration,  
    DOUBLE finalValue);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 移行の期間です。  
  
 `finalValue`  
 移行の最後に変数の最終的な値。  
  
##  <a name="interpolatevalue"></a>  CCustomInterpolator::InterpolateValue  
 指定されたオフセット値を補間します。  
  
```  
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 出力です。 補間値です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
##  <a name="interpolatevelocity"></a>  CCustomInterpolator::InterpolateVelocity  
 指定されたオフセット ベロシティを補間します。  
  
```  
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,  
    DOUBLE* velocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `velocity`  
 出力です。 オフセットで変数の速度です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
##  <a name="m_currentvalue"></a>  CCustomInterpolator::m_currentValue  
 補間値です。  
  
```  
DOUBLE m_currentValue;  
```  
  
##  <a name="m_currentvelocity"></a>  CCustomInterpolator::m_currentVelocity  
 補間された速度。  
  
```  
DOUBLE m_currentVelocity;  
```  
  
##  <a name="m_duration"></a>  CCustomInterpolator::m_duration  
 移行の期間です。  
  
```  
UI_ANIMATION_SECONDS m_duration;  
```  
  
##  <a name="m_finalvalue"></a>  CCustomInterpolator::m_finalValue  
 移行の最後に変数の最終的な値。  
  
```  
DOUBLE m_finalValue;  
```  
  
##  <a name="m_initialvalue"></a>  CCustomInterpolator::m_initialValue  
 移行の開始時に変数の値。  
  
```  
DOUBLE m_initialValue;  
```  
  
##  <a name="m_initialvelocity"></a>  CCustomInterpolator::m_initialVelocity  
 移行の開始時に変数の速度です。  
  
```  
DOUBLE m_initialVelocity;  
```  
  
##  <a name="setduration"></a>  CCustomInterpolator::SetDuration  
 Interpolator の期間を設定します。  
  
```  
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 移行の期間です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装は常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
##  <a name="setinitialvalueandvelocity"></a>  CCustomInterpolator::SetInitialValueAndVelocity  
 Interpolator の初期値と速度を設定します。  
  
```  
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,  
    DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValue`  
 移行の開始時に変数の値。  
  
 `initialVelocity`  
 移行の開始時に変数の速度です。  
  
### <a name="return-value"></a>戻り値  
 基本的な実装を常に TRUE を返します。 FALSE が返されますオーバーライドされた実装からイベントが失敗する場合。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
