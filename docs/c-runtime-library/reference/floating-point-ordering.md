---
title: isgreater、isgreaterequal、isless、islessequal、islessgreater、isunordered
ms.date: 01/31/2019
f1_keywords:
- isgreater
- math/isgreater
- isgreaterequal
- math/isgreaterequal
- isless
- math/isless
- islessequal
- math/islessequal
- islessgreater
- math/islessgreater
- isunordered
- math/isunordered
helpviewer_keywords:
- isgreater function
- isgreaterequal function
- isless function
- islessequal function
- islessgreater function
- isunordered function
ms.openlocfilehash: 907b26f4e1824d7ef5c7c1a36b4e4d8ccb74c978
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220718"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater、isgreaterequal、isless、islessequal、islessgreater、isunordered

2つの浮動小数点値間の順序付けリレーションシップを決定します。

## <a name="syntax"></a>構文

```C
int isgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isgreaterequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isless(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isunordered(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */
```

```C++
template <class FloatingType1, class FloatingType2>
inline bool isgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isgreaterequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isless(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isunordered(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>パラメーター

*x*、 *y*<br/>
比較する浮動小数点値。

## <a name="return-value"></a>戻り値

すべての比較で、同じ符号の無限大が等しいと見なされます。 負の無限大は、有限値または正の無限大を下回っています。 正の無限大が有限値または負の無限大を超えています。 符号に関係なく、ゼロは等しくなります。 Nan が、他の NaN を含む任意の値よりも小さいか、同じか、または大きい値ではありません。

どちらの引数も NaN でない場合、順序**付けマクロは**、 *x*と*y*の間に指定された順序付けの関係が true を保持している場合、 **isgreaterequal**、 **isgreater**、および**islessequal**は0以外の値を返します。 これらのマクロは、いずれかまたは両方の引数が Nan の場合、または順序付け関係が false の場合に0を返します。 関数の形式は同じように動作しますが、 **`true`** またはを返し **`false`** ます。

*X*と*y*の両方が nan ではなく、 *x*が y よりも小さいか、または*y*より大きい場合、 **isless**マクロは0以外の値を返します。 いずれかまたは両方の引数が Nan の場合、または値が等しい場合は0を返します。 関数フォームは同じように動作しますが、 **`true`** またはを返し **`false`** ます。

**Isunordered なし**のマクロは、 *x*、 *y*、またはその両方が nan の場合、0以外の値を返します。 それ以外の場合は 0 を返します。 関数フォームは同じように動作しますが、 **`true`** またはを返し **`false`** ます。

## <a name="remarks"></a>解説

これらの比較操作は、C としてコンパイルした場合はマクロとして実装され、C++ としてコンパイルされる場合はインラインテンプレート関数として実装されます。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー (C)|必須ヘッダー (C++)|
|--------------|---------------------------|-------------------------------|
| **isgreater**、 **isgreaterequal**、 **isgreater**、<br/>**islessequal**、 **is不等号** **isunordered** | \<math.h> | \<math.h> または \<cmath> |

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[浮動小数点のサポート](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite、_finite、_finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan、_isnan、_isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass、_fpclassf](fpclass-fpclassf.md)<br/>
