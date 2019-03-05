---
title: CInterpolatorBase クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 379aa5607e459ad8acfd99c5899315afb84ac4a3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57302287"
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
|[CInterpolatorBase::CreateInstance](#createinstance)|インスタンスを作成します`CInterpolatorBase`し、イベントを処理するカスタム補間へのポインターを格納します。|
|[CInterpolatorBase::GetDependencies](#getdependencies)|補間の依存関係を取得します。 ( `CUIAnimationInterpolatorBase::GetDependencies`をオーバーライドします)。|
|[CInterpolatorBase::GetDuration](#getduration)|インターポレーターの期間を取得します。 ( `CUIAnimationInterpolatorBase::GetDuration`をオーバーライドします)。|
|[CInterpolatorBase::GetFinalValue](#getfinalvalue)|Interpolator が潜在顧客の最終的な値を取得します。 ( `CUIAnimationInterpolatorBase::GetFinalValue`をオーバーライドします)。|
|[CInterpolatorBase::InterpolateValue](#interpolatevalue)|指定されたオフセット値を補間 (オーバーライド`CUIAnimationInterpolatorBase::InterpolateValue`)。|
|[CInterpolatorBase::InterpolateVelocity](#interpolatevelocity)|指定されたオフセット ベロシティの補間 (オーバーライド`CUIAnimationInterpolatorBase::InterpolateVelocity`)。|
|[CInterpolatorBase::SetCustomInterpolator](#setcustominterpolator)|イベントを処理するカスタム補間へのポインターを格納します。|
|[CInterpolatorBase::SetDuration](#setduration)|インターポレーターの期間を設定 (オーバーライド`CUIAnimationInterpolatorBase::SetDuration`)。|
|[CInterpolatorBase::SetInitialValueAndVelocity](#setinitialvalueandvelocity)|インターポレーターの初期値と速度を設定します。 ( `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`をオーバーライドします)。|

## <a name="remarks"></a>Remarks

このハンドラーが作成されに渡される`IUIAnimationTransitionFactory::CreateTransition`ときに、`CCustomTransition`アニメーション初期化プロセスの一部としてオブジェクトが作成される (によって開始された`CAnimationController::AnimateGroup`)。 通常、このクラスを直接使用する必要はありませんにすべてのイベントをだけ routs、 `CCustomInterpolator`-派生クラスでのコンス トラクターに渡されるポインターが`CCustomTransition`します。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>必要条件

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

*pInterpolator*<br/>
カスタム インターポレーターへのポインター。

*ppHandler*<br/>
出力します。 関数が返す場合は、CInterpolatorBase のインスタンスへのポインターが含まれています。

### <a name="return-value"></a>戻り値

##  <a name="getdependencies"></a>  CInterpolatorBase::GetDependencies

補間の依存関係を取得します。

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>パラメーター

*initialValueDependencies*<br/>
出力します。 Interpolator の初期値に依存する側面は、SetInitialValueAndVelocity に渡されます。

*initialVelocityDependencies*<br/>
出力します。 Interpolator の初期速度に依存する側面は、SetInitialValueAndVelocity に渡されます。

*durationDependencies*<br/>
出力します。 Interpolator の期間に依存する側面は、SetDuration に渡されます。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は、GetDependencies メソッドから FALSE を返しますの場合は E_FAIL を返します。

##  <a name="getduration"></a>  CInterpolatorBase::GetDuration

インターポレーターの期間を取得します。

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
出力します。 秒単位での移行の期間です。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は GetDuration メソッドから FALSE を返しますの場合は E_FAIL を返します。

##  <a name="getfinalvalue"></a>  CInterpolatorBase::GetFinalValue

Interpolator が潜在顧客の最終的な値を取得します。

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力します。 移行の最後に変数の最終的な値。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は GetFinalValue メソッドから FALSE を返しますの場合は E_FAIL を返します。

##  <a name="interpolatevalue"></a>  CInterpolatorBase::InterpolateValue

指定されたオフセット値を補間します。

```
IFACEMETHOD(InterpolateValue)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
移行の開始からのオフセット。 オフセットは、常により大きいまたは 0 に等しいと遷移の期間より小さい。 遷移の期間が 0 の場合、このメソッドは呼び出されません。

*value*<br/>
出力します。 補間値。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は InterpolateValue メソッドから FALSE を返しますの場合は E_FAIL を返します。

##  <a name="interpolatevelocity"></a>  CInterpolatorBase::InterpolateVelocity

指定されたオフセット ベロシティの補間します。

```
IFACEMETHOD(InterpolateVelocity)(
  __in UI_ANIMATION_SECONDS offset,
  __out DOUBLE* velocity);
```

### <a name="parameters"></a>パラメーター

*オフセット*<br/>
移行の開始からのオフセット。 オフセットは 0 以上では常に、遷移の期間。 遷移の期間が 0 の場合、このメソッドは呼び出されません。

*ベロシティ*<br/>
出力します。 オフセットで変数の速度。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は InterpolateVelocity メソッドから FALSE を返しますの場合は E_FAIL を返します。

##  <a name="setcustominterpolator"></a>  CInterpolatorBase::SetCustomInterpolator

イベントを処理するカスタム補間へのポインターを格納します。

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>パラメーター

*pInterpolator*<br/>
カスタム インターポレーターへのポインター。

##  <a name="setduration"></a>  CInterpolatorBase::SetDuration

インターポレーターの期間を設定します。

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
移行の期間です。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は、SetDuration メソッドから FALSE を返しますの場合は E_FAIL を返します。

##  <a name="setinitialvalueandvelocity"></a>  CInterpolatorBase::SetInitialValueAndVelocity

インターポレーターの初期値と速度を設定します。

```
IFACEMETHOD(SetInitialValueAndVelocity)(
  __in DOUBLE initialValue,
  __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*initialValue*<br/>
移行の開始時の変数の値。

*initialVelocity*<br/>
移行の開始時の変数の速度。

### <a name="return-value"></a>戻り値

メソッドが成功すると、S_OK を返します。 CCustomInterpolator が設定されていない、またはカスタムの実装は SetInitialValueAndVelocity メソッドから FALSE を返しますの場合は E_FAIL を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
