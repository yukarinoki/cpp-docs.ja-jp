---
title: Concurrency::fast_math 名前空間の関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp_math/Concurrency::fast_math::acos
- amp_math/Concurrency::fast_math::asin
- amp_math/Concurrency::fast_math::asinf
- amp_math/Concurrency::fast_math::atan2
- amp_math/Concurrency::fast_math::atan2f
- amp_math/Concurrency::fast_math::ceil
- amp_math/Concurrency::fast_math::ceilf
- amp_math/Concurrency::fast_math::cosf
- amp_math/Concurrency::fast_math::cosh
- amp_math/Concurrency::fast_math::exp
- amp_math/Concurrency::fast_math::exp2
- amp_math/Concurrency::fast_math::expf
- amp_math/Concurrency::fast_math::fabs
- amp_math/Concurrency::fast_math::floor
- amp_math/Concurrency::fast_math::floorf
- amp_math/Concurrency::fast_math::fmaxf
- amp_math/Concurrency::fast_math::fmin
- amp_math/Concurrency::fast_math::fmod
- amp_math/Concurrency::fast_math::fmodf
- amp_math/Concurrency::fast_math::frexpf
- amp_math/Concurrency::fast_math::isfinite
- amp_math/Concurrency::fast_math::isnan
- amp_math/Concurrency::fast_math::ldexp
- amp_math/Concurrency::fast_math::log
- amp_math/Concurrency::fast_math::log10
- amp_math/Concurrency::fast_math::log2
- amp_math/Concurrency::fast_math::log2f
- amp_math/Concurrency::fast_math::modf
- amp_math/Concurrency::fast_math::modff
- amp_math/Concurrency::fast_math::powf
- amp_math/Concurrency::fast_math::round
- amp_math/Concurrency::fast_math::rsqrt
- amp_math/Concurrency::fast_math::rsqrtf
- amp_math/Concurrency::fast_math::signbitf
- amp_math/Concurrency::fast_math::sin
- amp_math/Concurrency::fast_math::sincosf
- amp_math/Concurrency::fast_math::sinf
- amp_math/Concurrency::fast_math::sinhf
- amp_math/Concurrency::fast_math::sqrt
- amp_math/Concurrency::fast_math::tan
- amp_math/Concurrency::fast_math::tanf
- amp_math/Concurrency::fast_math::tanhf
- amp_math/Concurrency::fast_math::trunc
dev_langs:
- C++
ms.assetid: f5763d62-795b-4de6-a7a5-c7115f158708
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9bd20e2e1d88564c7e688e1e0c9c2392f1f4f2ac
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695312"
---
# <a name="concurrencyfastmath-namespace-functions"></a>Concurrency::fast_math 名前空間の関数
||||  
|-|-|-|  
|[acos](#acos)|[acosf](#acosf)|[asin](#asin)|  
|[asinf](#asinf)|[atan](#atan)|[atan2](#atan2)|  
|[atan2f](#atan2f)|[atanf](#atanf)|[ceil](#ceil)|  
|[ceilf](#ceilf)|[cos](#cos)|[cosf](#cosf)|  
|[cosh](#cosh)|[coshf](#coshf)|[exp](#exp)|  
|[exp2](#exp2)|[exp2f](#exp2f)|[expf](#expf)|  
|[fabs](#fabs)|[fabsf](#fabsf)|[floor](#floor)|  
|[floorf](#floorf)|[fmax](#fmax)|[fmaxf](#fmaxf)|  
|[fmin](#fmin)|[fminf](#fminf)|[fmod](#fmod)|  
|[fmodf](#fmodf)|[frexp](#frexp)|[frexpf](#frexpf)|  
|[isfinite](#isfinite)|[isinf](#isinf)|[isnan](#isnan)|  
|[ldexp](#ldexp)|[ldexpf](#ldexpf)|[log](#log)|  
|[log10](#log10)|[log10f](#log10f)|[log2](#log2)|  
|[log2f](#log2f)|[logf](#logf)|[modf](#modf)|  
|[modff](#modff)|[pow](#pow)|[powf](#powf)|  
|[round](#round)|[roundf](#roundf)|[rsqrt](#rsqrt)|  
|[rsqrtf](#rsqrtf)|[signbit](#signbit)|[signbitf](#signbitf)|  
|[sin](#sin)|[sincos](#sincos)|[sincosf](#sincosf)|  
|[sinf](#sinf)|[sinh](#sinh)|[sinhf](#sinhf)|  
|[sqrt](#sqrt)|[sqrtf](#sqrtf)|[tan](#tan)|  
|[tanf](#tanf)|[tanh](#tanh)|[tanhf](#tanhf)|  
|[trunc](#trunc)|[truncf](#truncf)|  
  
##  <a name="acos"></a>  acos  
 引数の逆余弦を計算します。  
  
```  
inline float acos(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆余弦の値を返します  
  
##  <a name="acosf"></a>  acosf  
 引数の逆余弦を計算します。  
  
```  
inline float acosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆余弦の値を返します  
  
##  <a name="asin"></a>  asin  
 引数の逆正弦を計算します。  
  
```  
inline float asin(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正弦値を返します  
  
##  <a name="asinf"></a>  asinf  
 引数の逆正弦を計算します。  
  
```  
inline float asinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正弦値を返します  
  
##  <a name="atan"></a>  atan  
 引数の逆正接を計算します。  
  
```  
inline float atan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正接値を返します  
  
##  <a name="atan2"></a>  atan2  
 _Y/_X の逆正接を計算します。  
  
```  
inline float atan2(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Y`  
 浮動小数点値  
  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _Y/_X の逆正接値を返します  
  
##  <a name="atan2f"></a>  atan2f  
 _Y/_X の逆正接を計算します。  
  
```  
inline float atan2f(
    float _Y,  
    float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Y`  
 浮動小数点値  
  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _Y/_X の逆正接値を返します  
  
##  <a name="atanf"></a>  atanf  
 引数の逆正接を計算します。  
  
```  
inline float atanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の逆正接値を返します  
  
##  <a name="ceil"></a>  ceil  
 引数の切り上げを計算します。  
  
```  
inline float ceil(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り上げ値を返します  
  
##  <a name="ceilf"></a>  ceilf  
 引数の切り上げを計算します。  
  
```  
inline float ceilf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り上げ値を返します  
  
##  <a name="cosf"></a>  cosf  
 引数の余弦を計算します。  
  
```  
inline float cosf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の余弦の値を返します  
  
##  <a name="coshf"></a>  coshf  
 引数の双曲線余弦の値を計算します。  
  
```  
inline float coshf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線余弦の値を返します  
  
##  <a name="cos"></a>  cos  
 引数の余弦を計算します。  
  
```  
inline float cos(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の余弦の値を返します  
  
##  <a name="cosh"></a>  cosh  
 引数の双曲線余弦の値を計算します。  
  
```  
inline float cosh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線余弦の値を返します  
  
##  <a name="exp"></a>  exp  
 e を底とする引数のべき乗を計算します。  
  
```  
inline float exp(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 E を底とする引数のべき乗を返します。  
  
##  <a name="exp2"></a>  exp2  
 2 を底とする引数のべき乗を計算します。  
  
```  
inline float exp2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 2 を底とする引数のべき乗を返します。  
  
##  <a name="exp2f"></a>  exp2f  
 2 を底とする引数のべき乗を計算します。  
  
```  
inline float exp2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 2 を底とする引数のべき乗を返します。  
  
##  <a name="expf"></a>  expf  
 e を底とする引数のべき乗を計算します。  
  
```  
inline float expf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 E を底とする引数のべき乗を返します。  
  
##  <a name="fabs"></a>  fabs  
 引数の絶対値を返します。  
  
```  
inline float fabs(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 引数の絶対値を返します。  
  
##  <a name="fabsf"></a>  fabsf  
 引数の絶対値を返します。  
  
```  
inline float fabsf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の絶対値を返します。  
  
##  <a name="floor"></a>  floor  
 引数の切り捨てを計算します。  
  
```  
inline float floor(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り捨てを返します  
  
##  <a name="floorf"></a>  floorf  
 引数の切り捨てを計算します。  
  
```  
inline float floorf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の切り捨てを返します  
  
##  <a name="fmax"></a>  fmax  
 引数の最大数値を判断します。  
  
```  
inline float max(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
 `_Y`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 引数の最大数値を返します。  
  
##  <a name="fmaxf"></a>  fmaxf  
 引数の最大数値を判断します。  
  
```  
inline float fmaxf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の最大数値を返します。  
  
##  <a name="fmin"></a>  fmin  
 引数の最小数値を判断します。  
  
```  
inline float min(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 整数値  
  
 `_Y`  
 整数値  
  
### <a name="return-value"></a>戻り値  
 引数の最小数値を返します。  
  
##  <a name="fminf"></a>  fminf  
 引数の最小数値を判断します。  
  
```  
inline float fminf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の最小数値を返します。  
  
##  <a name="fmod"></a>  fmod  
 _X/_Y の浮動小数点の剰余を計算します。  
  
```  
inline float fmod(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X/_Y の浮動小数点の剰余を返します  
  
##  <a name="fmodf"></a>  fmodf  
 _X/_Y の浮動小数点の剰余を計算します。  
  
```  
inline float fmodf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Y`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X/_Y の浮動小数点の剰余を返します  
  
##  <a name="frexp"></a>  frexp  
 _X の仮数と指数を取得します。  
  
```  
inline float frexp(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Exp`  
 浮動小数点値での _X の整数の指数を返します  
  
### <a name="return-value"></a>戻り値  
 仮数 _X を返します  
  
##  <a name="frexpf"></a>  frexpf  
 _X の仮数と指数を取得します。  
  
```  
inline float frexpf(
    float _X,  
    _Out_ int* _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Exp`  
 浮動小数点値での _X の整数の指数を返します  
  
### <a name="return-value"></a>戻り値  
 仮数 _X を返します  
  
##  <a name="isfinite"></a>  isfinite  
 引数に有限値が存在するかどうかを判断します。  
  
```  
inline int isfinite(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数に有限値がある場合にのみ、0 以外の値を返します  
  
##  <a name="isinf"></a>  isinf  
 引数が無限値であるかどうかを判断します。  
  
```  
inline int isinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数が無限の値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="isnan"></a>  isnan  
 引数が NaN であるかどうかを判断します。  
  
```  
inline int isnan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数が NaN 値を持つ場合にのみ、0 以外の値を返します  
  
##  <a name="ldexp"></a>  ldexp  
 仮数と指数から実数を計算します。  
  
```  
inline float ldexp(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値、mentissa  
  
 `_Exp`  
 整数の指数  
  
### <a name="return-value"></a>戻り値  
 _X * 2^_Exp を返します  
  
##  <a name="ldexpf"></a>  ldexpf  
 仮数と指数から実数を計算します。  
  
```  
inline float ldexpf(
    float _X,  
    int _Exp) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値、mentissa  
  
 `_Exp`  
 整数の指数  
  
### <a name="return-value"></a>戻り値  
 _X * 2^_Exp を返します  
  
##  <a name="log"></a>  log  
 e を底とする引数の対数を計算します。  
  
```  
inline float log(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の e を底と対数を返します  
  
##  <a name="log10"></a>  log10  
 10 を底とする引数の対数を計算します。  
  
```  
inline float log10(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底 10 の対数を返します  
  
##  <a name="log10f"></a>  log10f  
 10 を底とする引数の対数を計算します。  
  
```  
inline float log10f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底 10 の対数を返します  
  
##  <a name="log2"></a>  log2  
 2 を底とする引数の対数を計算します。  
  
```  
inline float log2(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底 2 の対数を返します  
  
##  <a name="log2f"></a>  log2f  
 2 を底とする引数の対数を計算します。  
  
```  
inline float log2f(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の底 10 の対数を返します  
  
##  <a name="logf"></a>  logf  
 e を底とする引数の対数を計算します。  
  
```  
inline float logf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の e を底と対数を返します  
  
##  <a name="modf"></a>  modf  
 _X を小数部と整数部に分割します。  
  
```  
inline float modf(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Ip`  
  
### <a name="return-value"></a>戻り値  
 _X の符号付き小数部分を返します  
  
##  <a name="modff"></a>  modff  
 _X を小数部と整数部に分割します。  
  
```  
inline float modff(
    float _X,  
    float* _Ip) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_Ip`  
  
### <a name="return-value"></a>戻り値  
 _X の符号付き小数部分を返します  
  
##  <a name="pow"></a>  pow  
 _X の _Y 乗を計算します。  
  
```  
inline float pow(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 基本浮動小数点値  
  
 `_Y`  
 浮動小数点値、指数  
  
### <a name="return-value"></a>戻り値  
 _X の _Y 乗の値を返します  
  
##  <a name="powf"></a>  powf  
 _X の _Y 乗を計算します。  
  
```  
inline float powf(
    float _X,  
    float _Y) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 基本浮動小数点値  
  
 `_Y`  
 浮動小数点値、指数  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="round"></a>  round  
 _X を最も近い整数値に丸めます。  
  
```  
inline float round(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の最も近い整数値を返します  
  
##  <a name="roundf"></a>  roundf  
 _X を最も近い整数値に丸めます。  
  
```  
inline float roundf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の最も近い整数値を返します  
  
##  <a name="rsqrt"></a>  rsqrt  
 引数の平方根の逆数を返します。  
  
```  
inline float rsqrt(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の平方根の逆数を返します。  
  
##  <a name="rsqrtf"></a>  rsqrtf  
 引数の平方根の逆数を返します。  
  
```  
inline float rsqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の平方根の逆数を返します。  
  
##  <a name="signbit"></a>  signbit  
 _X の符号が負の値であるかどうかを決定します。  
  
```  
inline int signbit(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の符号が負の場合にのみ、0 以外の値を返します  
  
##  <a name="signbitf"></a>  signbitf  
 _X の符号が負の値であるかどうかを決定します。  
  
```  
inline int signbitf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 _X の符号が負の場合にのみ、0 以外の値を返します  
  
##  <a name="sin"></a>  sin  
 引数の正弦値を計算します。  
  
```  
inline float sin(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正弦値を返します  
  
##  <a name="sinf"></a>  sinf  
 引数の正弦値を計算します。  
  
```  
inline float sinf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正弦値を返します  
  
##  <a name="sincos"></a>  sincos  
 _X の正弦と余弦の値を計算します  
  
```  
inline void sincos(
    float _X,  
    float* _S,  
    float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_S`  
 _X の正弦値を返します  
  
 `_C`  
 _X の余弦の値を返します  
  
##  <a name="sincosf"></a>  sincosf  
 _X の正弦と余弦の値を計算します  
  
```  
inline void sincosf(
    float _X,  
    float* _S,  
    float* _C) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
 `_S`  
 _X の正弦値を返します  
  
 `_C`  
 _X の余弦の値を返します  
  
##  <a name="sinh"></a>  sinh  
 引数の双曲線正弦の値を計算します。  
  
```  
inline float sinh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正弦の値を返します  
  
##  <a name="sinhf"></a>  sinhf  
 引数の双曲線正弦の値を計算します。  
  
```  
inline float sinhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正弦の値を返します  
  
##  <a name="sqrt"></a>  sqrt  
 引数の squre ルートを計算します。  
  
```  
inline float sqrt(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の squre ルートを返します  
  
##  <a name="sqrtf"></a>  sqrtf  
 引数の squre ルートを計算します。  
  
```  
inline float sqrtf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の squre ルートを返します  
  
##  <a name="tan"></a>  tan  
 引数の正接値を計算します。  
  
```  
inline float tan(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正接値を返します  
  
##  <a name="tanf"></a>  tanf  
 引数の正接値を計算します。  
  
```  
inline float tanf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の正接値を返します  
  
##  <a name="tanh"></a>  tanh  
 引数の双曲線正接の値を計算します。  
  
```  
inline float tanh(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正接の値を返します  
  
##  <a name="tanhf"></a>  tanhf  
 引数の双曲線正接の値を計算します。  
  
```  
inline float tanhf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の双曲線正接の値を返します  
  
##  <a name="trunc"></a>  trunc  
 引数を整数コンポーネントに切り捨てます。  
  
```  
inline float trunc(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の整数部分を返します  
  
##  <a name="truncf"></a>  truncf  
 引数を整数コンポーネントに切り捨てます。  
  
```  
inline float truncf(float _X) restrict(amp);
```  
  
### <a name="parameters"></a>パラメーター  
 `_X`  
 浮動小数点値  
  
### <a name="return-value"></a>戻り値  
 引数の整数部分を返します  

## <a name="requirements"></a>要件
**ヘッダー:** amp_math.h **Namespace:** concurrency::fast_math
  
## <a name="see-also"></a>関連項目  
 [Concurrency::fast_math 名前空間](concurrency-fast-math-namespace.md)
