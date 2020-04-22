---
title: CCustomInterpolator クラス
ms.date: 11/04/2016
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
ms.openlocfilehash: 00ce0661fa3fbde714a7299ecbbd54df7c9bcc36
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749162"
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
|[カスタム内挿器::Cカスタム内挿器](#ccustominterpolator)|オーバーロードされます。 カスタム補間オブジェクトを構築し、指定された値に対して期間と速度を初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[カスタム補間器::取得依存関係](#getdependencies)|インターポレーターの依存関係を取得します。|
|[カスタム補間器::ゲットデュレーション](#getduration)|インターポレーターの継続時間を取得します。|
|[カスタムインターポレーター:::最終値を取得します。](#getfinalvalue)|インターポレーターがリードする最終値を取得します。|
|[カスタム補間器::イニト](#init)|期間と最終値を初期化します。|
|[カスタム補間器::補間値](#interpolatevalue)|指定したオフセットの値を補間します。|
|[カスタム補間器::補間速度](#interpolatevelocity)|指定したオフセットの速度を補間します。|
|[カスタム補間器::設定期間](#setduration)|インターポレーターの継続時間を設定します。|
|[カスタム補間器:::初期値と速度の設定](#setinitialvalueandvelocity)|インターポレーターの初期値と速度を設定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[カスタム補間器::m_currentValue](#m_currentvalue)|補間された値。|
|[カスタム補間器::m_currentVelocity](#m_currentvelocity)|補間された速度。|
|[カスタム補間器::m_duration](#m_duration)|トランジションの期間。|
|[カスタム補間器::m_finalValue](#m_finalvalue)|遷移の終了時の変数の最終値。|
|[カスタム補間器::m_initialValue](#m_initialvalue)|遷移の開始時の変数の値。|
|[カスタム補間器::m_initialVelocity](#m_initialvelocity)|遷移の開始時の変数の速度。|

## <a name="remarks"></a>解説

CCustomInterpolator からクラスを派生させ、カスタム補間アルゴリズムを実装するために必要なすべてのメソッドをオーバーライドします。 このクラスへのポインターは、パラメーターとして渡す必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`CCustomInterpolator`

## <a name="requirements"></a>必要条件

**ヘッダー:** afxanimationcontroller.h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a>カスタム内挿器::Cカスタム内挿器

カスタム補間オブジェクトを構築し、すべての値をデフォルト 0 に設定します。

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
トランジションの期間。

*最終価値*

### <a name="remarks"></a>解説

CCustomInterpolator::Init を使用して、コードの後で期間と最終値を初期化します。

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a>カスタム補間器::取得依存関係

インターポレーターの依存関係を取得します。

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>パラメーター

*初期値依存関係*<br/>
出力。 初期値に基づいて行う補間の側面を設定します。

*初期速度依存*<br/>
出力。 初期速度に依存する補間の側面を設定初期値と速度に渡します。

*期間依存関係*<br/>
出力。 SetDuration に渡される期間に依存する補間器の特徴。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a>カスタム補間器::ゲットデュレーション

インターポレーターの継続時間を取得します。

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
出力。 遷移の継続時間 (秒単位)。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a>カスタムインターポレーター:::最終値を取得します。

インターポレーターがリードする最終値を取得します。

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力。 遷移の終了時の変数の最終値。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorinit"></a><a name="init"></a>カスタム補間器::イニト

期間と最終値を初期化します。

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
トランジションの期間。

*最終価値*<br/>
遷移の終了時の変数の最終値。

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a>カスタム補間器::補間値

指定したオフセットの値を補間します。

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力。 補間された値。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a>カスタム補間器::補間速度

指定したオフセットの速度を補間します。

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>パラメーター

*velocity*<br/>
出力。 オフセットでの変数の速度。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a>カスタム補間器::m_currentValue

補間された値。

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a>カスタム補間器::m_currentVelocity

補間された速度。

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a>カスタム補間器::m_duration

トランジションの期間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a>カスタム補間器::m_finalValue

遷移の終了時の変数の最終値。

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a>カスタム補間器::m_initialValue

遷移の開始時の変数の値。

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a>カスタム補間器::m_initialVelocity

遷移の開始時の変数の速度。

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a>カスタム補間器::設定期間

インターポレーターの継続時間を設定します。

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
トランジションの期間。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a>カスタム補間器:::初期値と速度の設定

インターポレーターの初期値と速度を設定します。

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*初期値*<br/>
遷移の開始時の変数の値。

*初期速度*<br/>
遷移の開始時の変数の速度。

### <a name="return-value"></a>戻り値

基本的な実装は常に TRUE を返します。 イベントを失敗する場合は、オーバーライドされた実装から FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
