---
title: 浮動小数点プリミティブ
ms.date: 4/2/2020
api_name:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
- _o__d_int
- _o__dclass
- _o__dlog
- _o__dnorm
- _o__dpcomp
- _o__dpoly
- _o__dscale
- _o__dsign
- _o__dsin
- _o__dtest
- _o__dunscale
- _o__fd_int
- _o__fdclass
- _o__fdexp
- _o__fdlog
- _o__fdpcomp
- _o__fdpoly
- _o__fdscale
- _o__fdsign
- _o__fdsin
- _o__ld_int
- _o__ldclass
- _o__ldexp
- _o__ldlog
- _o__ldpcomp
- _o__ldpoly
- _o__ldscale
- _o__ldsign
- _o__ldsin
- _o__ldtest
- _o__ldunscale
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: e28c873206d8f050dbde2afc9ebfe3540b6642ff
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218685"
---
# <a name="floating-point-primitives"></a>浮動小数点プリミティブ

標準 C ランタイムライブラリ (CRT) の浮動小数点関数を実装するために使用される、Microsoft 固有のプリミティブ関数。 完全を期すためにここに記載されていますが、使用することはお勧めしません。 これらの関数には、有効桁数、例外処理、および IEEE-754 の動作への準拠に関する問題があることがわかっているため、未使用として記載されています。 旧バージョンとの互換性のためにのみライブラリに存在します。 正しい動作、移植性、標準への準拠については、これらの関数に対して標準の浮動小数点関数を使用することをお勧めします。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass、_ldclass、_fdclass

### <a name="syntax"></a>構文

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点関数の引数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、CRT マクロの C バージョンを実装して、浮動小数点型を[分類](fpclassify.md)します。 引数*x*の分類は、次のいずれかの定数として返されます。

|値|説明|
|-----------|-----------------|
| **FP_NAN** | クワイエット型、シグナル型、または不確定の NaN |
| **FP_INFINITE** | 正または負の無限大 |
| **FP_NORMAL** | 正規化された正または負の 0 以外の値 |
| **FP_SUBNORMAL** | 正または負の subnormal (非正規化) 値 |
| **FP_ZERO** | 正または負の 0 値 |

詳細については、Microsoft 固有の[_fpclass、_fpclassf](fpclass-fpclassf.md)関数を使用できます。 移植性を確保するには、 [fpclassify](fpclassify.md)マクロまたは関数を使用します。

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign、_ldsign、_fdsign

### <a name="syntax"></a>構文

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点関数の引数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、CRT で[signbit](signbit.md)マクロまたは関数を実装します。 符号ビットが引数*x*の有効桁 (仮数) に設定されている場合、0以外の値を返します。符号ビットが設定されていない場合は0を返します。

## <a name="_dpcomp-_ldpcomp-_fdpcomp"></a>_dpcomp、_ldpcomp、_fdpcomp

### <a name="syntax"></a>構文

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>パラメーター

*x*、 *y*<br/>
浮動小数点関数の引数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、 *x*と*y*の2つの引数を受け取り、それらの順序の関係を示す値を返します。これらの定数のビットごとの or として表現されます。

| 値 | 説明 |
|------------|-----------------|
| **_FP_LT** | *x*は*y*より小さいと見なすことができます |
| **_FP_EQ** | *x*は*y*と同じであると見なすことができます。 |
| **_FP_GT** | *x*は*y*より大きいと見なすことができます |

これらのプリミティブは、CRT で[isgreater、isgreaterequal、isgreater、islessequal、isgreater](floating-point-ordering.md)のマクロと関数を実装します。

## <a name="_dtest-_ldtest-_fdtest"></a>_dtest、_ldtest、_fdtest

### <a name="syntax"></a>構文

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>パラメーター

*ピクセル*<br/>
浮動小数点引数へのポインター。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、CRT 関数の C++ バージョンを実装して、浮動小数点型を[分類](fpclassify.md)します。 引数*x*が評価され、次の定数の1つとして、math. h で定義された分類が返されます。

|値|説明|
|-----------|-----------------|
| **FP_NAN** | クワイエット型、シグナル型、または不確定の NaN |
| **FP_INFINITE** | 正または負の無限大 |
| **FP_NORMAL** | 正規化された正または負の 0 以外の値 |
| **FP_SUBNORMAL** | 正または負の subnormal (非正規化) 値 |
| **FP_ZERO** | 正または負の 0 値 |

詳細については、Microsoft 固有の[_fpclass、_fpclassf](fpclass-fpclassf.md)関数を使用できます。 移植性を確保するには、 [fpclassify](fpclassify.md)関数を使用します。

## <a name="_d_int-_ld_int-_fd_int"></a>_d_int、_ld_int、_fd_int

### <a name="syntax"></a>構文

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>パラメーター

*ピクセル*<br/>
浮動小数点引数へのポインター。

*exp*<br/>
整数型の指数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、浮動小数点値*px*と指数値*exp*へのポインターを取得し、可能であれば、浮動小数点値の小数部を指定された指数より下に削除します。 返される値は、入力値が NaN または無限大の場合は、その入力値を*px*で**分類**した結果であり、それ以外の場合は*px*の出力値で返されます。

## <a name="_dscale-_ldscale-_fdscale"></a>_dscale、_ldscale、_fdscale

### <a name="syntax"></a>構文

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>パラメーター

*ピクセル*<br/>
浮動小数点引数へのポインター。

*exp*<br/>
整数型の指数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、浮動小数点値*px*と指数値*exp*へのポインターを取得し、可能であれば、値を 2<sup>*exp*</sup>で*px*でスケーリングします。 返される値は、入力値が NaN または無限大の場合は、その入力値を*px*で**分類**した結果であり、それ以外の場合は*px*の出力値で返されます。 移植性を確保するには、 [ldexp、ldexp、および ldexp](ldexp.md)関数を優先します。

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale、_ldunscale、_fdunscale

### <a name="syntax"></a>構文

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>パラメーター

*pexp*<br/>
整数型の指数へのポインター。

*ピクセル*<br/>
浮動小数点引数へのポインター。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、可能であれば、 *px*によって示される浮動小数点値を、有効桁 (仮数) と指数に分割します。 有効桁は、絶対値が0.5 以上かつ1.0 未満になるようにスケーリングされます。 指数は値*n*です。元の浮動小数点値は、スケールされた有効桁 times 2<sup>*n*</sup>と等しくなります。 この整数指数*n*は、 *pexp*が指す位置に格納されます。 返される値は、入力値が NaN または無限大の場合は、その入力値を*px*で**分類**した結果であり、それ以外の場合は出力値で返されます。 移植性を確保するには、 [frexp、frexpf、frexpf](frexp.md)関数を優先します。

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp、_ldexp、_fdexp

### <a name="syntax"></a>構文

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>パラメーター

*y*<br/>
浮動小数点関数の引数。

*ピクセル*<br/>
浮動小数点引数へのポインター。

*exp*<br/>
整数型の指数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、 *px*が*y* * 2<sup>*exp*</sup>に等しい位置に浮動小数点値を構築します。 返される値は、値が NaN または無限の場合は*y*の入力値を、それ以外の場合は出力値を*px*で**分類**した結果です。 移植性を確保するには、 [ldexp、ldexp、および ldexp](ldexp.md)関数を優先します。

## <a name="_dnorm-_fdnorm"></a>_dnorm、_fdnorm

### <a name="syntax"></a>構文

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>パラメーター

*ps*<br/>
の配列として表現された浮動小数点値のビットごとの表現へのポインター **`unsigned short`** 。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、アンダーフロー浮動小数点値の小数部を正規化し、一致するように*特性*(バイアスを持つ指数) を調整します。 この値は **`unsigned short`** `_double_val` 、punning で宣言された、 `_ldouble_val` 、または `_float_val` 型の配列に変換された浮動小数点型のビットごとの表現として渡されます。 戻り値は、入力された浮動小数点値が NaN または無限大の場合はその値を、それ以外の場合は出力値に対して、 **fpclassify**の結果になります。

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly、_ldpoly、_fdpoly

### <a name="syntax"></a>構文

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点関数の引数。

*テーブル*<br/>
多項式の定数係数のテーブルへのポインター。

*n*<br/>
評価する多項式の順序。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、係数が*テーブル*内の対応する定数値によって表される、順序*n*の多項式の*x*の評価を返します。 たとえば、*テーブル* \[ 0] = 3.0、*テーブル* \[ 1] = 4.0、*テーブル* \[ 2] = 5.0、および*n* = 2 の場合、これは多項式 5.0 x<sup>2</sup> + 4.0 x + 3.0 を表します。 この多項式が2.0 の*x*に対して評価された場合、結果は31.0 になります。 これらの関数は、内部的には使用されません。

## <a name="_dlog-_dlog-_dlog"></a>_dlog、_dlog、_dlog

### <a name="syntax"></a>構文

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点関数の引数。

*base_flag*<br/>
使用するベースを制御するフラグです。0の場合は*0、base* 10 の場合は0以外の値に設定されます。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、 *x*、ln (*x*)、またはログ<sub>*e*</sub>(*x*) の自然対数を返します ( *base_flag*が0の場合)。 *Base_flag*が0以外の場合は、ログの底が10の*x*、またはログ<sub>10</sub>(*x*) が返されます。 これらの関数は、内部的には使用されません。 移植性のために、関数[log、logf、logf、log10、log10f、および log10l](log-logf-log10-log10f.md)を優先します。

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin、_ldsin、_fdsin

### <a name="syntax"></a>構文

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>パラメーター

*x*<br/>
浮動小数点関数の引数。

*クアドラント*<br/>
`sin`、、 `cos` `-sin` 、およびの結果を生成するために使用する、0、1、2、または3のクアドラントのオフセット `-cos` 。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、*クアドラント*剰余4によって*x*オフセットのサインを返します。 実質的には、これらは、各*クアドラント*が0、1、2、または3の場合、 *x*の正弦、コサイン、-正弦、および-余弦を返します。 これらの関数は、内部的には使用されません。 移植性のために、 [sin、sinf、sinf](sin-sinf-sinl.md)、 [cos、cosf、cosf](cos-cosf-cosl.md)の各関数を優先します。

## <a name="requirements"></a>必要条件

ヘッダー: \<math.h>

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点サポート](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[frexp、frexpf、frexpl](frexp.md)<br/>
[ldexp、ldexp、ldexp](ldexp.md)<br/>
[log、logf、logl、log10、log10f、log10l](log-logf-log10-log10f.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
