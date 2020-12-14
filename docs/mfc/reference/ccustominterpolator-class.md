---
description: '詳細情報: CCustomInterpolator クラス'
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
ms.openlocfilehash: 84fcdc20ce1a90441a508f1469d498095980af83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227755"
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
|[CCustomInterpolator:: CCustomInterpolator](#ccustominterpolator)|オーバーロードされます。 カスタム interpolator オブジェクトを構築し、指定された値に対して duration とベロシティを初期化します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CCustomInterpolator:: GetDependencies](#getdependencies)|Interpolator の依存関係を取得します。|
|[CCustomInterpolator:: GetDuration](#getduration)|Interpolator の継続時間を取得します。|
|[CCustomInterpolator:: GetFinalValue](#getfinalvalue)|Interpolator が潜在顧客の最終的な値を取得します。|
|[CCustomInterpolator:: Init](#init)|Duration と final 値を初期化します。|
|[CCustomInterpolator:: InterpolateValue](#interpolatevalue)|指定されたオフセットで値を補間します。|
|[CCustomInterpolator:: InterpolateVelocity](#interpolatevelocity)|指定されたオフセットで速度を補間します。|
|[CCustomInterpolator:: SetDuration](#setduration)|Interpolator の継続時間を設定します。|
|[CCustomInterpolator:: SetInitialValueAndVelocity](#setinitialvalueandvelocity)|Interpolator の初期値とベロシティを設定します。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|名前|説明|
|----------|-----------------|
|[CCustomInterpolator:: m_currentValue](#m_currentvalue)|補間値。|
|[CCustomInterpolator:: m_currentVelocity](#m_currentvelocity)|補間されたベロシティ。|
|[CCustomInterpolator:: m_duration](#m_duration)|遷移の継続時間。|
|[CCustomInterpolator:: m_finalValue](#m_finalvalue)|遷移の終了時の変数の最終的な値。|
|[CCustomInterpolator:: m_initialValue](#m_initialvalue)|遷移の開始時の変数の値。|
|[CCustomInterpolator:: m_initialVelocity](#m_initialvelocity)|遷移の開始時の変数の速度。|

## <a name="remarks"></a>解説

CCustomInterpolator からクラスを派生させ、カスタム補間アルゴリズムを実装するために必要なすべてのメソッドをオーバーライドします。 このクラスへのポインターは、CCustomTransition にパラメーターとして渡す必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`CCustomInterpolator`

## <a name="requirements"></a>要件

**ヘッダー:** afxanimationcontroller.h

## <a name="ccustominterpolatorccustominterpolator"></a><a name="ccustominterpolator"></a> CCustomInterpolator:: CCustomInterpolator

カスタム interpolator オブジェクトを構築し、すべての値を既定値の0に設定します。

```
CCustomInterpolator();

CCustomInterpolator(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
遷移の継続時間。

*finalValue*

### <a name="remarks"></a>解説

CCustomInterpolator:: Init を使用して、コードの後の期間と最終的な値を初期化します。

## <a name="ccustominterpolatorgetdependencies"></a><a name="getdependencies"></a> CCustomInterpolator:: GetDependencies

Interpolator の依存関係を取得します。

```
virtual BOOL GetDependencies(
    UI_ANIMATION_DEPENDENCIES* initialValueDependencies,
    UI_ANIMATION_DEPENDENCIES* initialVelocityDependencies,
    UI_ANIMATION_DEPENDENCIES* durationDependencies);
```

### <a name="parameters"></a>パラメーター

*initialValueDependencies*<br/>
出力。 SetInitialValueAndVelocity に渡される初期値に依存する interpolator の側面。

*initialVelocityDependencies*<br/>
出力。 SetInitialValueAndVelocity に渡される初期速度に依存する interpolator の側面。

*durationDependencies*<br/>
出力。 SetDuration に渡された期間に依存する interpolator の側面。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorgetduration"></a><a name="getduration"></a> CCustomInterpolator:: GetDuration

Interpolator の継続時間を取得します。

```
virtual BOOL GetDuration(UI_ANIMATION_SECONDS* duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
出力。 遷移の期間 (秒単位)。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorgetfinalvalue"></a><a name="getfinalvalue"></a> CCustomInterpolator:: GetFinalValue

Interpolator が潜在顧客の最終的な値を取得します。

```
virtual BOOL GetFinalValue(DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力。 遷移の終了時の変数の最終的な値。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorinit"></a><a name="init"></a> CCustomInterpolator:: Init

Duration と final 値を初期化します。

```cpp
void Init(
    UI_ANIMATION_SECONDS duration,
    DOUBLE finalValue);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
遷移の継続時間。

*finalValue*<br/>
遷移の終了時の変数の最終的な値。

## <a name="ccustominterpolatorinterpolatevalue"></a><a name="interpolatevalue"></a> CCustomInterpolator:: InterpolateValue

指定されたオフセットで値を補間します。

```
virtual BOOL InterpolateValue(
    UI_ANIMATION_SECONDS */,
    DOUBLE* value);
```

### <a name="parameters"></a>パラメーター

*value*<br/>
出力。 補間値。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorinterpolatevelocity"></a><a name="interpolatevelocity"></a> CCustomInterpolator:: InterpolateVelocity

指定されたオフセットで速度を補間します。

```
virtual BOOL InterpolateVelocity(
    UI_ANIMATION_SECONDS */,
    DOUBLE* velocity);
```

### <a name="parameters"></a>パラメーター

*速度*<br/>
出力。 オフセット位置の変数の速度。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorm_currentvalue"></a><a name="m_currentvalue"></a> CCustomInterpolator:: m_currentValue

補間値。

```
DOUBLE m_currentValue;
```

## <a name="ccustominterpolatorm_currentvelocity"></a><a name="m_currentvelocity"></a> CCustomInterpolator:: m_currentVelocity

補間されたベロシティ。

```
DOUBLE m_currentVelocity;
```

## <a name="ccustominterpolatorm_duration"></a><a name="m_duration"></a> CCustomInterpolator:: m_duration

遷移の継続時間。

```
UI_ANIMATION_SECONDS m_duration;
```

## <a name="ccustominterpolatorm_finalvalue"></a><a name="m_finalvalue"></a> CCustomInterpolator:: m_finalValue

遷移の終了時の変数の最終的な値。

```
DOUBLE m_finalValue;
```

## <a name="ccustominterpolatorm_initialvalue"></a><a name="m_initialvalue"></a> CCustomInterpolator:: m_initialValue

遷移の開始時の変数の値。

```
DOUBLE m_initialValue;
```

## <a name="ccustominterpolatorm_initialvelocity"></a><a name="m_initialvelocity"></a> CCustomInterpolator:: m_initialVelocity

遷移の開始時の変数の速度。

```
DOUBLE m_initialVelocity;
```

## <a name="ccustominterpolatorsetduration"></a><a name="setduration"></a> CCustomInterpolator:: SetDuration

Interpolator の継続時間を設定します。

```
virtual BOOL SetDuration(UI_ANIMATION_SECONDS duration);
```

### <a name="parameters"></a>パラメーター

*duration*<br/>
遷移の継続時間。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="ccustominterpolatorsetinitialvalueandvelocity"></a><a name="setinitialvalueandvelocity"></a> CCustomInterpolator:: SetInitialValueAndVelocity

Interpolator の初期値とベロシティを設定します。

```
virtual BOOL SetInitialValueAndVelocity(
    DOUBLE initialValue,
    DOUBLE initialVelocity);
```

### <a name="parameters"></a>パラメーター

*initialValue*<br/>
遷移の開始時の変数の値。

*初期速度*<br/>
遷移の開始時の変数の速度。

### <a name="return-value"></a>戻り値

基本実装では常に TRUE が返されます。 イベントを失敗させる場合は、オーバーライドされた実装から FALSE を返します。

## <a name="see-also"></a>関連項目

[クラス](../../mfc/reference/mfc-classes.md)
