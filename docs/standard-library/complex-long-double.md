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
ms.openlocfilehash: 19d4569523879911209bf0c05e762eba2c9852a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389178"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

この明示的に特殊化されたテンプレート クラスは、両方の種類のオブジェクトの順序付きペアを格納するオブジェクトをについて説明します**long double**、最初の複素数の値と、2 つ目の実数部を表す虚数部を表します。

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

// rest same as template class complex
};
```

### <a name="parameters"></a>パラメーター

*_RealVal*<br/>
構築される複素数の実数部の **long double** 型の値。

*_ImagVal*<br/>
型の値**long double**構築される複素数の虚数部。

*complexNum*<br/>
型の複素数**二重**または型の**float**が実数部と虚数部の部分は、型の複素数の初期化に使用される**long double**構築されます。

## <a name="return-value"></a>戻り値

型の複素数**long double**します。

## <a name="remarks"></a>Remarks

テンプレート クラスの明示的な特殊化`complex`型の complex クラスに対する**long double**定義コンス トラクターでのみ、テンプレート クラスとは異なります。 変換**long double**に**float**は暗黙的に許可されてからの変換が、**二重**に**long double**が必要ですある**明示的な**します。 **explicit** を使用すると、割り当て構文を使用した型変換による開始は禁止されます。

テンプレート クラスの詳細については`complex`、そのメンバーを参照してくださいと[complex クラス](../standard-library/complex-class.md)します。

**Microsoft 固有の仕様**:**Long double**と**二重**型は、同じの表現が、別の型。 詳細については、次を参照してください。[基本的な型](../cpp/fundamental-types-cpp.md)します。

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

**ヘッダー**: \<complex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[complex クラス](../standard-library/complex-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
