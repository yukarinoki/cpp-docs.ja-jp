---
title: complex&lt;double&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<double>
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
ms.openlocfilehash: b9bf4780dd78800653804762301b36ff6bb30a92
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230079"
---
# <a name="complexltdoublegt"></a>complex&lt;double&gt;

順序付けされたオブジェクトのペア (最初のオブジェクトが **`double`** 複素数の実数部、2番目のオブジェクトが虚数部を表す) を格納するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as class template complex
};
```

### <a name="parameters"></a>パラメーター

*RealVal*\
**`double`** 構築される複素数の実数部の型の値。

*ImagVal*\
**`double`** 構築される複素数の虚数部の型の値。

*complexNum*\
**`float`** **`long double`** 構築される型の複素数を初期化するために実数部と虚数部が使用される型または型の複素数。 **`double`**

## <a name="return-value"></a>戻り値

型の複素数 **`double`** 。

## <a name="remarks"></a>解説

クラステンプレート complex を型の複合クラスに明示的に特殊化する **`double`** ことは、それが定義するコンストラクター内でのみクラステンプレートとは異なります。 からへの **`float`** 変換 **`double`** は暗黙的に行うことができますが、からへの変換は **`long double`** **`double`** である必要があり **`explicit`** ます。 を使用すると、 **`explicit`** 割り当て構文を使用した型変換での開始がルールによって除外されます。

クラステンプレートの詳細につい `complex` ては、「[複合クラス](../standard-library/complex-class.md)」を参照してください。 クラステンプレートのメンバーの一覧につい `complex` ては、「」を参照してください。

## <a name="example"></a>例

```cpp
// complex_comp_dbl.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << "as type double gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 4.0 , 5.0 );
   complex <double> c2double ( c2float );
   cout << "Implicit conversion from type float to type double,"
        << endl << "gives c2double = " << c2double << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 4.0 , 5.0 );
   complex <double> c3double ( c3longdouble );
   cout << "Explicit conversion from type float to type double,"
        << endl << "gives c3longdouble = " << c3longdouble << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3longdouble );
   double argc3 = arg ( c3longdouble );
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:" << endl
        << "arg ( c3 ) = " << argc3 << " radians, which is "
        << argc3 * 180 / pi << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type double gives c1 = (4,5)
Implicit conversion from type float to type double,
gives c2double = (4,5)
Explicit conversion from type float to type double,
gives c3longdouble = (4,5)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.
*/
```

## <a name="requirements"></a>必要条件

**ヘッダー**:\<complex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[複合クラス](../standard-library/complex-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
