---
title: CInterpolatorBase クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CInterpolatorBase
- AFXANIMATIONCONTROLLER/CInterpolatorBase::CreateInstance
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDependencies
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::GetFinalValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateValue
- AFXANIMATIONCONTROLLER/CInterpolatorBase::InterpolateVelocity
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetCustomInterpolator
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetDuration
- AFXANIMATIONCONTROLLER/CInterpolatorBase::SetInitialValueAndVelocity
dev_langs:
- C++
helpviewer_keywords:
- CInterpolatorBase [MFC], CInterpolatorBase
- CInterpolatorBase [MFC], CreateInstance
- CInterpolatorBase [MFC], GetDependencies
- CInterpolatorBase [MFC], GetDuration
- CInterpolatorBase [MFC], GetFinalValue
- CInterpolatorBase [MFC], InterpolateValue
- CInterpolatorBase [MFC], InterpolateVelocity
- CInterpolatorBase [MFC], SetCustomInterpolator
- CInterpolatorBase [MFC], SetDuration
- CInterpolatorBase [MFC], SetInitialValueAndVelocity
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c0ca520fe89e04d984e6490c495f2622a6037c79
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="cinterpolatorbase-class"></a>CInterpolatorBase クラス
アニメーション変数の新しい値を計算する必要があるときに、Animation API によって呼び出されるコールバックを実装します。  
  
## <a name="syntax"></a>構文  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](#cinterpolatorbase)|構築、`CInterpolatorBase`オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](#createinstance)|インスタンスを作成`CInterpolatorBase`し、イベントを処理するカスタム補間へのポインターを格納します。|  
|[CInterpolatorBase::GetDependencies](#getdependencies)|Interpolator の依存関係を取得します。 (`CUIAnimationInterpolatorBase::GetDependencies` をオーバーライドします)。|  
|[CInterpolatorBase::GetDuration](#getduration)|Interpolator の期間を取得します。 (`CUIAnimationInterpolatorBase::GetDuration` をオーバーライドします)。|  
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Interpolator が潜在顧客の最終的な値を取得します。 (`CUIAnimationInterpolatorBase::GetFinalValue` をオーバーライドします)。|  
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|指定されたオフセット値を補間 (オーバーライド`CUIAnimationInterpolatorBase::InterpolateValue`)。|  
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|指定されたオフセット ベロシティを補間 (オーバーライド`CUIAnimationInterpolatorBase::InterpolateVelocity`)。|  
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|イベントを処理するカスタム補間へのポインターを格納します。|  
|[CInterpolatorBase::SetDuration](#setduration)|Interpolator の期間を設定 (オーバーライド`CUIAnimationInterpolatorBase::SetDuration`)。|  
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Interpolator の初期値と速度を設定します。 (`CUIAnimationInterpolatorBase::SetInitialValueAndVelocity` をオーバーライドします)。|  
  
## <a name="remarks"></a>コメント  
 このハンドラーが作成されに渡される`IUIAnimationTransitionFactory::CreateTransition`ときに、`CCustomTransition`オブジェクトがアニメーション初期化プロセスの一部として作成される (によって開始された`CAnimationController::AnimateGroup`)。 通常、このクラスを直接使用する必要はありませんにすべてのイベントをだけ routs、 `CCustomInterpolator`-派生クラスを持つポインターのコンス トラクターに渡される`CCustomTransition`です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxanimationcontroller.h  
  
##  <a name="cinterpolatorbase"></a>  CInterpolatorBase::CInterpolatorBase  
 CInterpolatorBase オブジェクトを構築します。  
  
```  
CInterpolatorBase();
```  
  
##  <a name="createinstance"></a>  CInterpolatorBase::CreateInstance  
 CInterpolatorBase のインスタンスを作成し、イベントを処理するカスタム補間へのポインターを格納します。  
  
```  
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,  
    IUIAnimationInterpolator** ppHandler);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInterpolator`  
 カスタムのインターポレータへのポインター。  
  
 `ppHandler`  
 出力です。 関数が返す場合は、CInterpolatorBase のインスタンスへのポインターが含まれます。  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies  
 Interpolator の依存関係を取得します。  
  
```  
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValueDependencies`  
 出力です。 Interpolator の初期値に依存する要素は、SetInitialValueAndVelocity に渡されます。  
  
 `initialVelocityDependencies`  
 出力です。 Interpolator の初期速度に依存する要素は、SetInitialValueAndVelocity に渡されます。  
  
 `durationDependencies`  
 出力です。 Interpolator の期間に依存する要素は、SetDuration に渡されます。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は GetDependencies メソッドから FALSE を返す場合は E_FAIL を返します。  
  
##  <a name="getduration"></a>  CInterpolatorBase::GetDuration  
 Interpolator の期間を取得します。  
  
```  
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 出力です。 秒単位で、移行の期間です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は GetDuration メソッドから FALSE を返す場合は E_FAIL を返します。  
  
##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue  
 Interpolator が潜在顧客の最終的な値を取得します。  
  
```  
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `value`  
 出力です。 移行の最後に変数の最終的な値。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は GetFinalValue メソッドから FALSE を返す場合は E_FAIL を返します。  
  
##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue  
 指定されたオフセット値を補間します。  
  
```  
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset, 
  __out DOUBLE* value);
```  
  
### <a name="parameters"></a>パラメーター  
 `offset`  
 移行の開始からのオフセット。 オフセットは、常により大きいまたは 0 に等しい、遷移の期間よりも小さいです。 移行の期間が 0 の場合、このメソッドは呼び出されません。  
  
 `value`  
 出力です。 補間値です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は InterpolateValue メソッドから FALSE を返す場合は E_FAIL を返します。  
  
##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity  
 指定されたオフセット ベロシティを補間します。  
  
```  
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `offset`  
 移行の開始からのオフセット。 オフセットは 0 以上では常に、遷移の期間以下です。 移行の期間が 0 の場合、このメソッドは呼び出されません。  
  
 `velocity`  
 出力です。 オフセットで変数の速度です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は InterpolateVelocity メソッドから FALSE を返す場合は E_FAIL を返します。  
  
##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator  
 イベントを処理するカスタム補間へのポインターを格納します。  
  
```  
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```  
  
### <a name="parameters"></a>パラメーター  
 `pInterpolator`  
 カスタムのインターポレータへのポインター。  
  
##  <a name="setduration"></a>  CInterpolatorBase::SetDuration  
 Interpolator の期間を設定します。  
  
```  
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```  
  
### <a name="parameters"></a>パラメーター  
 `duration`  
 移行の期間です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は SetDuration メソッドから FALSE を返す場合は E_FAIL を返します。  
  
##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity  
 Interpolator の初期値と速度を設定します。  
  
```  
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue, 
  __in DOUBLE initialVelocity);
```  
  
### <a name="parameters"></a>パラメーター  
 `initialValue`  
 移行の開始時に変数の値。  
  
 `initialVelocity`  
 移行の開始時に変数の速度です。  
  
### <a name="return-value"></a>戻り値  
 メソッドが成功した場合は S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は SetInitialValueAndVelocity メソッドから FALSE を返す場合は E_FAIL を返します。  
  
## <a name="see-also"></a>関連項目  
 [クラス](../../mfc/reference/mfc-classes.md)
