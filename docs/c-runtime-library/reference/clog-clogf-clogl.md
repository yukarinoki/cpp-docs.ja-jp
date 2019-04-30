---
title: clog、clogf、clogl
ms.date: 11/04/2016
apiname:
- clog
- clogf
- clogl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- clog
- clogf
- clogl
- complex/clog
- complex/clogf
- complex/clogl
helpviewer_keywords:
- clog function
- clogf function
- clogl function
ms.assetid: 870b9b0b-6618-46f3-bfcf-da595cbd5e18
ms.openlocfilehash: fcbc9ba7984898d51f7a3d0beb5ef7c8b6d6892c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340639"
---
# <a name="clog-clogf-clogl"></a>clog、clogf、clogl

負の実軸に沿って分岐線法を使用して、複素数の自然対数を取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex clog(
   _Dcomplex z
);
_Fcomplex clog(
   _Fcomplex z
);  // C++ only
_Lcomplex clog(
   _Lcomplex z
);  // C++ only
_Fcomplex clogf(
   _Fcomplex z
);
_Lcomplex clogl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
対数の底。

## <a name="return-value"></a>戻り値

自然対数*z*します。 結果は、実軸の間隔で [-π、+ π] 虚軸。

戻り値には次のようなものがあります。

|z パラメーター|戻り値|
|-----------------|------------------|
|正|z の底 10 の対数|
|0|- ∞|
|負|NaN|
|NaN|NaN|
|+ ∞|+ ∞|

## <a name="remarks"></a>Remarks

C++では、オーバー ロードのオーバー ロードを呼び出すことができます**clog**を受け取って返す **_Fcomplex**と **_Lcomplex**値。 C プログラムで**clog**は、 **_Dcomplex**値。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**clog**、 **clogf**、 **clogl**|\<complex.h>|\<ccomplex>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[cexp、cexpf、cexpl](cexp-cexpf-cexpl.md)<br/>
[cpow、cpowf、cpowl](cpow-cpowf-cpowl.md)<br/>
[clog10、clog10f、clog10l](clog10-clog10f-clog10l.md)<br/>
