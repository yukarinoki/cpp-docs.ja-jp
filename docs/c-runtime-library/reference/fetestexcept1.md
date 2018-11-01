---
title: fetestexcept
ms.date: 04/05/2018
apiname:
- fetestexcept
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
- fetestexcept
- fenv/fetestexcept
helpviewer_keywords:
- fetestexept function
ms.assetid: ca4dc43f-5573-440d-bc19-ead7571b13dc
ms.openlocfilehash: ae170e4c5826e2053b330d81773b75f176303332
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50667442"
---
# <a name="fetestexcept"></a>fetestexcept

指定した浮動小数点例外状態フラグのうち、現在設定されているフラグを確認します。

## <a name="syntax"></a>構文

```C
int fetestexcept(
   int excepts
);

```

### <a name="parameters"></a>パラメーター

*除く*<br/>
テストする浮動小数点状態フラグのビット演算 OR。

## <a name="return-value"></a>戻り値

成功時には、現在設定されている例外状態フラグに対応する浮動小数点例外処理マクロのビット演算 OR を含むビットマスクを返します。 例外が設定されていない場合は、0 を返します。

## <a name="remarks"></a>Remarks

fetestexcept 関数は、浮動小数点演算で発生した例外を確認するために使用します。 使用して、*除く*パラメーターをテストする例外状態フラグを指定します。 **Fetestexcept**関数で定義されているこれらの例外処理マクロを使用して\<fenv.h > で*除く*と戻り値。

|例外処理マクロ|説明|
|---------------------|-----------------|
|FE_DIVBYZERO|前の浮動小数点演算で特異点エラーまたは極エラーが発生しました。無限大の値が作成されました。|
|FE_INEXACT|前の浮動小数点演算の格納結果は強制的に丸められました。|
|FE_INVALID|前の浮動小数点演算でドメイン エラーが発生しました。|
|FE_OVERFLOW|範囲エラーが発生しました。前の浮動小数点演算結果は大きすぎて表現できませんでした。|
|FE_UNDERFLOW|前の浮動小数点演算結果は小さすぎて最大有効桁数で表現できませんでした。|
|FE_ALLEXCEPT|すべてのサポートされる浮動小数点例外のビット演算 OR。|

指定した*除く*引数には 0、1 つまたは 2 つまたは複数のマクロのサポートされる浮動小数点例外マクロ、またはビットごとの可能性があります。 その他の効果*除く*引数の値が定義されていません。

この関数を使用するには、呼び出しの前に `#pragma fenv_access(on)` ディレクティブを使用してアクセスを妨げる可能性のある浮動小数点の最適化をオフにする必要があります。 詳細については、「 [fenv_access](../../preprocessor/fenv-access.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|C ヘッダー|C++ ヘッダー|
|--------------|--------------|------------------|
|**fetestexcept**|\<fenv.h>|\<cfenv>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[feclearexcept](feclearexcept1.md)<br/>
[feraiseexcept](feraiseexcept.md)<br/>
