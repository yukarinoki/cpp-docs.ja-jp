---
title: typeid 演算子
ms.date: 11/04/2016
helpviewer_keywords:
- typeid operator
ms.assetid: 8871cee6-d6b9-4301-a5cb-bf3dc9798d61
ms.openlocfilehash: dfbf5275391e2820c94d2827c9b2c3eb252365c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571926"
---
# <a name="typeid-operator"></a>typeid 演算子

## <a name="syntax"></a>構文

```
typeid(type-id)
typeid(expression)
```

## <a name="remarks"></a>Remarks

**Typeid**演算子により、実行時に決定されるオブジェクトの型。

結果**typeid**は、`const type_info&`します。 値がへの参照を`type_info`いずれかを表すオブジェクト、*タイプ id*または種類の*式*の形式に応じて、 **typeid**使用されます。 参照してください[type_info クラス](../cpp/type-info-class.md)詳細についてはします。

**Typeid**演算子は、マネージ型 (抽象宣言子またはインスタンス) では機能しませんを参照してください[typeid](../windows/typeid-cpp-component-extensions.md)取得について、<xref:System.Type>指定の型。

**Typeid**演算子は、ポリモーフィックなクラス型の左辺値に適用すると、実行時チェックによって提供される静的情報オブジェクトの実際の型を特定できません。 そのようなケースを次に示します。

- クラスへの参照

- 逆参照、ポインター \*

- 添字付きのポインター ([ ]) (一般に、ポリモーフィックな型へのポインターで添字を使用すると、安全ではないことに注意してください)。

場合、*式*まだその基底クラスから派生した型のオブジェクトが実際には、基本クラスの型を指す、`type_info`派生クラスは、結果を参照します。 *式*ポリモーフィックな型 (仮想関数を持つクラス) をポイントする必要があります。 結果は、それ以外の場合、`type_info`で参照される静的クラスの*式*します。 さらに、ポインターが指し示すオブジェクトが使用されるように、ポインターを逆参照する必要があります。 ポインターを逆参照になります、`type_info`どのような it ではないが指すポインター。 例えば:

```cpp
// expre_typeid_Operator.cpp
// compile with: /GR /EHsc
#include <iostream>
#include <typeinfo.h>

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

場合、*式*、ポインターを逆参照はポインターの値が 0、 **typeid**がスローされます、 [bad_typeid 例外](../cpp/bad-typeid-exception.md)。 ポインターが有効なオブジェクトを指していない場合は、`__non_rtti_object`例外がスローされたエラーをトリガーした RTTI を分析する試行を示す (アクセス違反など)、オブジェクトが何らかの理由で無効です (無効なポインターや、コードがコンパイルした[/GR](../build/reference/gr-enable-run-time-type-information.md))。

場合、*式*はポインターでも、オブジェクトの基底クラスへの参照を結果は、`type_info`の静的な型を表す参照、*式*します。 *静的な型*式の型を表し、式のコンパイル時に認識されています。 実行セマンティクスは、式の静的な型を評価するときは無視されます。 さらに、式の静的な型を判断するときに、参照は可能な限り無視されます。

```cpp
// expre_typeid_Operator_2.cpp
#include <typeinfo>

int main()
{
   typeid(int) == typeid(int&); // evaluates to true
}
```

**typeid**テンプレートのパラメーターの種類を決定するテンプレートでも使用されます。

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

[ランタイム型情報](../cpp/run-time-type-information.md)<br/>
[キーワード](../cpp/keywords-cpp.md)