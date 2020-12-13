---
description: '詳細情報: isnormal'
title: isnormal
ms.date: 01/31/2019
f1_keywords:
- isnormal
- math/isnormal
helpviewer_keywords:
- isnormal function
ms.openlocfilehash: 3afae5196a7a6b2b149028ad347f95baa27b1544
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337762"
---
# <a name="isnormal"></a>isnormal

浮動小数点値が通常の値かどうかを判断します。

## <a name="syntax"></a>構文

```C
int isnormal(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isnormal(
   FloatingType x
) throw(); /* C++-only function template */
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

 **`true`** 引数 *x* が0、subnormal、無限、NaN のいずれでもない場合、isnormal は0以外の値 (C++ コード) を返します。 それ以外の場合、 **isnormal** は 0 ( **`false`** C++ コードでは) を返します。

## <a name="remarks"></a>解説

**isnormal** は、c としてコンパイルされた場合はマクロ、C++ としてコンパイルされた場合はインライン関数テンプレートです。

## <a name="requirements"></a>要件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------------|-------------------------------|
|**isnormal**|\<math.h>|\<math.h> または \<cmath>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
