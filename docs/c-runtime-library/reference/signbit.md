---
description: 詳細については、「signbit」を参照してください。
title: signbit
ms.date: 01/31/2019
f1_keywords:
- signbit
- math/signbit
helpviewer_keywords:
- signbit function
ms.openlocfilehash: 7f6416647db67a49bd6950c011575b72f4c43f10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303467"
---
# <a name="signbit"></a>signbit

浮動小数点値が負であるかどうかを判断します。

## <a name="syntax"></a>構文

```C
int signbit(
   /* floating-point */ x
); /* C-only macro */

inline bool signbit(
   float x
) throw(); /* C++-only overloaded function */

inline bool signbit(
   double x
) throw(); /* C++-only overloaded function */

inline bool signbit(
   long double x
) throw(); /* C++-only overloaded function */
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

 **`true`** 引数 *x* が負の値または負の無限大である場合、Signbit は、(C++ では) 0 以外の値を返します。 **`false`** 引数が負でない、正の無限大、または NAN の場合は、0 (C++ では) を返します。

## <a name="remarks"></a>解説

**signbit** は、c としてコンパイルされた場合はマクロ、C++ としてコンパイルされる場合はオーバーロードされたインライン関数です。

## <a name="requirements"></a>要件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------------|-------------------------------|
|**signbit**|\<math.h>|\<math.h> または \<cmath>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
