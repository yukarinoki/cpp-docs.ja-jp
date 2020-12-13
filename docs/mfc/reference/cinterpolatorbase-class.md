---
description: '詳細情報: CInterpolatorBase クラス'
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
ms.openlocfilehash: 73204e8b81db862fe30058d1b2451ea468d332e8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340958"
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
|[CInterpolatorBase:: CInterpolatorBase](#cinterpolatorbase)|オブジェクトを構築 `CInterpolatorBase` します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CInterpolatorBase:: CreateInstance](#createinstance)|のインスタンスを作成 `CInterpolatorBase` し、カスタム interpolator へのポインターを格納します。これは、イベントを処理します。|
|[CInterpolatorBase:: GetDependencies](#getdependencies)|Interpolator の依存関係を取得します。 ( `CUIAnimationInterpolatorBase::GetDependencies`をオーバーライドします)。|
|[CInterpolatorBase:: GetDuration](#getduration)|Interpolator の継続時間を取得します。 ( `CUIAnimationInterpolatorBase::GetDuration`をオーバーライドします)。|
|[CInterpolatorBase:: GetFinalValue](#getfinalvalue)|Interpolator が潜在顧客の最終的な値を取得します。 ( `CUIAnimationInterpolatorBase::GetFinalValue`をオーバーライドします)。|
|[CInterpolatorBase:: InterpolateValue](#interpolatevalue)|指定されたオフセットで値を補間します (をオーバーライド `CUIAnimationInterpolatorBase::InterpolateValue` します)。|
|[CInterpolatorBase:: InterpolateVelocity](#interpolatevelocity)|指定されたオフセットで速度を補間 `CUIAnimationInterpolatorBase::InterpolateVelocity` します (オーバーライドします)。|
|[CInterpolatorBase:: SetCustomInterpolator](#setcustominterpolator)|イベントを処理するカスタム interpolator へのポインターを格納します。|
|[CInterpolatorBase:: SetDuration](#setduration)|Interpolator の継続時間 (オーバーライド) を設定し `CUIAnimationInterpolatorBase::SetDuration` ます。|
|[CInterpolatorBase:: SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Interpolator の初期値とベロシティを設定します。 ( `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`をオーバーライドします)。|

## <a name="remarks"></a>解説

このハンドラーは、 `IUIAnimationTransitionFactory::CreateTransition` `CCustomTransition` オブジェクトがアニメーション初期化プロセスの一部として作成されるときに、によって作成され、に渡されます (から開始 `CAnimationController::AnimateGroup` )。 通常、このクラスを直接使用する必要はありません。すべてのイベントを派生クラスにルーティングするだけで `CCustomInterpolator` 、そのポインターはのコンストラクターに渡され `CCustomTransition` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a> CInterpolatorBase:: CInterpolatorBase

CInterpolatorBase オブジェクトを構築します。

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a> CInterpolatorBase:: CreateInstance

CInterpolatorBase のインスタンスを作成し、カスタム interpolator へのポインターを格納します。これは、イベントを処理します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>パラメーター

*pInterpolator*<br/>
カスタム interpolator へのポインター。

*ppHandler*<br/>
出力。 関数がを返したときの CInterpolatorBase のインスタンスへのポインターを格納します。

### <a name="return-value"></a>戻り値

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a> CInterpolatorBase:: GetDependencies

Interpolator の依存関係を取得します。

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>パラメーター

*initialValueDependencies*<br/>
出力。 SetInitialValueAndVelocity に渡される初期値に依存する interpolator の側面。

*initialVelocityDependencies*<br/>
出力。 SetInitialValueAndVelocity に渡される初期速度に依存する interpolator の側面。

*durationDependencies*<br/>
出力。 SetDuration に渡された期間に依存する interpolator の側面。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が GetDependencies メソッドから FALSE を返した場合、E_FAIL を返します。

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a> CInterpolatorBase:: GetDuration

Interpolator の継続時間を取得します。

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
出力。 遷移の期間 (秒単位)。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が GetDuration メソッドから FALSE を返す場合は E_FAIL が返されます。

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a> CInterpolatorBase:: GetFinalValue

Interpolator が潜在顧客の最終的な値を取得します。

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力。 遷移の終了時の変数の最終的な値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が GetFinalValue メソッドから FALSE を返した場合、E_FAIL を返します。

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a> CInterpolatorBase:: InterpolateValue

指定されたオフセットで値を補間します。

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*offset*<br/>
遷移の開始からのオフセット。 オフセットは、常に0以上、移行の継続時間よりも短くなります。 遷移の継続時間が0の場合、このメソッドは呼び出されません。

*value*<br/>
出力。 補間値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が InterpolateValue メソッドから FALSE を返した場合、E_FAIL を返します。

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a> CInterpolatorBase:: InterpolateVelocity

指定されたオフセットで速度を補間します。

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>パラメーター

*offset*<br/>
遷移の開始からのオフセット。 オフセットは、常に0以上、移行の期間以下であることを示します。 遷移の継続時間が0の場合、このメソッドは呼び出されません。

*速度*<br/>
出力。 オフセット位置の変数の速度。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が InterpolateVelocity メソッドから FALSE を返した場合、E_FAIL を返します。

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a> CInterpolatorBase:: SetCustomInterpolator

イベントを処理するカスタム interpolator へのポインターを格納します。

```cpp
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>パラメーター

*pInterpolator*<br/>
カスタム interpolator へのポインター。

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a> CInterpolatorBase:: SetDuration

Interpolator の継続時間を設定します。

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
遷移の継続時間。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が SetDuration メソッドから FALSE を返した場合、E_FAIL を返します。

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> CInterpolatorBase:: SetInitialValueAndVelocity

Interpolator の初期値とベロシティを設定します。

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*initialValue*<br/>
遷移の開始時の変数の値。

*初期速度*<br/>
遷移の開始時の変数の速度。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が SetInitialValueAndVelocity メソッドから FALSE を返した場合、E_FAIL を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
