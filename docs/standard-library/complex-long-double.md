---
title: complex&lt;long double&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 73027ba76d608424b1a6da346e861b10c66989fe
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228389"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

この明示的に特殊化されたクラステンプレートは、順序付けされたオブジェクトのペア (両方の型) を格納するオブジェクトを記述し **`long double`** ます。1つは複素数の実数部、2番目のオブジェクトは虚数部を表します。

## <a name="syntax"></a>構文

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as class template complex
};
```

### <a name="parameters"></a>パラメーター

*_RealVal*\
**`long double`** 構築される複素数の実数部の型の値。

*_ImagVal*\
**`long double`** 構築される複素数の虚数部の型の値。

*complexNum*\
**`double`** **`float`** 構築される型の複素数を初期化するために実数部と虚数部が使用される型または型の複素数。 **`long double`**

## <a name="return-value"></a>戻り値

型の複素数 **`long double`** 。

## <a name="remarks"></a>解説

クラステンプレートを `complex` 型の複合クラスに明示的に特殊化する **`long double`** ことは、それが定義するコンストラクター内でのみクラステンプレートとは異なります。 からへの **`long double`** 変換 **`float`** は暗黙的に行うことができますが、からへの変換は **`double`** **`long double`** である必要があり **`explicit`** ます。 を使用すると、 **`explicit`** 割り当て構文を使用した型変換での開始がルールによって除外されます。

クラステンプレートとそのメンバーの詳細につい `complex` ては、「[複合クラス](../standard-library/complex-class.md)」を参照してください。

**Microsoft 固有**: **`long double`** **`double`** 型と型は同じ表現を持ちますが、異なる型です。 詳細については、「[組み込み型](../cpp/fundamental-types-cpp.md)」を参照してください。

## <a name="example"></a>例

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<long double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of complex number of type float
    complex<float> c2float( 1.0 , 3.0 );
    complex<long double> c2longdouble ( c2float );
    cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

    // The third constructor initializes values of the real &
    // imaginary parts using those of a complex number
    // of type double
    complex<double> c3double( 3.0 , 4.0 );
    complex<long double> c3longdouble( c3double );
    cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3longdouble );
    double argc3 = arg( c3longdouble );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

```Output
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg( c3 ) = 0.927295 radians, which is 53.1301 degrees.
```

## <a name="requirements"></a>必要条件

**ヘッダー**:\<complex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[複合クラス](../standard-library/complex-class.md)\
[C++ 標準ライブラリのスレッドセーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
