---
title: fegetexceptflag |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- fegetexceptflag
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
- fegetexceptflag
- fenv/fegetexceptflag
dev_langs:
- C++
helpviewer_keywords:
- fegetexceptflag function
ms.assetid: 2d28f0ca-70c9-4cff-be8b-3d876eacde71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baccf3f32381568472bd4d0d5f37d434ca789fc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399541"
---
# <a name="fegetexceptflag"></a>fegetexceptflag

指定した浮動小数点例外フラグの現在の状態を格納します。

## <a name="syntax"></a>構文

```C
int fegetexceptflag(
   fexcept_t* pstatus,
   int excepts
);

```

### <a name="parameters"></a>パラメーター

*pstatus*<br/>
ポインター、 **fexcept_t**で指定された例外フラグの現在の値を格納するオブジェクト*excepts*です。

*excepts*<br/>
格納する浮動小数点例外フラグ*pstatus*です。

## <a name="return-value"></a>戻り値

成功した場合は 0 を返します。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>コメント

**Fegetexceptflag**関数で指定された浮動小数点例外状態フラグの現在の状態を格納する*excepts*で、 **fexcept_t**によって指されるオブジェクト*pstatus*です。  *pstatus*指す必要があります、有効な**fexcept_t**オブジェクト、またはそれ以降の動作は未定義です。 **Fegetexceptflag**関数で定義されているこれらの例外マクロをサポートしている\<fenv.h >:

|例外処理マクロ|説明|
|---------------------|-----------------|
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|

*Excepts*引数が、0 にすることがあります、サポートされている浮動小数点例外処理マクロ、またはビットごとのまたはマクロの 2 つ以上のいずれか。 他の引数値の結果は未定義です。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fegetexceptflag**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fesetexceptflag](fesetexceptflag2.md)<br/>
