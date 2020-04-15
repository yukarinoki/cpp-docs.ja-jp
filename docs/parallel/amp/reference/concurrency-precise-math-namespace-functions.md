---
title: Concurrency::precise_math 名前空間関数
ms.date: 11/04/2016
f1_keywords:
- amp_math/Concurrency::precise_math::acos
- amp_math/Concurrency::precise_math::acosh
- amp_math/Concurrency::precise_math::acoshf
- amp_math/Concurrency::precise_math::asinf
- amp_math/Concurrency::precise_math::asinh
- amp_math/Concurrency::precise_math::atan
- amp_math/Concurrency::precise_math::atan2
- amp_math/Concurrency::precise_math::atanf
- amp_math/Concurrency::precise_math::atanh
- amp_math/Concurrency::precise_math::cbrt
- amp_math/Concurrency::precise_math::cbrtf
- amp_math/Concurrency::precise_math::ceilf
- amp_math/Concurrency::precise_math::copysign
- amp_math/Concurrency::precise_math::cos
- amp_math/Concurrency::precise_math::cosf
- amp_math/Concurrency::precise_math::coshf
- amp_math/Concurrency::precise_math::cospi
- amp_math/Concurrency::precise_math::erf
- amp_math/Concurrency::precise_math::erfc
- amp_math/Concurrency::precise_math::erfcinv
- amp_math/Concurrency::precise_math::erfcinvf
- amp_math/Concurrency::precise_math::erfinv
- amp_math/Concurrency::precise_math::erfinvf
- amp_math/Concurrency::precise_math::exp10
- amp_math/Concurrency::precise_math::exp10f
- amp_math/Concurrency::precise_math::exp2f
- amp_math/Concurrency::precise_math::expf
- amp_math/Concurrency::precise_math::expm1f
- amp_math/Concurrency::precise_math::fabs
- amp_math/Concurrency::precise_math::floor
- amp_math/Concurrency::precise_math::fdim
- amp_math/Concurrency::precise_math::floorf
- amp_math/Concurrency::precise_math::fmaf
- amp_math/Concurrency::precise_math::fmaxf
- amp_math/Concurrency::precise_math::fmin
- amp_math/Concurrency::precise_math::fmod
- amp_math/Concurrency::precise_math::fmodf
- amp_math/Concurrency::precise_math::frexp
- amp_math/Concurrency::precise_math::frexpf
- amp_math/Concurrency::precise_math::hypotf
- amp_math/Concurrency::precise_math::ilogb
- amp_math/Concurrency::precise_math::isfinite
- amp_math/Concurrency::precise_math::isinf
- amp_math/Concurrency::precise_math::isnormal
- amp_math/Concurrency::precise_math::ldexp
- amp_math/Concurrency::precise_math::lgamma
- amp_math/Concurrency::precise_math::lgammaf
- amp_math/Concurrency::precise_math::log10
- amp_math/Concurrency::precise_math::log10f
- amp_math/Concurrency::precise_math::log1pf
- amp_math/Concurrency::precise_math::log2
- amp_math/Concurrency::precise_math::logb
- amp_math/Concurrency::precise_math::logbf
- amp_math/Concurrency::precise_math::modf
- amp_math/Concurrency::precise_math::modff
- amp_math/Concurrency::precise_math::nanf
- amp_math/Concurrency::precise_math::nearbyint
- amp_math/Concurrency::precise_math::nextafter
- amp_math/Concurrency::precise_math::nextafterf
- amp_math/Concurrency::precise_math::phif
- amp_math/Concurrency::precise_math::pow
- amp_math/Concurrency::precise_math::probit
- amp_math/Concurrency::precise_math::probitf
- amp_math/Concurrency::precise_math::rcbrtf
- amp_math/Concurrency::precise_math::remainder
- amp_math/Concurrency::precise_math::remquo
- amp_math/Concurrency::precise_math::remquof
- amp_math/Concurrency::precise_math::roundf
- amp_math/Concurrency::precise_math::rsqrt
- amp_math/Concurrency::precise_math::scalb
- amp_math/Concurrency::precise_math::scalbf
- amp_math/Concurrency::precise_math::scalbnf
- amp_math/Concurrency::precise_math::signbit
- amp_math/Concurrency::precise_math::sin
- amp_math/Concurrency::precise_math::sincos
- amp_math/Concurrency::precise_math::sinf
- amp_math/Concurrency::precise_math::sinh
- amp_math/Concurrency::precise_math::sinpi
- amp_math/Concurrency::precise_math::sinpif
- amp_math/Concurrency::precise_math::sqrtf
- amp_math/Concurrency::precise_math::tan
- amp_math/Concurrency::precise_math::tanh
- amp_math/Concurrency::precise_math::tanhf
- amp_math/Concurrency::precise_math::tanpif
- amp_math/Concurrency::precise_math::tgamma
- amp_math/Concurrency::precise_math::trunc
- amp_math/Concurrency::precise_math::truncf
ms.assetid: fae53ab4-d1c5-45bb-a6a0-a74258e9aea3
ms.openlocfilehash: ee6ab2313fbdc288ebba1b3fdacf192b7b578eb6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321840"
---
# <a name="concurrencyprecise_math-namespace-functions"></a>Concurrency::precise_math 名前空間関数

||||
|-|-|-|
|[Acos](#acos)|[acosf](#acosf)|[アコッシュ](#acosh)|
|[acoshf](#acoshf)|[Asin](#asin)|[asinf](#asinf)|
|[アシン](#asinh)|[asinhf](#asinhf)|[Atan](#atan)|
|[atan2](#atan2)|[atan2f](#atan2f)|[atanf](#atanf)|
|[アタン](#atanh)|[atanhf](#atanhf)|[cbrt](#cbrt)|
|[cbrtf](#cbrtf)|[セイル](#ceil)|[ceilf](#ceilf)|
|[コピーサイン](#copysign)|[copysignf](#copysignf)|[Cos](#cos)|
|[cosf](#cosf)|[Cosh](#cosh)|[coshf](#coshf)|
|[コスピ](#cospi)|[コスピフ](#cospif)|[Erf](#erf)|
|[エrfc](#erfc)|[erfcf](#erfcf)|[エrfcinv](#erfcinv)|
|[エrfcinvf](#erfcinvf)|[erff](#erff)|[エルフィンフ](#erfinv)|
|[エルフィンフフ](#erfinvf)|[Exp](#exp)|[exp10](#exp10)|
|[exp10f](#exp10f)|[exp2](#exp2)|[exp2f](#exp2f)|
|[expf](#expf)|[expm1](#expm1)|[expm1f](#expm1f)|
|[fabs](#fabs)|[fabsf](#fabsf)|[床](#floor)|
|[fdim](#fdim)|[fdimf](#fdimf)||
|[floorf](#floorf)|[fma](#fma)|[fmaf](#fmaf)|
[fmax](#fmax)|[fmaxf](#fmaxf)||
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|
|[fmodf](#fmodf)|[fpclassify](#fpclassify)|[frexp](#frexp)|
|[フインシュフ](#frexpf)|[hypot](#hypot)|[ハイポtf](#hypotf)|
|[ilogb](#ilogb)|[ilogbf](#ilogbf)|[イスフィント](#isfinite)|
|[イシンフ](#isinf)|[Isnan](#isnan)|[isnormal](#isnormal)|
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[lgamma](#lgamma)|
|[lgammaf](#lgammaf)|[ログ](#log)|[ログ10](#log10)|
|[log10f](#log10f)|[log1p](#log1p)|[log1pf](#log1pf)|
|[ログ2](#log2)|[log2f](#log2f)|[logb](#logb)|
|[logbf](#logbf)|[logf](#logf)|[modf](#modf)|
|[modff](#modff)|[nan](#nan)|[nanf](#nanf)|
|[nearbyint](#nearbyint)|[nearbyintf](#nearbyintf)|[nextafter](#nextafter)|
|[次のアフターフ](#nextafterf)|[ファイ](#phi)|[ファイフ](#phif)|
|[えい](#pow)|[powf](#powf)|[プロビット](#probit)|
|[プロビトフ](#probitf)|[rcbrt](#rcbrt)|[rcbrtf](#rcbrtf)|
|[残り](#remainder)|[remainderf](#remainderf)|[remquo](#remquo)|
|[remquof](#remquof)|[ラウンド](#round)|[roundf](#roundf)|
|[rsqrt](#rsqrt)|[を使用します。](#rsqrtf)|[スカルブ](#scalb)|
|[スカルBF](#scalbf)|[scalbn](#scalbn)|[scalbnf](#scalbnf)|
|[signbit](#signbit)|[サインビットフ](#signbitf)|[罪](#sin)|
|[シンコス](#sincos)|[シンコスフ](#sincosf)|[sinf](#sinf)|
|[sinh](#sinh)|[sinhf](#sinhf)|[シンピ](#sinpi)|
|[シンピフ](#sinpif)|[Sqrt](#sqrt)|[sqrtf](#sqrtf)|
|[日焼け](#tan)|[tanf](#tanf)|[Tanh](#tanh)|
|[tanhf](#tanhf)|[タンピ](#tanpi)|[タンピフ](#tanpif)|
|[tgamma](#tgamma)|[tgammaf](#tgammaf)|[トランク](#trunc)|
|[truncf](#truncf)|

## <a name="acos"></a><a name="acos"></a>Acos

引数の逆余弦を計算します。

```cpp
inline float acos(float _X) restrict(amp);

inline double acos(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のアークコサイン値を返します。

## <a name="acosf"></a><a name="acosf"></a>アコスフ

引数の逆余弦を計算します。

```cpp
inline float acosf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のアークコサイン値を返します。

## <a name="acosh"></a><a name="acosh"></a>アコッシュ

引数の逆双曲線余弦を計算します。

```cpp
inline float acosh(float _X) restrict(amp);

inline double acosh(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆双曲線コサイン値を返します。

## <a name="acoshf"></a><a name="acoshf"></a>アコスフ

引数の逆双曲線余弦を計算します。

```cpp
inline float acoshf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆双曲線コサイン値を返します。

## <a name="asin"></a><a name="asin"></a>Asin

引数の逆正弦を計算します。

```cpp
inline float asin(float _X) restrict(amp);

inline double asin(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のアークセイン値を返します。

## <a name="asinf"></a><a name="asinf"></a>アシンフ

引数の逆正弦を計算します。

```cpp
inline float asinf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のアークセイン値を返します。

## <a name="asinh"></a><a name="asinh"></a>アシン

引数の逆双曲線サインを計算します。

```cpp
inline float asinh(float _X) restrict(amp);

inline double asinh(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆双曲線正弦の値を返します。

## <a name="asinhf"></a><a name="asinhf"></a>アシンフ

引数の逆双曲線サインを計算します。

```cpp
inline float asinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆双曲線正弦の値を返します。

## <a name="atan"></a><a name="atan"></a>Atan

引数の逆正接を計算します。

```cpp
inline float atan(float _X) restrict(amp);

inline double atan(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のアークタンジェント値を返します。

## <a name="atan2"></a><a name="atan2"></a>atan2

_Y/_X の逆正接を計算します。

```cpp
inline float atan2(
    float _Y,
    float _X) restrict(amp);

inline double atan2(
    double _Y,
    double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_y*<br/>
浮動小数点値

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Y/_Xのアークタンジェント値を返します。

## <a name="atan2f"></a><a name="atan2f"></a>atan2f

_Y/_X の逆正接を計算します。

```cpp
inline float atan2f(
    float _Y,
    float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_y*<br/>
浮動小数点値

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Y/_Xのアークタンジェント値を返します。

## <a name="atanf"></a><a name="atanf"></a>アタンフ

引数の逆正接を計算します。

```cpp
inline float atanf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のアークタンジェント値を返します。

## <a name="atanh"></a><a name="atanh"></a>アタン

引数の逆双曲線タンジェントを計算します。

```cpp
inline float atanh(float _X) restrict(amp);

inline double atanh(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆双曲線正接値を返します。

## <a name="atanhf"></a><a name="atanhf"></a>アタンフ

引数の逆双曲線タンジェントを計算します。

```cpp
inline float atanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆双曲線正接値を返します。

## <a name="cbrt"></a><a name="cbrt"></a>cbrt

引数の実際のキューブ ルートを計算します。

```cpp
inline float cbrt(float _X) restrict(amp);

inline double cbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の実際の立方体のルートを返します。

## <a name="cbrtf"></a><a name="cbrtf"></a>cbrtf

引数の実際のキューブ ルートを計算します。

```cpp
inline float cbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の実際の立方体のルートを返します。

## <a name="ceil"></a><a name="ceil"></a>セイル

引数の切り上げを計算します。

```cpp
inline float ceil(float _X) restrict(amp);

inline double ceil(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の上限を返します。

## <a name="ceilf"></a><a name="ceilf"></a>セイルフ

引数の切り上げを計算します。

```cpp
inline float ceilf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の上限を返します。

## <a name="copysign"></a><a name="copysign"></a>コピーサイン

_Xの大きさと記号を持つ値を生成_Y

```cpp
inline float copysign(
    float _X,
    float _Y) restrict(amp);

inline double copysign(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの大きさと_Yの符号を持つ値を返します。

## <a name="copysignf"></a><a name="copysignf"></a>コピーサイン

_Xの大きさと記号を持つ値を生成_Y

```cpp
inline float copysignf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの大きさと_Yの符号を持つ値を返します。

## <a name="cos"></a><a name="cos"></a>Cos

引数の余弦を計算します。

```cpp
inline float cos(float _X) restrict(amp);

inline double cos(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の余弦値を返します。

## <a name="cosf"></a><a name="cosf"></a>コスフ

引数の余弦を計算します。

```cpp
inline float cosf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の余弦値を返します。

## <a name="cosh"></a><a name="cosh"></a>Cosh

引数の双曲線余弦の値を計算します。

```cpp
inline float cosh(float _X) restrict(amp);

inline double cosh(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の双曲線余弦値を返します。

## <a name="coshf"></a><a name="coshf"></a>コスフ

引数の双曲線余弦の値を計算します。

```cpp
inline float coshf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の双曲線余弦値を返します。

## <a name="cospi"></a><a name="cospi"></a>コスピ

pi \* _Xの余弦値を計算します。

```cpp
inline float cospi(float _X) restrict(amp);

inline double cospi(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

pi \* _Xの余弦値を返します。

## <a name="cospif"></a><a name="cospif"></a>コスピフ

pi \* _Xの余弦値を計算します。

```cpp
inline float cospif(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

pi \* _Xの余弦値を返します。

## <a name="erf"></a><a name="erf"></a>Erf

_Xのエラー関数を計算します。

```cpp
inline float erf(float _X) restrict(amp);

inline double erf(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xのエラー関数を返します。

## <a name="erfc"></a><a name="erfc"></a>エrfc

_Xの相補誤差関数を計算します。

```cpp
inline float erfc(float _X) restrict(amp);

inline double erfc(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの相補誤差関数を返します。

## <a name="erfcf"></a><a name="erfcf"></a>エrfcf

_Xの相補誤差関数を計算します。

```cpp
inline float erfcf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの相補誤差関数を返します。

## <a name="erfcinv"></a><a name="erfcinv"></a>エrfcinv

_Xの逆補完誤差関数を計算します。

```cpp
inline float erfcinv(float _X) restrict(amp);

inline double erfcinv(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの逆補完誤差関数を返します。

## <a name="erfcinvf"></a><a name="erfcinvf"></a>エrfcinvf

_Xの逆補完誤差関数を計算します。

```cpp
inline float erfcinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの逆補完誤差関数を返します。

## <a name="erff"></a><a name="erff"></a>エルフ

_Xのエラー関数を計算します。

```cpp
inline float erff(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xのエラー関数を返します。

## <a name="erfinv"></a><a name="erfinv"></a>エルフィンフ

_Xの逆エラー関数を計算します。

```cpp
inline float erfinv(float _X) restrict(amp);

inline double erfinv(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの逆エラー関数を返します。

## <a name="erfinvf"></a><a name="erfinvf"></a>エルフィンフフ

_Xの逆エラー関数を計算します。

```cpp
inline float erfinvf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの逆エラー関数を返します。

## <a name="exp10"></a><a name="exp10"></a>exp10

引数の底10指数を計算します。

```cpp
inline float exp10(float _X) restrict(amp);

inline double exp10(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の底 10 の指数を返します。

## <a name="exp10f"></a><a name="exp10f"></a>exp10f

引数の底10指数を計算します。

```cpp
inline float exp10f(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の底 10 の指数を返します。

## <a name="expm1"></a><a name="expm1"></a>1

e を底とする引数のべき乗マイナス 1 を計算します。

```cpp
inline float expm1(float exponent) restrict(amp);

inline double expm1(double exponent) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*指数*<br/>
n の*数式*`e`の指数語 n<sup>は</sup>`e`、自然対数の底です。

### <a name="return-value"></a>戻り値

e を底とする引数のべき乗マイナス 1 を返します。

## <a name="expm1f"></a><a name="expm1f"></a>expm1f

e を底とする引数のべき乗マイナス 1 を計算します。

```cpp
inline float expm1f(float exponent) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*指数*<br/>
n の*数式*`e`の指数語 n<sup>は</sup>`e`、自然対数の底です。

### <a name="return-value"></a>戻り値

e を底とする引数のべき乗マイナス 1 を返します。

## <a name="exp"></a><a name="exp"></a>Exp

e を底とする引数のべき乗を計算します。

```cpp
inline float exp(float _X) restrict(amp);

inline double exp(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の底から e の指数を返します。

## <a name="expf"></a><a name="expf"></a>expf

e を底とする引数のべき乗を計算します。

```cpp
inline float expf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の底から e の指数を返します。

## <a name="exp2"></a><a name="exp2"></a>exp2

2 を底とする引数のべき乗を計算します。

```cpp
inline float exp2(float _X) restrict(amp);

inline double exp2(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

底 2 を引数で累乗した値を返します。

## <a name="exp2f"></a><a name="exp2f"></a>exp2f

2 を底とする引数のべき乗を計算します。

```cpp
inline float exp2f(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

底 2 を引数で累乗した値を返します。

## <a name="fabs"></a><a name="fabs"></a>工場

引数の絶対値を返します。

```cpp
inline float fabs(float _X) restrict(amp);

inline double fabs(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の絶対値を返します。

## <a name="fabsf"></a><a name="fabsf"></a>ファブスフ

引数の絶対値を返します。

```cpp
inline float fabsf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の絶対値を返します。

## <a name="fdim"></a><a name="fdim"></a>フディム

引数間の正の値の差を計算します。

```cpp
inline float fdim(
   float _X,
   float _Y
) restrict(amp);
inline double fdim(
   double _X,
   double _Y
) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値 *_Y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xが_Yより大きい場合は、_Xと_Yの差。それ以外の場合は+0。

## <a name="fdimf"></a><a name="fdimf"></a>fdimf

引数間の正の値の差を計算します。

```cpp
inline float fdimf(
   float _X,
   float _Y
) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値 *_Y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xが_Yより大きい場合は、_Xと_Yの差。それ以外の場合は+0。

## <a name="floor"></a><a name="floor"></a>床

引数の切り捨てを計算します。

```cpp
inline float floor(float _X) restrict(amp);

inline double floor(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の階を返します。

## <a name="floorf"></a><a name="floorf"></a>フロアフ

引数の切り捨てを計算します。

```cpp
inline float floorf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の階を返します。

## <a name="a-namefma-fma"></a><a name="fma">Fma

1 番目と 2 番目に指定された引数の積を計算し、その結果に 3 番目に指定された引数を加えます。全体の計算は単一の操作として実行されます。

```cpp
inline float fma(
   float _X,
   float _Y,
   float _Z
) restrict(amp);

inline double fma(
   double _X,
   double _Y,
   double _Z
) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
最初の浮動小数点引数。
*_y*<br/>
2 番目の浮動小数点引数。
*_Z*<br/>
3 番目の浮動小数点引数。

### <a name="return-value"></a>戻り値

式 (_X _Y) \* + _Zの結果。 全体の計算は単一の操作として実行されます。つまり、サブ式は無限の精度で計算され、最終結果だけが丸められます。

## <a name="fmaf"></a><a name="fmaf"></a>fmaf

1 番目と 2 番目に指定された引数の積を計算し、その結果に 3 番目に指定された引数を加えます。全体の計算は単一の操作として実行されます。

```cpp
inline float fmaf(
   float _X,
   float _Y,
   float _Z
) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
最初の浮動小数点引数。
*_y*<br/>
2 番目の浮動小数点引数。
*_Z*<br/>
3 番目の浮動小数点引数。

### <a name="return-value"></a>戻り値

式 (_X _Y) \* + _Zの結果。 全体の計算は単一の操作として実行されます。つまり、サブ式は無限の精度で計算され、最終結果だけが丸められます。

## <a name="fmax"></a><a name="fmax"></a>fmax

引数の最大数値を判断します。

```cpp
inline float fmax(
    float _X,
    float _Y) restrict(amp);

inline double fmax(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の最大数値を返します。

## <a name="fmaxf"></a><a name="fmaxf"></a>fマックスフ

引数の最大数値を判断します。

```cpp
inline float fmaxf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の最大数値を返します。

## <a name="fmin"></a><a name="fmin"></a>fmin

引数の最小数値を判断します。

```cpp
inline float fmin(
    float _X,
    float _Y) restrict(amp);

inline double fmin(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の最小数値を返します。

## <a name="fminf"></a><a name="fminf"></a>fminf

引数の最小数値を判断します。

```cpp
inline float fminf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の最小数値を返します。

## <a name="fmod-function-c-amp"></a><a name="fmod"></a>fmod 関数 (C++ AMP)

2 番目の指定された引数で除算した 1 番目の指定された引数の剰余を計算します。

```cpp
inline float fmod(
    float _X,
    float _Y) restrict(amp);

inline double fmod(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
最初の浮動小数点引数。

*_y*<br/>
2 番目の浮動小数点引数。

### <a name="return-value"></a>戻り値

除算の`_X`残りの`_Y`部分。つまり`_X` - `_Y`*、n*の値は*n*の大きさが`_X` - `_Y`の大きさより小さい*整数です。* `_Y`

## <a name="fmodf"></a><a name="fmodf"></a>フモドフ

2 番目の指定された引数で除算した 1 番目の指定された引数の剰余を計算します。

```cpp
inline float fmodf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
最初の浮動小数点引数。

*_y*<br/>
2 番目の浮動小数点引数。

### <a name="return-value"></a>戻り値

除算の`_X`残りの`_Y`部分。つまり`_X` - `_Y`*、n*の値は*n*の大きさが`_X` - `_Y`の大きさより小さい*整数です。* `_Y`

## <a name="fpclassify"></a><a name="fpclassify"></a>fp分類

引数の値を NaN、無限、正規、非正規、ゼロとして分類します。

```cpp
inline int fpclassify(float _X) restrict(amp);

inline int fpclassify(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の値に適した数値分類マクロの値を返します。

## <a name="frexp"></a><a name="frexp"></a>フレエクス

_X の仮数と指数を取得します。

```cpp
inline float frexp(
    float _X,
    _Out_ int* _Exp) restrict(amp);

inline double frexp(
    double _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_Exp*<br/>
浮動小数点値の_Xの整数指数を返します。

### <a name="return-value"></a>戻り値

カマシサ_Xを返します。

## <a name="frexpf"></a><a name="frexpf"></a>フインシュフ

_X の仮数と指数を取得します。

```cpp
inline float frexpf(
    float _X,
    _Out_ int* _Exp) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_Exp*<br/>
浮動小数点値の_Xの整数指数を返します。

### <a name="return-value"></a>戻り値

カマシサ_Xを返します。

## <a name="hypot"></a><a name="hypot"></a>仮説

_Xと_Yの平方和の平方根を計算します。

```cpp
inline float hypot(
    float _X,
    float _Y) restrict(amp);

inline double hypot(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xと_Yの平方和の平方根を返します。

## <a name="hypotf"></a><a name="hypotf"></a>ハイポtf

_Xと_Yの平方和の平方根を計算します。

```cpp
inline float hypotf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xと_Yの平方和の平方根を返します。

## <a name="ilogb"></a><a name="ilogb"></a>イログブ

_Xの指数を符号付き int 値として抽出する

```cpp
inline int ilogb(float _X) restrict(amp);

inline int ilogb(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの指数を符号付き整数の値として返します。

## <a name="ilogbf"></a><a name="ilogbf"></a>イログbf

_Xの指数を符号付き int 値として抽出する

```cpp
inline int ilogbf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの指数を符号付き整数の値として返します。

## <a name="isfinite"></a><a name="isfinite"></a>イスフィント

引数に有限値が存在するかどうかを判断します。

```cpp
inline int isfinite(float _X) restrict(amp);

inline int isfinite(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数に有限値がある場合にのみ、0 以外の値を返します。

## <a name="isinf"></a><a name="isinf"></a>イシンフ

引数が無限値であるかどうかを判断します。

```cpp
inline int isinf(float _X) restrict(amp);

inline int isinf(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数に無限の値がある場合に限り、0 以外の値を返します。

## <a name="isnan"></a><a name="isnan"></a>Isnan

引数が NaN であるかどうかを判断します。

```cpp
inline int isnan(float _X) restrict(amp);

inline int isnan(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数に NaN 値がある場合にのみ、0 以外の値を返します。

## <a name="isnormal"></a><a name="isnormal"></a>正常

引数が正規かどうかを判断します。

```cpp
inline int isnormal(float _X) restrict(amp);

inline int isnormal(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数に正規の値がある場合にのみ、0 以外の値を返します。

## <a name="ldexp"></a><a name="ldexp"></a>ldexp

指定された仮数と指数から実数を計算します。

```cpp
inline float ldexp(
    float _X,
    int _Exp) restrict(amp);

inline double ldexp(
    double _X,
    double _Exp) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点の値、仮数

*_Exp*<br/>
整数値、指数

### <a name="return-value"></a>戻り値

2^_Exp_X\*返します

## <a name="ldexpf"></a><a name="ldexpf"></a>ldexpf

指定された仮数と指数から実数を計算します。

```cpp
inline float ldexpf(
    float _X,
    int _Exp) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点の値、仮数

*_Exp*<br/>
整数値、指数

### <a name="return-value"></a>戻り値

2^_Exp_X\*返します

## <a name="lgamma"></a><a name="lgamma"></a>lガンマ

引数のガンマの絶対値の自然対数を計算します。

```cpp
inline float lgamma(
    float _X,
    _Out_ int* _Sign) restrict(amp);

inline double lgamma(
    double _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_Sign*<br/>
符号を返します。

### <a name="return-value"></a>戻り値

引数のガンマの絶対値の自然対数を返します。

## <a name="lgammaf"></a><a name="lgammaf"></a>lガンマフ

引数のガンマの絶対値の自然対数を計算します。

```cpp
inline float lgammaf(
    float _X,
    _Out_ int* _Sign) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_Sign*<br/>
符号を返します。

### <a name="return-value"></a>戻り値

引数のガンマの絶対値の自然対数を返します。

## <a name="log"></a><a name="log"></a>ログ

e を底とする引数の対数を計算します。

```cpp
inline float log(float _X) restrict(amp);

inline double log(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の底を表す対数を返します。

## <a name="log10"></a><a name="log10"></a>ログ10

10 を底とする引数の対数を計算します。

```cpp
inline float log10(float _X) restrict(amp);

inline double log10(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の 10 を底数の対数で返します。

## <a name="log10f"></a><a name="log10f"></a>ログ10f

10 を底とする引数の対数を計算します。

```cpp
inline float log10f(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の 10 を底数の対数で返します。

## <a name="log1p"></a><a name="log1p"></a>ログ1p

1 の底と e の対数を引数に加算して計算します。

```cpp
inline float log1p(float _X) restrict(amp);

inline double log1p(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

1 の底の対数に引数を加えた値を返します。

## <a name="log1pf"></a><a name="log1pf"></a>ログ1pf

1 の底と e の対数を引数に加算して計算します。

```cpp
inline float log1pf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

1 の底の対数に引数を加えた値を返します。

## <a name="log2"></a><a name="log2"></a>ログ2

2 を底とする引数の対数を計算します。

```cpp
inline float log2(float _X) restrict(amp);

inline double log2(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の 10 を底数の対数で返します。

## <a name="log2f"></a><a name="log2f"></a>ログ2f

2 を底とする引数の対数を計算します。

```cpp
inline float log2f(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の 10 を底数の対数で返します。

## <a name="logb"></a><a name="logb"></a>ログブ

_Xの指数を浮動小数点形式の符号付き整数値として抽出します。

```cpp
inline float logb(float _X) restrict(amp);

inline double logb(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの符号付き指数を返します。

## <a name="logbf"></a><a name="logbf"></a>ログbf

_Xの指数を浮動小数点形式の符号付き整数値として抽出します。

```cpp
inline float logbf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの符号付き指数を返します。

## <a name="logf"></a><a name="logf"></a>ログフ

e を底とする引数の対数を計算します。

```cpp
inline float logf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の底を表す対数を返します。

## <a name="modf"></a><a name="modf"></a>モドフ

指定された引数を小数部と整数部に分割します。

```cpp
inline float modf(
    float _X,
    _Out_ float* _Iptr) restrict(amp);

inline double modf(
    double _X,
    _Out_ double* _Iptr) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_Iptr*<br/>
[アウト]浮動小数点値で表`_X`される整数部分。

### <a name="return-value"></a>戻り値

`_X` の符号付の小数部分。

## <a name="modff"></a><a name="modff"></a>モッズフ

指定された引数を小数部と整数部に分割します。

```cpp
inline float modff(
    float _X,
    _Out_ float* _Iptr) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_Iptr*<br/>
浮動小数点値としての、`_X` の整数部分。

### <a name="return-value"></a>戻り値

`_X` の符号付き小数部を返します。

## <a name="nan"></a><a name="nan"></a>Nan

静かな NaN を返します。

```cpp
inline double nan(int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

### <a name="return-value"></a>戻り値

コンテンツが表示されている場合は、静止した NaN を返_X

## <a name="nanf"></a><a name="nanf"></a>ナンフ

静かな NaN を返します。

```cpp
inline float nanf(int _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
整数値

### <a name="return-value"></a>戻り値

コンテンツが表示されている場合は、静止した NaN を返_X

## <a name="nearbyint"></a><a name="nearbyint"></a>近く

現在の丸め方向を使用して、引数を浮動小数点形式の整数値に丸めます。

```cpp
inline float nearbyint(float _X) restrict(amp);

inline double nearbyint(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

丸められた整数値を返します。

## <a name="nearbyintf"></a><a name="nearbyintf"></a>近く

現在の丸め方向を使用して、引数を浮動小数点形式の整数値に丸めます。

```cpp
inline float nearbyintf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

丸められた整数値を返します。

## <a name="nextafter"></a><a name="nextafter"></a>次の次

_Y 方向での _X の後、関数の型で次に表示できる値を確認します

```cpp
inline float nextafter(
    float _X,
    float _Y) restrict(amp);

inline double nextafter(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Y 方向での _X の後で、関数の型で次に表示できる値を返します

## <a name="nextafterf"></a><a name="nextafterf"></a>次のアフターフ

_Y 方向での _X の後、関数の型で次に表示できる値を確認します

```cpp
inline float nextafterf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Y 方向での _X の後で、関数の型で次に表示できる値を返します

## <a name="phi"></a><a name="phi"></a>ファイ

引数の累積分布関数を返します。

```cpp
inline float phi(float _X) restrict(amp);

inline double phi(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の累積分布関数を返します。

## <a name="phif"></a><a name="phif"></a>ファイフ

引数の累積分布関数を返します。

```cpp
inline float phif(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の累積分布関数を返します。

## <a name="pow"></a><a name="pow"></a>えい

_X の _Y 乗を計算します。

```cpp
inline float pow(
    float _X,
    float _Y) restrict(amp);

inline double pow(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値、基数

*_y*<br/>
浮動小数点値,指数

### <a name="return-value"></a>戻り値

## <a name="powf"></a><a name="powf"></a>ポウフ

_X の _Y 乗を計算します。

```cpp
inline float powf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値、基数

*_y*<br/>
浮動小数点値,指数

### <a name="return-value"></a>戻り値

## <a name="probit"></a><a name="probit"></a>プロビット

引数の逆累積分布関数を返します。

```cpp
inline float probit(float _X) restrict(amp);

inline double probit(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆累積分布関数を返します。

## <a name="probitf"></a><a name="probitf"></a>プロビトフ

引数の逆累積分布関数を返します。

```cpp
inline float probitf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の逆累積分布関数を返します。

## <a name="rcbrt"></a><a name="rcbrt"></a>rcbrt

引数のキューブ ルートの逆数を返します。

```cpp
inline float rcbrt(float _X) restrict(amp);

inline double rcbrt(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のキューブ ルートの逆数を返します。

## <a name="rcbrtf"></a><a name="rcbrtf"></a>rcbrtf

引数のキューブ ルートの逆数を返します。

```cpp
inline float rcbrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のキューブ ルートの逆数を返します。

## <a name="remainder"></a><a name="remainder"></a>残り

残りの部分を計算します: _X REM _Y

```cpp
inline float remainder(
    float _X,
    float _Y) restrict(amp);

inline double remainder(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

レム_Y_X返します。

## <a name="remainderf"></a><a name="remainderf"></a>残りのフ

残りの部分を計算します: _X REM _Y

```cpp
inline float remainderf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

レム_Y_X返します。

## <a name="remquo"></a><a name="remquo"></a>レムコ

2 番目の指定された引数で除算した 1 番目の指定された引数の剰余を計算します。 また、1 番目に指定された引数の有効桁数を 2 番目に指定された引数の有効桁で割った商を計算し、3 番目の引数で指定された位置を使用して商を返します。

```cpp
inline float remquo(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);

inline double remquo(
    double _X,
    double _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
最初の浮動小数点引数。

*_y*<br/>
2 番目の浮動小数点引数。

*_Quo*<br/>
[アウト]の小数部で`_X`割った小数ビットの商を返すために使用される整数の`_Y`アドレス。

### <a name="return-value"></a>戻り値

`_X` を `_Y` で割った剰余を返します。

## <a name="remquof"></a><a name="remquof"></a>レムホフ

2 番目の指定された引数で除算した 1 番目の指定された引数の剰余を計算します。 また、1 番目に指定された引数の有効桁数を 2 番目に指定された引数の有効桁で割った商を計算し、3 番目の引数で指定された位置を使用して商を返します。

```cpp
inline float remquof(
    float _X,
    float _Y,
    _Out_ int* _Quo) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
最初の浮動小数点引数。

*_y*<br/>
2 番目の浮動小数点引数。

*_Quo*<br/>
[アウト]の小数部で`_X`割った小数ビットの商を返すために使用される整数の`_Y`アドレス。

### <a name="return-value"></a>戻り値

`_X` を `_Y` で割った剰余を返します。

## <a name="round"></a><a name="round"></a>ラウンド

_X を最も近い整数値に丸めます。

```cpp
inline float round(float _X) restrict(amp);

inline double round(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの最も近い整数を返します。

## <a name="roundf"></a><a name="roundf"></a>ラウンドフ

_X を最も近い整数値に丸めます。

```cpp
inline float roundf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの最も近い整数を返します。

## <a name="rsqrt"></a><a name="rsqrt"></a>rsqrt

引数の平方根の逆数を返します。

```cpp
inline float rsqrt(float _X) restrict(amp);

inline double rsqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の平方根の逆数を返します。

## <a name="rsqrtf"></a><a name="rsqrtf"></a>を使用します。

引数の平方根の逆数を返します。

```cpp
inline float rsqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の平方根の逆数を返します。

## <a name="scalb"></a><a name="scalb"></a>スカルブ

_Xを電力_YにFLT_RADIX倍

```cpp
inline float scalb(
    float _X,
    float _Y) restrict(amp);

inline double scalb(
    double _X,
    double _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_X\*を返します (FLT_RADIX ^ _Y)

## <a name="scalbf"></a><a name="scalbf"></a>スカルBF

_Xを電力_YにFLT_RADIX倍

```cpp
inline float scalbf(
    float _X,
    float _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_X\*を返します (FLT_RADIX ^ _Y)

## <a name="scalbn"></a><a name="scalbn"></a>スカルブン

_Xを電力_YにFLT_RADIX倍

```cpp
inline float scalbn(
    float _X,
    int _Y) restrict(amp);

inline double scalbn(
    double _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
整数値

### <a name="return-value"></a>戻り値

_X\*を返します (FLT_RADIX ^ _Y)

## <a name="scalbnf"></a><a name="scalbnf"></a>スカルブナフ

_Xを電力_YにFLT_RADIX倍

```cpp
inline float scalbnf(
    float _X,
    int _Y) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_y*<br/>
整数値

### <a name="return-value"></a>戻り値

_X\*を返します (FLT_RADIX ^ _Y)

## <a name="signbit"></a><a name="signbit"></a>サインビット

_Xの符号が負であるかどうかを判断します。

```cpp
inline int signbit(float _X) restrict(amp);

inline int signbit(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの符号が負の場合にのみ、0 以外の値を返します。

## <a name="signbitf"></a><a name="signbitf"></a>サインビットフ

_Xの符号が負であるかどうかを判断します。

```cpp
inline int signbitf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xの符号が負の場合にのみ、0 以外の値を返します。

## <a name="sin"></a><a name="sin"></a>罪

引数の正弦値を計算します。

```cpp
inline float sin(float _X) restrict(amp);

inline double sin(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の正常な値を返します。

## <a name="sinf"></a><a name="sinf"></a>シンフ

引数の正弦値を計算します。

```cpp
inline float sinf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の正常な値を返します。

## <a name="sincos"></a><a name="sincos"></a>シンコス

_X の正弦と余弦の値を計算します

```cpp
inline void sincos(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);

inline void sincos(
    double _X,
    _Out_ double* _S,
    _Out_ double* _C) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_S*<br/>
_Xの右の値を返します。

*_C*<br/>
_Xの余弦値を返します。

## <a name="sincosf"></a><a name="sincosf"></a>シンコスフ

_X の正弦と余弦の値を計算します

```cpp
inline void sincosf(
    float _X,
    _Out_ float* _S,
    _Out_ float* _C) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

*_S*<br/>
_Xの右の値を返します。

*_C*<br/>
_Xの余弦値を返します。

## <a name="sinh"></a><a name="sinh"></a>Sinh

引数の双曲線正弦の値を計算します。

```cpp
inline float sinh(float _X) restrict(amp);

inline double sinh(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の双曲線正弦の値を返します。

## <a name="sinhf"></a><a name="sinhf"></a>シンフ

引数の双曲線正弦の値を計算します。

```cpp
inline float sinhf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の双曲線正弦の値を返します。

## <a name="sinpi"></a><a name="sinpi"></a>シンピ

pi \* _Xの右の値を計算します。

```cpp
inline float sinpi(float _X) restrict(amp);

inline double sinpi(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

pi \* _Xの正常な値を返します。

## <a name="sinpif"></a><a name="sinpif"></a>シンピフ

pi \* _Xの右の値を計算します。

```cpp
inline float sinpif(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

pi \* _Xの正常な値を返します。

## <a name="sqrt"></a><a name="sqrt"></a>Sqrt

引数のスコール ルートを計算します。

```cpp
inline float sqrt(float _X) restrict(amp);

inline double sqrt(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のスコール ルートを返します。

## <a name="sqrtf"></a><a name="sqrtf"></a>sqrtf

引数のスコール ルートを計算します。

```cpp
inline float sqrtf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数のスコール ルートを返します。

## <a name="tan"></a><a name="tan"></a>日焼け

引数の正接値を計算します。

```cpp
inline float tan(float _X) restrict(amp);

inline double tan(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の正接値を返します。

## <a name="tanf"></a><a name="tanf"></a>タンフ

引数の正接値を計算します。

```cpp
inline float tanf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の正接値を返します。

## <a name="tanh"></a><a name="tanh"></a>Tanh

引数の双曲線正接の値を計算します。

```cpp
inline float tanh(float _X) restrict(amp);

inline double tanh(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の双曲線正接値を返します。

## <a name="tanhf"></a><a name="tanhf"></a>タンフ

引数の双曲線正接の値を計算します。

```cpp
inline float tanhf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の双曲線正接値を返します。

## <a name="tanpi"></a><a name="tanpi"></a>タンピ

pi _Xの正接値\*を計算します。

```cpp
inline float tanpi(float _X) restrict(amp);

inline double tanpi(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

pi の接線値\*を返_X

## <a name="tanpif"></a><a name="tanpif"></a>タンピフ

pi _Xの正接値\*を計算します。

```cpp
inline float tanpif(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

pi の接線値\*を返_X

## <a name="tgamma"></a><a name="tgamma"></a>ガンマ

_Xのガンマ関数を計算します。

```cpp
inline float tgamma(float _X) restrict(amp);

inline double tgamma(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xのガンマ関数の結果を返します。

## <a name="tgammaf"></a><a name="tgammaf"></a>ガンマフ

_Xのガンマ関数を計算します。

```cpp
inline float tgammaf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

_Xのガンマ関数の結果を返します。

## <a name="trunc"></a><a name="trunc"></a>トランク

引数を整数コンポーネントに切り捨てます。

```cpp
inline float trunc(float _X) restrict(amp);

inline double trunc(double _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の整数要素を返します。

## <a name="truncf"></a><a name="truncf"></a>を切り取る

引数を整数コンポーネントに切り捨てます。

```cpp
inline float truncf(float _X) restrict(amp);
```

### <a name="parameters"></a>パラメーター

*_x*<br/>
浮動小数点値

### <a name="return-value"></a>戻り値

引数の整数要素を返します。

## <a name="see-also"></a>関連項目

[同時実行: :precise_math 名前空間](concurrency-precise-math-namespace.md)
