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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d861fbf2b71d557354a60f65b8a76dc24ca1dd13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346708"
---
# <a name="floating-point-primitives"></a>浮動小数点プリミティブ

標準 C ランタイム ライブラリ (CRT) 浮動小数点関数の実装に使用される Microsoft 固有のプリミティブ関数。 これらは、完全な情報を記載していますが、使用することは推奨されません。 これらの関数の中には、精度、例外処理、IEEE-754 動作への準拠に問題が発生することがわかっているため、未使用として示されるものもあります。 これらは、下位互換性を保つためにのみライブラリに存在します。 正しい動作、移植性、標準への準拠を行うために、これらの関数よりも標準の浮動小数点関数を優先します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass、_ldclass、_fdclass

### <a name="syntax"></a>構文

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
浮動小数点関数の引数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、浮動小数点型の CRT マクロ[fpclassify](fpclassify.md)の C バージョンを実装します。 引数*x*の分類は、math.h で定義された次のいずれかの定数として返されます。

|[値]|説明|
|-----------|-----------------|
| **FP_NAN** | クワイエット型、シグナル型、または不確定の NaN |
| **FP_INFINITE** | 正または負の無限大 |
| **FP_NORMAL** | 正規化された正または負の 0 以外の値 |
| **FP_SUBNORMAL** | 正または負の非正規 (非正規化) 値 |
| **FP_ZERO** | 正または負の 0 値 |

詳細については、マイクロソフト固有の[_fpclass、_fpclassf機能を](fpclass-fpclassf.md)使用できます。 移植性のために[fpclassify](fpclassify.md)マクロまたは関数を使用します。

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign、_ldsign、_fdsign

### <a name="syntax"></a>構文

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
浮動小数点関数の引数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、CRT に[符号](signbit.md)マクロまたは関数を実装します。 引数*x*の符号 (mantissa) に符号ビットが設定されている場合はゼロ以外の値を返し、符号ビットが設定されていない場合は 0 を返します。

## <a name="_dpcomp-_ldpcomp-_fdpcomp"></a>_dpcomp、_ldpcomp、_fdpcomp

### <a name="syntax"></a>構文

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>パラメーター

*x*, *y*<br/>
浮動小数点関数の引数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは *、x*と*y*の 2 つの引数を受け取り、math.h で定義されたビット単位またはこれらの定数の順序付けの関係を示す値を返します。

| [値] | 説明 |
|------------|-----------------|
| **_FP_LT** | *x*は*y*より小さいと見なすことができます |
| **_FP_EQ** | *x*は*y*と等しいと見なすことができます。 |
| **_FP_GT** | *x*は*y*より大きいと見なすことができます |

これらのプリミティブは、より[大きく、等しく、等しく、無等く、無等く、無](floating-point-ordering.md)意味、および CRT の非順序のマクロと関数を実装します。

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

これらの浮動小数点プリミティブは、浮動小数点型の CRT 関数[fpclassify](fpclassify.md)の C++ バージョンを実装します。 引数*x*が評価され、クラスが math.h で定義された次のいずれかの定数として返されます。

|[値]|説明|
|-----------|-----------------|
| **FP_NAN** | クワイエット型、シグナル型、または不確定の NaN |
| **FP_INFINITE** | 正または負の無限大 |
| **FP_NORMAL** | 正規化された正または負の 0 以外の値 |
| **FP_SUBNORMAL** | 正または負の非正規 (非正規化) 値 |
| **FP_ZERO** | 正または負の 0 値 |

詳細については、マイクロソフト固有の[_fpclass、_fpclassf機能を](fpclass-fpclassf.md)使用できます。 移植性のために[fp 分類](fpclassify.md)関数を使用します。

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

*Exp*<br/>
整数型としての指数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、浮動小数点値*px*へのポインターと指数値*exp*を受け取り、可能であれば、指定された指数より下の浮動小数点値の小数部分を削除します。 返される値は、入力値が NaN または無限大の場合は*入力*値に対する**fpclassify**の結果であり、それ以外の場合は px の出力値に対する*fpclassify*です。

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

*Exp*<br/>
整数型としての指数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、浮動小数点値*px*へのポインタと指数値*exp*を受け取り、可能であれば*px*で値を 2<sup>*exp*</sup>にスケーリングします。 返される値は、入力値が NaN または無限大の場合は*入力*値に対する**fpclassify**の結果であり、それ以外の場合は px の出力値に対する*fpclassify*です。 移植性を高めるには[、ldexp 関数、ldexpf 関数、および ldexpl](ldexp.md)関数を使用してください。

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale、_ldunscale、_fdunscale

### <a name="syntax"></a>構文

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>パラメーター

*ペxp*<br/>
整数型としての指数へのポインター。

*ピクセル*<br/>
浮動小数点引数へのポインター。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは *、px*で指さされた浮動小数点値を、可能であれば、仮数 (仮数) と指数に分解します。 この意味は、絶対値が 0.5 以上、1.0 未満になるようにスケーリングされます。 指数は*値 n*で、元の浮動小数点値は倍率の 2<sup>*n*</sup>の倍率に等しくなります。 この整数指数*n*は *、pexp*が指す位置に格納されます。 返される値は、入力値が NaN または無限大の場合は*px*の入力値に対する fpclassify の結果であり、それ以外の場合は出力値に対する**fpclassify**の結果です。 移植性のために[、frexp、frexpf、frexpl](frexp.md)関数を好みます。

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp、_ldexp、_fdexp

### <a name="syntax"></a>構文

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>パラメーター

*Y*<br/>
浮動小数点関数の引数。

*ピクセル*<br/>
浮動小数点引数へのポインター。

*Exp*<br/>
整数型としての指数。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは *、y* * 2<sup>*exp*</sup>に等しい*px*で指す位置に浮動小数点値を構築します。 返される値は *、y*の入力値が NaN または無限大の場合は fpclassify の結果であり、それ以外の場合は*px*の出力値に対する**fpclassify**です。 移植性を高めるには[、ldexp 関数、ldexpf 関数、および ldexpl](ldexp.md)関数を使用してください。

## <a name="_dnorm-_fdnorm"></a>_dnorm,_fdnorm

### <a name="syntax"></a>構文

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>パラメーター

*ps*<br/>
**符号なし** **short**の配列として表される浮動小数点値のビットごとの表現へのポインター。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、アンダーフローされた浮動小数点値の小数部を正規化し、*特性*、つまり偏った指数を調整して一致させます。 値は、math.h`_double_val`で宣言された`_ldouble_val`、、、または`_float_val`型のパンニング共用体を通して **、符号なし** **short**の配列に変換される浮動小数点型のビットごとの表現として渡されます。 戻り値は、入力浮動小数点値が NaN または無限大の場合は fpclassify の結果であり、それ以外の場合は出力値に対する**fpclassify**の結果です。

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly、_ldpoly、_fdpoly

### <a name="syntax"></a>構文

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
浮動小数点関数の引数。

*テーブル*<br/>
多項式の定数係数のテーブルへのポインタ。

*n*<br/>
評価する多項式の順序。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、*係数がテーブル*内の対応する定数値で表される、多項式*n*の*x*の評価を返します。 たとえば、*表*\[0] = 3.0、*表*\[1] = 4.0、*表*\[2] = 5.0、n *n* = 2 の場合、多項式 5.0x<sup>2</sup> + 4.0x + 3.0 を表します。 この多項式が*x* 2.0 の評価を受けていれば、結果は 31.0 になります。 これらの関数は内部的には使用されません。

## <a name="_dlog-_dlog-_dlog"></a>_dlog、_dlog、_dlog

### <a name="syntax"></a>構文

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
浮動小数点関数の引数。

*base_flag*<br/>
使用するベースを制御するフラグ、ベース*e*の場合は 0、底 10 の場合は 0 以外のフラグ。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは *、base_flag*が 0 の場合 *、x*、ln(*x*) または log<sub>*e*</sub>(*x*) の自然対数を返します。 *base_flag*が 0*以外の場合*、x のログ ベース 10 またはログ<sub>10</sub>*(x)* を返します。 これらの関数は内部的には使用されません。 移植性のために、[関数ログ、ログ、ログ、ログ、log10、log10f、およびlog10l](log-logf-log10-log10f.md)を好みます。

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin、_ldsin、_fdsin

### <a name="syntax"></a>構文

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>パラメーター

*X*<br/>
浮動小数点関数の引数。

*象限*<br/>
結果 、、、`sin`および の`cos``-sin``-cos`結果を生成するために使用する、領域オフセットは 0、1、2、または 3 です。

### <a name="remarks"></a>解説

これらの浮動小数点プリミティブは、*象限*モジュロ 4 によってオフセットされた*x*の sine を返します。 事実上、*象限*モジュロ*4が*0、1、2、または3である場合、xのサイン、コサイン、-サイン、-コサインを返します。 これらの関数は内部的には使用されません。 移植性のために[は、罪、シンフ、シンル、](sin-sinf-sinl.md)[コス、コスフ、コスル](cos-cosf-cosl.md)の関数を好みます。

## <a name="requirements"></a>必要条件

ヘッダー: \<math.h>

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[イシンフ](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos、cosf、cosl](cos-cosf-cosl.md)<br/>
[frexp、frexpf、frexpl](frexp.md)<br/>
[ldexp、ldexpf、および ldexpl](ldexp.md)<br/>
[log、logf、logl、log10、log10f、log10l](log-logf-log10-log10f.md)<br/>
[sin、sinf、sinl](sin-sinf-sinl.md)<br/>
