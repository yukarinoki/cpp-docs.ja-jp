---
title: decltype (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- decltype_cpp
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], decltype
- decltype operator
- operators [C++], type of an expression
- operators [C++], deduce expression type
ms.assetid: 6dcf8888-8196-4f13-af50-51e3797255d4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac9fe7ebf3d3e406854308e56d38e37567acc07a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418040"
---
# <a name="decltype--c"></a>decltype (C++)
`decltype` 型指定子は、指定された式の型を生成します。 `decltype`と共に指定子を入力、 [auto キーワード](../cpp/auto-cpp.md)、主に記述する開発者にとってテンプレート ライブラリ役に立ちます。 `auto` と `decltype` を使用して、テンプレートの引数の型に応じた戻り値の型を持つテンプレート関数を宣言します。 または、`auto` と `decltype` を使用して、別の関数の呼び出しをラップしたテンプレート関数を宣言し、ラップされた関数の戻り値の型を返します。  
  
## <a name="syntax"></a>構文  
  
```  
decltype( expression )  
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`expression`|任意の式を指定します。 詳細については、次を参照してください。[式](../cpp/expressions-cpp.md)です。|  
  
## <a name="return-value"></a>戻り値  
 `expression` パラメーターの型。  
  
## <a name="remarks"></a>コメント  
 `decltype` 型指定子は、Visual C++ 2010 以降のバージョンでサポートされ、ネイティブ コードまたはマネージ コードと共に使用できます。 `decltype(auto)` (C++14) は Visual Studio 2015 以降でサポートされています。  
  
 コンパイラは、`expression` パラメーターの型を特定するために以下の規則を使用します。  
  
-   場合、`expression`パラメーターは、識別子または[クラス メンバーに対するアクセス](../cpp/member-access-operators-dot-and.md)、`decltype(expression)`によってという名前のエンティティの種類は、`expression`です。 このようなエンティティまたは `expression` パラメーター名で一連のオーバーロードされた関数に名前を付けると、コンパイラでエラー メッセージが生成されます。  
  
-   場合、`expression`パラメーターが関数またはオーバー ロードされた演算子関数への呼び出し`decltype(expression)`は関数の戻り値の型。 オーバーロードされた演算子を囲んでいるかっこは無視されます。  
  
-   場合、`expression`パラメーターは、[右辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)、`decltype(expression)`の種類は、`expression`です。 場合、`expression`パラメーターは、[左辺値](../cpp/lvalues-and-rvalues-visual-cpp.md)、`decltype(expression)`は、[左辺値参照](../cpp/lvalue-reference-declarator-amp.md)の型に`expression`です。  
  
 `decltype` 型指定子のいくつかの使用方法を次のコード例に示します。 最初に次のステートメントを記述したとします。  
  
```cpp  
int var;  
const int&& fx();   
struct A { double x; }  
const A* a = new A();  
```  
  
 次に、次の表の 4 つの `decltype` ステートメントによって返される型をチェックします。  
  
|ステートメント|型|メモ|  
|---------------|----------|-----------|  
|`decltype(fx());`|`const int&&`|[右辺値参照](../cpp/rvalue-reference-declarator-amp-amp.md)を`const int`です。|  
|`decltype(var);`|`int`|変数 `var` の型。|  
|`decltype(a->x);`|`double`|メンバー アクセスの型。|  
|`decltype((a->x));`|`const double&`|内側のかっこは、ステートメントをメンバー アクセスではなく式として評価します。 そして、`a` は `const` ポインターとして宣言されているため、型は `const double` への参照です。|  
  
## <a name="decltype-and-auto"></a>decltype および auto  
 C++ 14 で使用できます`decltype(auto)`ありません後続の戻り値の型をテンプレート関数の戻り値の型を宣言すると、テンプレート引数の型に依存します。  
  
 C++11 では、テンプレートの引数の型に応じて戻り値の型が異なるテンプレート関数を宣言するために、`auto` キーワードとともに、後続の戻り値の型に `decltype` 型指定子を使用できます。 たとえば、テンプレート関数の戻り値の型がテンプレート引数の型に依存している次のコード例について考えます。 コード例では、*不明な*プレース ホルダーは、戻り値の型を指定できないことを示します。  
  
```cpp  
template<typename T, typename U>  
UNKNOWN func(T&& t, U&& u){ return t + u; };   
```  
  
 `decltype` 型指定子を導入することで、開発者はテンプレート関数が返す式の型を取得できます。 使用して、*代替関数宣言の構文*後に表示される、`auto`キーワード、および`decltype`宣言指定子を入力、*遅延指定された*型を返します。 遅延指定された戻り値の型は、宣言がコード化されたときではなく、コンパイルされたときに決定します。  
  
 次のプロトタイプは代替関数宣言の構文について説明します。 注意してください、`const`と`volatile`修飾子、および`throw`[例外指定](../cpp/exception-specifications-throw-cpp.md)は省略可能です。 *Function_body*プレース ホルダーは、関数の動作を指定する複合ステートメントを表します。 コーディングのベスト プラクティスとして、*式*内のプレース ホルダー、`decltype`ステートメントで指定された表現に一致する必要があります、`return`ステートメントでは、存在する場合に、 *function_body*です。  
  
 **自動** *function_name* **(** *パラメーター*<sub>opt</sub> **)** **const**<sub>opt</sub> **揮発性**<sub>opt</sub> **->** **decltype (***式* **)** **スロー**<sub>opt</sub> **{** *function_body***};**  
  
 次のコード例では、`myFunc` テンプレート関数の遅延指定された戻り値の型は、テンプレート引数 `t` と `u` の型によって決まります。 コーディングのベスト プラクティス、として、コード例もは右辺値参照と`forward`関数テンプレートは、サポート*完全転送を行います*です。 詳細については、「[右辺値参照宣言子: &&](../cpp/rvalue-reference-declarator-amp-amp.md)」を参照してください。  
  
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
  
 このシナリオでは、`decltype` 型指定子がないと、適切な型式を記述できません。 `decltype` 型指定子は、関数が参照型を返すかどうかに関する必須情報を失わないという理由で、ジェネリック転送関数を有効にします。 転送関数のコード例については、前の `myFunc` テンプレート関数の例を参照してください。  
  
## <a name="example"></a>例  
 次のコード例は、テンプレート関数 `Plus()` の遅延指定の戻り値の型を宣言します。 `Plus` の関数は `operator+` オーバーロードを持つ 2 つのオペランドを処理します。 その結果、プラス演算子 (+) と `Plus` 関数の戻り値の型の解釈は、関数の引数の型によって異なります。  
  
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
**2017 およびそれ以降の visual Studio:** テンプレートは宣言ではなくインスタンス化されるときに、コンパイラが decltype 引数を解析します。 その結果、decltype 引数に非依存の特殊化が見つかった場合、インスタンス化時まで遅延されずにすぐに処理され、結果として発生したエラーは、その時点で診断されます。

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

## <a name="requirements"></a>要件  
 Visual C++ 2010 以降のバージョン。  
  
 `decltype(auto)` Visual Studio 2015 以降が必要です。  
  
