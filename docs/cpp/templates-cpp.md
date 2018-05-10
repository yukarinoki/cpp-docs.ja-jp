---
title: テンプレート (C++) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- template_cpp
dev_langs:
- C++
helpviewer_keywords:
- templates, C++
- templates [C++]
ms.assetid: 90fcc14a-2092-47af-9d2e-dba26d25b872
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5aa532246054ff0a0b67b9560e40ae704a40fc8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="templates-c"></a>テンプレート (C++)
テンプレートは、C++ では汎用のプログラミングの基礎です。 C++ では厳密に型指定された言語では、すべての変数を明示的にプログラマが宣言されている、またはコンパイラによって推測された特定の型を持つ必要があります。 ただし、多くのデータ構造やアルゴリズムの種類に関係なく同じに見えます。 これらの操作の種類のクラスや関数の操作を定義し、ユーザーがどのような具象型を指定できるテンプレートの有効化で動作する必要があります。  
  
## <a name="defining-and-using-templates"></a>定義して、テンプレートを使用します。  
 テンプレートは、コンパイル時にユーザーをテンプレート パラメーターの指定引数に基づいて、通常の型や関数を生成するコンストラクトです。 たとえば、次のように関数テンプレートを定義できます。  
  
```cpp  
template <typename T>  
T minimum(const T& lhs, const T& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 上記のコードには、1 つの型パラメーターを持つジェネリック関数のテンプレートがについて説明します`T`、戻り値、およびパラメーター (lhs と rhs) の呼び出しはすべてこの種類のです。 できる任意の名前を型パラメーターと同様が規則 1 つの大文字で入力して、最も一般的に使用します。 `T` テンプレート パラメーターです。`typename`キーワードは、このパラメーターは、型のプレース ホルダーを表示します。 コンパイラでのすべてのインスタンスが置き換えられます、関数が呼び出されると、`T`具象型引数では、ユーザーが指定した値またはコンパイラによって推測されたとします。 コンパイラには、クラスが生成されます。 または、テンプレートからの関数と呼びますプロセス*テンプレートのインスタンス化*です。  `minimum<int>`テンプレートのインスタンス化は、`minimum<T>`です。  
  
 他の場所で、ユーザーが int の特化したテンプレートのインスタンスを宣言できます。Get_a() と get_b() が int を返す関数であると仮定します。  
  
```  
int a = get_a();  
int b = get_b();  
int i = minimum<int>(a, b);  
```  
  
 ただし、ため、これは、関数テンプレートと、コンパイラがの型を推測`T`引数から`a`と`b`、通常の関数と同じように呼び出すことができます。  
  
```cpp  
int i = minimum(a, b);  
```  
  
 どのに一致するすべての新しい関数を生成、コンパイラには、その最後のステートメントが検出されると、 *T*テンプレートでは置き換え`int`:  
  
```  
  
      int minimum(const int& lhs, const int& rhs)  
{  
    return lhs < rhs ? lhs : rhs;  
}  
```  
  
 関数テンプレートにおいて、コンパイラが型の推論を実行するための規則は、通常の関数の規則に基づきます。 詳細については、次を参照してください。[オーバー ロードの解決の関数テンプレート呼び出し](../cpp/overload-resolution-of-function-template-calls.md)です。  
  
## <a id="type_parameters"></a> 型パラメーター  
 `minimum`テンプレート上、注意してください、型パラメーター`T`が使用されると関数の関数のパラメーターに const と参照修飾子が追加された任意の方法では修飾されません。  
  
 型パラメーターの数に事実上制限はありません。 複数のパラメーターをコンマで区切ります。  
  
```cpp  
template <typename T, typename U, typename V> class Foo{};  
  
```  
  
 キーワード`class`は等価`typename`このコンテキストでします。 前の例として表すことができます。  
  
```  
template <class T, class U, class V> class Foo{};   
```  
  
 0 個以上の型パラメーターの任意の数を受け取るテンプレートを定義するのに、省略記号演算子 (...) を使用できます。  
  
```cpp  
template<typename... Arguments> class vtclass;  
  
vtclass< > vtinstance1;  
vtclass<int> vtinstance2;  
vtclass<float, bool> vtinstance3;  
```  
  
 任意の組み込みまたはユーザー定義型は、型引数として使用できます。 Int、double、文字列を格納する標準ライブラリで std::vector を使用するなど、MyClass、const MyClass *、MyClass (& a)。 テンプレートを使用する場合は、重要な制限は、型引数が型パラメーターに適用されているすべての操作をサポートする必要があります。 たとえば、最小値と呼んで MyClass を使用して、この例のように。  
  
```cpp  
class MyClass  
{  
public:  
    int num;  
    std::wstring description;  
};  
  
int main()  
{      
    MyClass mc1 {1, L"hello"};  
    MyClass mc2 {2, L"goodbye"};  
    auto result = minimum(mc1, mc2); // Error! C2678  
}  
  
```  
  
 MyClass がのオーバー ロードを提供しないので、コンパイラ エラーが生成されます、< 演算子。  
  
 このような制限を適用するテンプレートを定義できますが、特定のテンプレートのすべての型引数が同じオブジェクトの階層に属している固有の要件はありません。 テンプレートのオブジェクト指向の手法を組み合わせることができます。たとえば、格納できます Derived * ベクターに\<ベース\*>。    引数はポインターである必要があります。  
  
```  
vector<MyClass*> vec;  
   MyDerived d(3, L"back again", time(0));  
   vec.push_back(&d);  
  
   // or more realistically:  
   vector<shared_ptr<MyClass>> vec2;  
   vec2.push_back(make_shared<MyDerived>());  
```  
  
 要素に設定する、ベクターとその他の標準ライブラリのコンテナーの基本的な要件`T`される`T`コピー割り当てとコピー構築します。  
  
## <a name="non-type-parameters"></a>非型パラメーター  
 C# や Java などの他の言語でジェネリック型の場合とは異なりは、C++ テンプレートは、値パラメーターとも呼ばれます。 非型パラメーターをサポートします。 たとえば、この例では、標準ライブラリで std::array クラスに似ていますと同様、配列の長さを指定する定数整数値を指定できます。  
  
```  
template<typename T, size_t L>  
class MyArray  
{  
    T arr[L];  
public:  
    MyArray() { ... }  
};  
  
```  
  
 テンプレート宣言の構文に注意してください。 Size_t 値は、コンパイル時に、テンプレート引数として渡され、定数または式を constexpr にする必要があります。 次のように使用します。  
  
```cpp  
MyArray<MyClass*, 10> arr;  
```  
  
 その他のポインターと参照を含む値は、非型パラメーターとしてで渡すことができます。 たとえば、ポインターに関数または関数オブジェクト、テンプレート コード内でいくつかの操作をカスタマイズするに渡すことができます。  
  
## <a id="template_parameters"></a> テンプレート パラメーターとしてテンプレート  
 テンプレートには、テンプレート パラメーターを指定できます。 この例では、MyClass2 は 2 つのテンプレート パラメーターを持ちます: typename パラメーター`T`とテンプレート パラメーター `Arr`:。  
  
```cpp  
template<typename T, template<typename U, int I> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
    U u; //Error. U not in scope  
};  
```  
  
 `Arr`パラメーター自体には本体がない、そのパラメーター名は必要ありません。 実際を参照すると、エラーは`Arr`の typename またはクラス内のパラメーター名からの本文`MyClass2`です。 このため、`Arr`のこの例で示すように、型パラメーター名を省略できます。  
  
```cpp  
template<typename T, template<typename, int> class Arr>  
class MyClass2  
{  
    T t; //OK  
    Arr<T, 10> a;  
};  
```  
  
## <a name="default-template-arguments"></a>既定のテンプレート引数  
 クラスと関数テンプレートは、既定の引数を持つことができます。 テンプレートがある既定の引数のままにするときに使用すると指定されていません。 たとえば、std::vector テンプレートには、アロケーターの既定の引数は。  
  
```cpp  
template <class T, class Allocator = allocator<T>> class vector;  
```  
  
 ほとんどの場合、既定 std::allocator クラスは、次のように、ベクトルを使用するため、許容されます。  
  
```cpp  
vector<int> myInts;  
```  
  
 かどうかに必要なことを指定するカスタム アロケーターが、次のようにします。  
  
```cpp  
vector<int, MyAllocator> ints;  
```  
  
 テンプレート引数が複数ある場合、最初の既定の引数の後は、すべての引数に既定の引数が必要です。  
  
 パラメーターを持つすべての既定のテンプレートを使用する場合は、空の山かっこを使用します。  
  
```cpp  
template<typename A = int, typename B = double>  
class Bar  
{  
    //...  
};  
...  
int main()  
{  
    Bar<> bar; // use all default type arguments  
}  
  
```  
  
## <a name="template-specialization"></a>テンプレートの特殊化  
 場合によっては、または任意の型に対して正確に同じコードを定義するテンプレートの不適切なことはありません。 たとえば、型引数は、ポインター、または、std::wstring または特定の基本クラスから派生した型である場合にのみ実行するコード パスを定義しておくこともできます。  このような場合に定義することができます、*特殊化*の特定の種類のテンプレートです。 ユーザーは、その型でテンプレートをインスタンス化と、コンパイラでは、特殊化を使用して、クラスを生成する、コンパイラは他のすべての種類では、一般的なテンプレートを選択します。 すべてのパラメーターが特殊な特殊化は*特殊化を完了*です。 呼び出された一部のパラメーターは、特化しただけの場合、*部分的特殊化*です。  
  
```cpp  
template <typename K, typename V>  
class MyMap{/*...*/};  
  
// partial specialization for string keys  
template<typename V>  
class MyMap<string, V> {/*...*/};  
...  
MyMap<int, MyClass> classes; // uses original template  
MyMap<string, MyClass> classes2; // uses the partial specialization  
  
```  
  
 テンプレート特殊化された型パラメーターごとに、一意な限り、任意の数の特殊化のことができます。   クラス テンプレートのみを部分的に特殊化することがあります。 テンプレートのすべての完了および部分的な特殊化は、元のテンプレートと同じ名前空間で宣言する必要があります。  
  
 詳細については、次を参照してください。[テンプレートの特殊化](../cpp/template-specialization-cpp.md)です。