---
title: csinh、csinhf、csinhl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
apiname:
- csinh
- csinhf
- csinhl
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
- csinh
- csinhf
- csinhl
- complex/csinh
- complex/csinhf
- complex/csinhl
dev_langs:
- C++
helpviewer_keywords:
- csinh function
- csinhf function
- csinhl function
ms.assetid: cc616e55-d14d-4cd3-91f0-fbee03ce5edf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f620bdddb7bb86494b7981c84e12573a3ad89fa1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395969"
---
# <a name="csinh-csinhf-csinhl"></a>csinh、csinhf、csinhl

複素数のハイパーボリック サインを取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex csinh(
   _Dcomplex z
);
_Fcomplex csinh(
   _Fcomplex z
);  // C++ only
_Lcomplex csinh(
   _Lcomplex z
);  // C++ only
_Fcomplex csinhf(
   _Fcomplex z
);
_Lcomplex csinhl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
角度をラジアンで表す複素数。

## <a name="return-value"></a>戻り値

ハイパーボリック サイン*z*、(ラジアン単位)。

## <a name="remarks"></a>コメント

C++ では、オーバー ロードできるよう、ためのオーバー ロードを呼び出すことができます**csinh**を受け取り、返します **_Fcomplex**と **_Lcomplex**値。 C プログラムでは、 **csinh**常に受け取りを返す、 **_Dcomplex**値。

## <a name="requirements"></a>要件

|ルーチン|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**csinh**、 **csinhf**、 **csinhl**|\<complex.h>|\<ccomplex>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[関数リファレンス (アルファベット順)](crt-alphabetical-function-reference.md)<br/>
[catanh、catanhf、catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh、ctanhf、ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan、catanf、catanl](catan-catanf-catanl.md)<br/>
[casinh、casinhf、casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh、ccoshf、ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh、cacoshf、cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos、cacosf、cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan、ctanf、ctanl](ctan-ctanf-ctanl.md)<br/>
[csin、csinf、csinl](csin-csinf-csinl.md)<br/>
[casin、casinf、casinl](casin-casinf-casinl.md)<br/>
[ccos、ccosf、ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt、csqrtf、csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
