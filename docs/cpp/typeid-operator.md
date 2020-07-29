---
title: typeid 演算子
ms.date: 10/04/2019
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: e17b88d81d9987ec586401e025e108cfbe88cb3b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223525"
---
# <a name="typeid-operator"></a>typeid 演算子

## <a name="syntax"></a>構文

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>解説

**`typeid`** 演算子を使用すると、オブジェクトの型を実行時に決定できます。

の結果は **`typeid`** `const type_info&` です。 値は、 `type_info` 使用されるの形式に応じて、*型 id*または*式*の型のいずれかを表すオブジェクトへの参照です **`typeid`** 。 詳細については、「 [Type_info クラス](../cpp/type-info-class.md)」を参照してください。

**`typeid`** 演算子はマネージ型 (抽象宣言子またはインスタンス) では機能しません。 指定された型のを取得する方法については <xref:System.Type> 、「 [typeid](../extensions/typeid-cpp-component-extensions.md)」を参照してください。

演算子は、 **`typeid`** ポリモーフィックなクラス型の左辺値に適用される場合にランタイムチェックを実行します。この場合、オブジェクトの実際の型は、指定された静的な情報によって判断されることはありません。 そのようなケースを次に示します。

- クラスへの参照

- ポインター (逆参照)`*`

- 添字ポインター ( `[ ]` )。 (ポリモーフィックな型へのポインターで添字を使用するのは安全ではありません)。

*式*が基底クラス型を指していても、オブジェクトがその基底クラスから派生した型である場合、 `type_info` 派生クラスの参照が結果になります。 *式*はポリモーフィック型 (仮想関数を持つクラス) を指す必要があります。 それ以外の場合、結果は、 `type_info` *式*で参照されている静的クラスのになります。 また、ポインターを逆参照する必要があります。これにより、使用されるオブジェクトが参照先のオブジェクトになります。 ポインターを逆参照しない場合、結果は `type_info` ポインターが指すものではなく、ポインターのになります。 次に例を示します。

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo>

class Base {
public:
   virtual void vvfunc() {}
};

class Derived : public Base {};

using namespace std;
int main() {
   Derived* pd = new Derived;
   Base* pb = pd;
   cout << typeid( pb ).name() << endl;   //prints "class Base *"
   cout << typeid( *pb ).name() << endl;   //prints "class Derived"
   cout << typeid( pd ).name() << endl;   //prints "class Derived *"
   cout << typeid( *pd ).name() << endl;   //prints "class Derived"
   delete pd;
}
```

*式*がポインターを逆参照していて、そのポインターの値が0である場合、は **`typeid`** [bad_typeid 例外](../cpp/bad-typeid-exception.md)をスローします。 ポインターが有効なオブジェクトを指していない場合は、 `__non_rtti_object` 例外がスローされます。 オブジェクトが無効であるためにエラーをトリガーした RTTI の分析が試行されたことを示します。 (たとえば、無効なポインターであるか、またはコードが[/gr](../build/reference/gr-enable-run-time-type-information.md)でコンパイルされていません)。

*式*がオブジェクトの基底クラスへの参照ではなくポインターではない場合、結果は `type_info` *式*の静的な型を表す参照になります。 式の*静的な型*は、コンパイル時に認識される式の型を参照します。 実行セマンティクスは、式の静的な型を評価するときは無視されます。 さらに、式の静的な型を判断するときに、参照は可能な限り無視されます。

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**`typeid`** テンプレートで使用して、テンプレートパラメーターの型を決定することもできます。

```cpp
// expre_typeid_Operator_3.cpp
// compile with: /c
#include <typeinfo>
template < typename T >
T max( T arg1, T arg2 ) {
   cout << typeid( T ).name() << "s compared." << endl;
   return ( arg1 > arg2 ? arg1 : arg2 );
}
```

## <a name="see-also"></a>関連項目

[実行時の型情報](../cpp/run-time-type-information.md)\
[キーワード](../cpp/keywords-cpp.md)
