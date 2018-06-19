---
title: feclearexcept1 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- feclearexcept
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
- feclearexcept
- fenv/feclearexcept
dev_langs:
- C++
helpviewer_keywords:
- feclearexcept function
ms.assetid: ef419da3-c248-4432-b53c-8e7a475d9533
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe943bcc0a1e1a027e432911bd2ad722fc7c7c1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399024"
---
# <a name="feclearexcept"></a>feclearexcept

引数で指定された浮動小数点例外フラグのクリアを試みます。

## <a name="syntax"></a>構文

```C
int feclearexcept(
   int excepts
);
```

### <a name="parameters"></a>パラメーター

*excepts*<br/>
クリアする例外状態フラグ。

## <a name="return-value"></a>戻り値

場合は 0 を返します*excepts*ゼロ、または指定されたすべての例外が正常にクリアされた場合。 それ以外の場合は、0 以外の値を返します。

## <a name="remarks"></a>コメント

**Feclearexcept**関数浮動をクリアするポイントで指定された例外状態フラグ*excepts*です。 この関数は、fenv.h に定義されている次の例外処理マクロをサポートしています。

|例外処理マクロ|説明|
|---------------------|-----------------|
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|

*Excepts*ゼロ、またはサポートされている例外マクロの 1 つ以上のビットごとの OR を引数として使用することがあります。 他の引数値の結果は未定義です。

## <a name="requirements"></a>要件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**feclearexcept**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[fetestexcept](fetestexcept1.md)<br/>
