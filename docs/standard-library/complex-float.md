---
description: 詳細については、「complex float」を参照してください。 &lt;&gt;
title: complex&lt;float&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<float>
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
ms.openlocfilehash: f3efa0425bbf7b6d1df4a6211d549ccf6693fd5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233852"
---
# <a name="complexltfloatgt"></a>complex&lt;float&gt;

順序付けされたオブジェクトのペア (最初のオブジェクトが **`float`** 複素数の実数部、2番目のオブジェクトが虚数部を表す) を格納するオブジェクトを記述します。

## <a name="syntax"></a>構文

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as class template complex
};
```

### <a name="parameters"></a>パラメーター

*_RealVal*\
**`float`** 構築される複素数の実数部の型の値。

*_ImagVal*\
**`float`** 構築される複素数の虚数部の型の値。

*complexNum*\
**`double`** **`long double`** 構築される型の複素数を初期化するために実数部と虚数部が使用される型または型の複素数。 **`float`**

## <a name="return-value"></a>戻り値

型の複素数 **`float`** 。

## <a name="remarks"></a>解説

クラステンプレート complex を型の複合クラスに明示的に特殊化する **`float`** ことは、それが定義するコンストラクター内でのみクラステンプレートとは異なります。 からへの **`float`** 変換 **`double`** は暗黙的に行うことができますが、からへの安全な変換は **`float`** **`long double`** でなければなり **`explicit`** ません。 を使用すると、 **`explicit`** 割り当て構文を使用した型変換での開始がルールによって除外されます。

クラステンプレートの詳細につい `complex` ては、「 [複合クラス](../standard-library/complex-class.md)」を参照してください。 クラステンプレートのメンバーの一覧につい `complex` ては、「」を参照してください。

## <a name="example"></a>例

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << endl << "gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << endl << "gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:"
        << endl << "arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
gives c2float = (1,3)
Explicit conversion from type long double to type float,
gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>要件

**ヘッダー**: \<complex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[複合クラス](../standard-library/complex-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
