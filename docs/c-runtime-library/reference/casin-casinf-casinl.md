---
description: 詳細については、casin、casin、casinl に関するページを参照してください。
title: casin、casinf、casinl
ms.date: 11/04/2016
api_name:
- casin
- casinf
- casinl
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- casin
- casinf
- casinl
- complex/casin
- complex/casinf
- complex/casinl
helpviewer_keywords:
- casin function
- casinf function
- casinl function
ms.assetid: b75d1455-7b1e-43b0-bd46-c530be190be9
ms.openlocfilehash: 222e1b99bcc366b3d3d6656bd438d69f670f75eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326338"
---
# <a name="casin-casinf-casinl"></a>casin、casinf、casinl

実数軸に沿って区間 [-1, + 1] の外側に分岐がある場合に、複素数のアークサインを取得します。

## <a name="syntax"></a>構文

```C
_Dcomplex casin(
   _Dcomplex z
);
_Fcomplex casin(
   _Fcomplex z
);  // C++ only
_Lcomplex casin(
   _Lcomplex z
);  // C++ only
_Fcomplex casinf(
   _Fcomplex z
);
_Lcomplex casinl(
   _Lcomplex z
);
```

### <a name="parameters"></a>パラメーター

*z*<br/>
角度をラジアンで表す複素数。

## <a name="return-value"></a>戻り値

*Z* のアークサイン (ラジアン)。 結果は、虚数軸に沿って、実際の軸に沿って [-π/2, + π/2] の間隔で無制限になります。

## <a name="remarks"></a>解説

C++ ではオーバーロードが可能であるため、 **_Fcomplex** と **_Lcomplex** の値を受け取って返す、 **casin** のオーバーロードを呼び出すことができます。 C プログラムでは、 **casin** は常にを受け取り、 **_Dcomplex** 値を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|C ヘッダー|C++ ヘッダー|
|-------------|--------------|------------------|
|**casin**、               **casin**、 **casinl**|\<complex.h>|\<ccomplex>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[アルファベット順の関数リファレンス](crt-alphabetical-function-reference.md)<br/>
[catanh、catanhf、catanhl](catanh-catanhf-catanhl.md)<br/>
[ctanh、ctanhf、ctanhl](ctanh-ctanhf-ctanhl.md)<br/>
[catan、catanf、catanl](catan-catanf-catanl.md)<br/>
[csinh、csinhf、csinhl](csinh-csinhf-csinhl.md)<br/>
[casinh、casinhf、casinhl](casinh-casinhf-casinhl.md)<br/>
[ccosh、ccoshf、ccoshl](ccosh-ccoshf-ccoshl.md)<br/>
[cacosh、cacoshf、cacoshl](cacosh-cacoshf-cacoshl.md)<br/>
[cacos、cacosf、cacosl](cacos-cacosf-cacosl.md)<br/>
[ctan、ctanf、ctanl](ctan-ctanf-ctanl.md)<br/>
[csin、csinf、csinl](csin-csinf-csinl.md)<br/>
[ccos、ccosf、ccosl](ccos-ccosf-ccosl.md)<br/>
[csqrt、csqrtf、csqrtl](csqrt-csqrtf-csqrtl.md)<br/>
