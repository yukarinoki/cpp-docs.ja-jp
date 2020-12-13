---
description: '詳細情報: isinf'
title: isinf
ms.date: 01/31/2019
f1_keywords:
- isinf
- math/isinf
helpviewer_keywords:
- isinf function
ms.openlocfilehash: f174855ddbb8cc43fd7338d4254c0f03bf53967d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332637"
---
# <a name="isinf"></a>isinf

浮動小数点値が無限大であるかどうかを判断します。

## <a name="syntax"></a>構文

```C
int isinf(
   /* floating-point */ x
); /* C-only macro */

template <class FloatingType>
inline bool isinf(
   FloatingType x
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>パラメーター

*x*<br/>
テストする浮動小数点値。

## <a name="return-value"></a>戻り値

 **`true`** 引数 *x* が正または負の無限大の場合、isinf は (C++ コードでは) 0 以外の値を返します。 引数が有限または NAN の場合、 **isinf** は 0 ( **`false`** C++ コード内) を返します。 法線と subnormal の両方の浮動小数点値は、有限と見なされます。

## <a name="remarks"></a>解説

**isinf** は、c としてコンパイルされた場合はマクロ、C++ としてコンパイルされた場合はインラインテンプレート関数です。

## <a name="requirements"></a>要件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------------|-------------------------------|
|**isinf**|\<math.h>|\<math.h> または \<cmath>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
