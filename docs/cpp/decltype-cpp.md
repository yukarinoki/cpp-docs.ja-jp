---
title: decltype  (C++)
ms.date: 11/04/2016
f1_keywords:
- decltype_cpp
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
ms.openlocfilehash: abcc18ee29e2dcb09ca15ae77219ae5dd4d74c65
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228935"
---
# <a name="decltype--c"></a>decltype  (C++)

**`decltype`** 型指定子は、指定された式の型を生成します。 **`decltype`** 型指定子は[ `auto` キーワード](../cpp/auto-cpp.md)と共に、主にテンプレートライブラリを記述する開発者にとって役立ちます。 とを使用し **`auto`** て、 **`decltype`** 戻り値の型がテンプレート引数の型に依存するテンプレート関数を宣言します。 または、とを使用して、 **`auto`** **`decltype`** 別の関数の呼び出しをラップするテンプレート関数を宣言し、ラップされた関数の戻り値の型を返します。

## <a name="syntax"></a>構文

> **`decltype(`***式***`)`**

### <a name="parameters"></a>パラメーター

|パラメーター|[説明]|
|---------------|-----------------|
|*式 (expression)*|式。 詳細については、「[式](../cpp/expressions-cpp.md)」を参照してください。|

## <a name="return-value"></a>戻り値

*式*パラメーターの型。

## <a name="remarks"></a>解説

**`decltype`** 型指定子は、Visual Studio 2010 以降のバージョンでサポートされており、ネイティブコードまたはマネージコードと共に使用できます。 `decltype(auto)` (C++14) は Visual Studio 2015 以降でサポートされています。

コンパイラは、次の規則を使用して、*式*パラメーターの型を決定します。

- *Expression*パラメーターが識別子または[クラスメンバーアクセス](../cpp/member-access-operators-dot-and.md)の場合、 `decltype(expression)` は*expression*によって名前が付けられたエンティティの型になります。 このようなエンティティが存在しない場合や、*式*パラメーターがオーバーロードされた関数のセットに名前を指定していない場合は、コンパイラによってエラーメッセージが生成されます。

- *Expression*パラメーターが関数またはオーバーロードされた演算子関数の呼び出しである場合、 `decltype(expression)` は関数の戻り値の型です。 オーバーロードされた演算子を囲んでいるかっこは無視されます。

- *Expression*パラメーターが[右辺](../cpp/lvalues-and-rvalues-visual-cpp.md)値の場合 `decltype(expression)` は、*式*の型です。 *Expression*パラメーターが[左辺](../cpp/lvalues-and-rvalues-visual-cpp.md)値の場合、 `decltype(expression)` は*式*の型への左辺値[参照](../cpp/lvalue-reference-declarator-amp.md)です。

型指定子の使用例を次のコード例に示し **`decltype`** ます。 最初に次のステートメントを記述したとします。

```cpp
int var;
const int&& fx();
struct A { double x; }
const A* a = new A();
```

次に、次の表に示す4つのステートメントによって返される型を確認し **`decltype`** ます。

|ステートメント|Type|Notes|
|---------------|----------|-----------|
|`decltype(fx());`|`const int&&`|への[右辺](../cpp/rvalue-reference-declarator-amp-amp.md)値参照 **`const int`** 。|
|`decltype(var);`|**`int`**|変数 `var` の型。|
|`decltype(a->x);`|**`double`**|メンバー アクセスの型。|
|`decltype((a->x));`|`const double&`|内側のかっこは、ステートメントをメンバー アクセスではなく式として評価します。 また、 `a` はポインターとして宣言されているため、 **`const`** 型はへの参照です **`const double`** 。|

## <a name="decltype-and-auto"></a>decltype および auto

C++ 14 では、 `decltype(auto)` 後続の戻り値の型を指定せずにを使用して、戻り値の型がテンプレート引数の型に依存するテンプレート関数を宣言できます。

C++ 11 では、後続の戻り値の型の型指定子をキーワードと共に使用して、 **`decltype`** **`auto`** 戻り値の型がテンプレート引数の型に依存するテンプレート関数を宣言できます。 たとえば、テンプレート関数の戻り値の型がテンプレート引数の型に依存している次のコード例について考えます。 コード例では、*不明な*プレースホルダーは戻り値の型を指定できないことを示しています。

```cpp
template<typename T, typename U>
UNKNOWN func(T&& t, U&& u){ return t + u; };
```

**`decltype`** 型指定子の導入により、開発者は、テンプレート関数が返す式の型を取得できます。 後に示す*別の関数宣言構文*、 **`auto`** キーワード、および **`decltype`** 型指定子を使用して、*遅延指定*の戻り値の型を宣言します。 遅延指定された戻り値の型は、宣言がコード化されたときではなく、コンパイルされたときに決定します。

次のプロトタイプは代替関数宣言の構文について説明します。 **`const`** 修飾子と修飾子、 **`volatile`** および **`throw`** [例外指定](../cpp/exception-specifications-throw-cpp.md)は省略可能であることに注意してください。 *Function_body*プレースホルダーは、関数の動作を指定する複合ステートメントを表します。 コーディングのベストプラクティスとして、ステートメント内の*式*のプレースホルダーは、 **`decltype`** **`return`** ステートメント (存在する場合) によって指定された式と一致する必要があります ( *function_body*)。

**`auto`***function_name* **`(`***パラメーター*<sub>opt</sub> **`)`** **`const`** <sub>opt</sub> **`volatile`** <sub>opt</sub> **`->`** **`decltype(`** *式*の **`)`** **`noexcept`** <sub>選択</sub> **`{`** *function_body***`};`**

次のコード例では、`myFunc` テンプレート関数の遅延指定された戻り値の型は、テンプレート引数 `t` と `u` の型によって決まります。 コーディングのベストプラクティスとして、コード例では、 `forward` *完全転送*をサポートする右辺値参照と関数テンプレートも使用します。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。

```cpp
//C++11
template<typename T, typename U>
auto myFunc(T&& t, U&& u) -> decltype (forward<T>(t) + forward<U>(u))
        { return forward<T>(t) + forward<U>(u); };

//C++14
template<typename T, typename U>
decltype(auto) myFunc(T&& t, U&& u)
        { return forward<T>(t) + forward<U>(u); };
```

## <a name="decltype-and-forwarding-functions-c11"></a>Decltype および転送関数 (C++11)

転送関数は、他の関数の呼び出しをラップします。 関数テンプレートで、引数、またはそれらの引数を含む式の結果を別の関数に転送する場合を考えます。 さらに、転送関数は、他の関数を呼び出した結果を返します。 このシナリオでは、転送関数の戻り値の型は、ラップされた関数の戻り値の型と同じである必要があります。

このシナリオでは、型指定子を使用せずに適切な型の式を記述することはできません **`decltype`** 。 **`decltype`** 型指定子は、関数が参照型を返すかどうかに関する必要な情報を失うことはないため、汎用転送関数を有効にします。 転送関数のコード例については、前の `myFunc` テンプレート関数の例を参照してください。

## <a name="example"></a>例

次のコード例は、テンプレート関数 `Plus()` の遅延指定の戻り値の型を宣言します。 関数は、 `Plus` オーバーロードを使用して2つのオペランドを処理し **`operator+`** ます。 そのため、関数のプラス演算子 ( **`+`** ) と戻り値の型の解釈は、関数の `Plus` 引数の型によって異なります。

```cpp
// decltype_1.cpp
// compile with: cl /EHsc decltype_1.cpp

#include <iostream>
#include <string>
#include <utility>
#include <iomanip>

using namespace std;

template<typename T1, typename T2>
auto Plus(T1&& t1, T2&& t2) ->
   decltype(forward<T1>(t1) + forward<T2>(t2))
{
   return forward<T1>(t1) + forward<T2>(t2);
}

class X
{
   friend X operator+(const X& x1, const X& x2)
   {
      return X(x1.m_data + x2.m_data);
   }

public:
   X(int data) : m_data(data) {}
   int Dump() const { return m_data;}
private:
   int m_data;
};

int main()
{
   // Integer
   int i = 4;
   cout <<
      "Plus(i, 9) = " <<
      Plus(i, 9) << endl;

   // Floating point
   float dx = 4.0;
   float dy = 9.5;
   cout <<
      setprecision(3) <<
      "Plus(dx, dy) = " <<
      Plus(dx, dy) << endl;

   // String
   string hello = "Hello, ";
   string world = "world!";
   cout << Plus(hello, world) << endl;

   // Custom type
   X x1(20);
   X x2(22);
   X x3 = Plus(x1, x2);
   cout <<
      "x3.Dump() = " <<
      x3.Dump() << endl;
}
```

```Output
Plus(i, 9) = 13
Plus(dx, dy) = 13.5
Hello, world!
x3.Dump() = 42
```

## <a name="example"></a>例

**Visual Studio 2017 以降:** コンパイラは **`decltype`** 、テンプレートがインスタンス化されるのではなく、宣言されている場合に引数を解析します。 したがって、引数に非依存の特殊化が見つかった場合は、 **`decltype`** インスタンス化時に遅延されることはなく、直ちに処理され、結果のエラーはその時点で診断されます。

次の例は、宣言時に発生するこのようなコンパイラ エラーを示しています。

```cpp
#include <utility>
template <class T, class ReturnT, class... ArgsT> class IsCallable
{
public:
   struct BadType {};
   template <class U>
   static decltype(std::declval<T>()(std::declval<ArgsT>()...)) Test(int); //C2064. Should be declval<U>
   template <class U>
   static BadType Test(...);
   static constexpr bool value = std::is_convertible<decltype(Test<T>(0)), ReturnT>::value;
};

constexpr bool test1 = IsCallable<int(), int>::value;
static_assert(test1, "PASS1");
constexpr bool test2 = !IsCallable<int*, int>::value;
static_assert(test2, "PASS2");
```

## <a name="requirements"></a>必要条件

Visual Studio 2010 以降のバージョン。

`decltype(auto)`Visual Studio 2015 以降が必要です。
