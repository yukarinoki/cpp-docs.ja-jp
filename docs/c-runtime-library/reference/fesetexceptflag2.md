---
title: fesetexceptflag
ms.date: 04/05/2018
apiname:
- fesetexceptflag
apilocation:
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fesetexceptflag
- fenv/fesetexceptflag
helpviewer_keywords:
- fesetexceptflag function
ms.assetid: 2f7dad77-9e54-4097-a3e3-35176ace4de5
ms.openlocfilehash: 9ac79e790f0b1e7a89413a0d4974f6053c95616e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333996"
---
# <a name="fesetexceptflag"></a>fesetexceptflag

現在の浮動小数点環境の指定した浮動小数点状態フラグを設定します。

## <a name="syntax"></a>構文

```C
int fesetexceptflag(
     const fexcept_t *pstatus,
     int excepts
);
```

### <a name="parameters"></a>パラメーター

*pstatus*<br/>
ポインター、 **fexcept_t**例外状態フラグを設定する値を含むオブジェクト。 オブジェクトは、以前の [fegetexceptflag](fegetexceptflag2.md) の呼び出しで設定される可能性があります。

*excepts*<br/>
設定する浮動小数点例外状態フラグ。

## <a name="return-value"></a>戻り値

すべての指定した例外状態フラグが正常に設定された場合は、0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>Remarks

**Fesetexceptflag**関数で指定された浮動小数点例外状態フラグの状態を設定する*除く*内の対応する値を**fexcept_t**によって指されるオブジェクト*pstatus*します。  この結果で例外は発生しません。 *Pstatus*を有効なポインターがポイントする必要があります**fexcept_t**オブジェクト、またはその後の動作が定義されていません。 **Fesetexceptflag**関数でこれらの例外マクロの値をサポートしている*除く*で定義された\<fenv.h >:

|例外処理マクロ|説明|
|---------------------|-----------------|
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|

*除く*引数が、0 にすることがありますまたはマクロの 2 つ以上のサポートされる浮動小数点例外マクロ、またはビットごとの 1 つ。 他の引数値の結果は未定義です。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fesetexceptflag**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fegetexceptflag](fegetexceptflag2.md)<br/>
