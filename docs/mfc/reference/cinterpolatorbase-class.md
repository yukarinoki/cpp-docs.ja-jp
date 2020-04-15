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
ms.openlocfilehash: e5294aabc42301e2f874d5b8328d648f4deeb3c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372351"
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
|[インターポレーターベース::インターポレーターベース](#cinterpolatorbase)|オブジェクトを`CInterpolatorBase`構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[インターポレーターベース::インスタンスの作成](#createinstance)|イベントを処理する`CInterpolatorBase`カスタム補間ツールへのポインターを作成し、格納します。|
|[インターポレーターベース::取得依存関係](#getdependencies)|インターポレーターの依存関係を取得します。 ( `CUIAnimationInterpolatorBase::GetDependencies`をオーバーライドします)。|
|[インターポレーターベース::ゲットデュレーション](#getduration)|インターポレーターの継続時間を取得します。 ( `CUIAnimationInterpolatorBase::GetDuration`をオーバーライドします)。|
|[インターポレーターベース::ゲットファイナルバリュー](#getfinalvalue)|インターポレーターがリードする最終値を取得します。 ( `CUIAnimationInterpolatorBase::GetFinalValue`をオーバーライドします)。|
|[インターポレーターベース:補間値](#interpolatevalue)|指定したオフセットの値を補間`CUIAnimationInterpolatorBase::InterpolateValue`します (オーバーライド .|
|[インターポレーターベース::インターポレート速度](#interpolatevelocity)|指定されたオフセットでの速度を補間`CUIAnimationInterpolatorBase::InterpolateVelocity`します (オーバーライド.|
|[インターポレーターベース::カスタム補間器の設定](#setcustominterpolator)|イベントを処理するカスタム補間ツールへのポインターを格納します。|
|[インターポレーターベース::設定期間](#setduration)|インターポレーターの継続時間を設定`CUIAnimationInterpolatorBase::SetDuration`します (オーバーライドします)。|
|[インターポレーターベース::セット初期値と速度](#setinitialvalueandvelocity)|インターポレーターの初期値と速度を設定します。 ( `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`をオーバーライドします)。|

## <a name="remarks"></a>解説

このハンドラは、`IUIAnimationTransitionFactory::CreateTransition``CCustomTransition`オブジェクトがアニメーション初期化プロセスの一部として作成されるときに作成され、渡されます (`CAnimationController::AnimateGroup`によって開始されます)。 通常、このクラスを直接`CCustomInterpolator``CCustomTransition`使用する必要はありません。

## <a name="inheritance-hierarchy"></a>継承階層

`CUIAnimationCallbackBase`

`CUIAnimationInterpolatorBase`

`CInterpolatorBase`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="cinterpolatorbasecinterpolatorbase"></a><a name="cinterpolatorbase"></a>インターポレーターベース::インターポレーターベース

CInterpolatorBase オブジェクトを構築します。

```
CInterpolatorBase();
```

## <a name="cinterpolatorbasecreateinstance"></a><a name="createinstance"></a>インターポレーターベース::インスタンスの作成

CInterpolatorBase のインスタンスを作成し、イベントを処理するカスタム補間機能へのポインターを格納します。

```
static COM_DECLSPEC_NOTHROW HRESULT CreateInstance(
    CCustomInterpolator* pInterpolator,
    IUIAnimationInterpolator** ppHandler);
```

### <a name="parameters"></a>パラメーター

*pインターポレーター*<br/>
カスタム補間器へのポインター。

*ppHandler*<br/>
出力。 関数が返されるときに CInterpolatorBase のインスタンスへのポインターを格納します。

### <a name="return-value"></a>戻り値

## <a name="cinterpolatorbasegetdependencies"></a><a name="getdependencies"></a>インターポレーターベース::取得依存関係

インターポレーターの依存関係を取得します。

```
IFACEMETHOD(GetDependencies)(
    __out UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    __out UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    __out UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>パラメーター

*初期値依存関係*<br/>
出力。 初期値に基づいて行う補間の側面を設定します。

*初期速度依存*<br/>
出力。 初期速度に依存する補間の側面を設定初期値と速度に渡します。

*期間依存関係*<br/>
出力。 SetDuration に渡される期間に依存する補間器の特徴。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が GetDependencies メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="cinterpolatorbasegetduration"></a><a name="getduration"></a>インターポレーターベース::ゲットデュレーション

インターポレーターの継続時間を取得します。

```
IFACEMETHOD(GetDuration)(__out UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
出力。 遷移の継続時間 (秒単位)。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が GetDuration メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="cinterpolatorbasegetfinalvalue"></a><a name="getfinalvalue"></a>インターポレーターベース::ゲットファイナルバリュー

インターポレーターがリードする最終値を取得します。

```
IFACEMETHOD(GetFinalValue)(__out DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力。 遷移の終了時の変数の最終値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が GetFinalValue メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="cinterpolatorbaseinterpolatevalue"></a><a name="interpolatevalue"></a>インターポレーターベース:補間値

指定したオフセットの値を補間します。

```
IFACEMETHOD(InterpolateValue)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*offset*<br/>
トランジションの開始からのオフセット。 オフセットは、常にゼロ以上であり、トランジションの継続時間より小さい値です。 トランジションの継続時間が 0 の場合、このメソッドは呼び出されません。

*value*<br/>
出力。 補間された値。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装がインターポレート値メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="cinterpolatorbaseinterpolatevelocity"></a><a name="interpolatevelocity"></a>インターポレーターベース::インターポレート速度

指定したオフセットの速度を補間します。

```
IFACEMETHOD(InterpolateVelocity)(
    __in UI_ANIMATION_SECONDS offset,
    __out DOUBLE* velocity);
```

### <a name="parameters"></a>パラメーター

*offset*<br/>
トランジションの開始からのオフセット。 オフセットは、常に 0 以上、遷移の継続時間以下になります。 トランジションの継続時間が 0 の場合、このメソッドは呼び出されません。

*velocity*<br/>
出力。 オフセットでの変数の速度。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装がインターポレート速度メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="cinterpolatorbasesetcustominterpolator"></a><a name="setcustominterpolator"></a>インターポレーターベース::カスタム補間器の設定

イベントを処理するカスタム補間ツールへのポインターを格納します。

```
void SetCustomInterpolator(CCustomInterpolator* pInterpolator);
```

### <a name="parameters"></a>パラメーター

*pインターポレーター*<br/>
カスタム補間器へのポインター。

## <a name="cinterpolatorbasesetduration"></a><a name="setduration"></a>インターポレーターベース::設定期間

インターポレーターの継続時間を設定します。

```
IFACEMETHOD(SetDuration)(__in UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*期間*<br/>
トランジションの期間。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が SetDuration メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="cinterpolatorbasesetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>インターポレーターベース::セット初期値と速度

インターポレーターの初期値と速度を設定します。

```
IFACEMETHOD(SetInitialValueAndVelocity)(
    __in DOUBLE initialValue,
    __in DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*初期値*<br/>
遷移の開始時の変数の値。

*初期速度*<br/>
遷移の開始時の変数の速度。

### <a name="return-value"></a>戻り値

メソッドが成功した場合は、S_OK を返します。 CCustomInterpolator が設定されていない場合、またはカスタム実装が SetInitialValueAndVelocity メソッドから FALSE を返す場合は、E_FAILを返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
