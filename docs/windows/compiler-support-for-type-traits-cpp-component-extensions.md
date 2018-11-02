---
title: 型の特徴のコンパイラ サポート (C +/cli および C++/cli CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __is_simple_value_class
- __has_trivial_destructor
- __has_assign
- __is_union
- __is_class
- __is_abstract
- __has_trivial_assign
- __has_virtual_destructor
- __is_ref_array
- __is_base_of
- __has_copy
- __is_polymorphic
- __has_nothrow_constructor
- __is_ref_class
- __is_delegate
- __is_convertible_to
- __is_value_class
- __is_interface_class
- __has_nothrow_copy
- __is_sealed
- __has_trivial_constructor
- __has_trivial_copy
- __is_enum
- __has_nothrow_assign
- __has_finalizer
- __is_empty
- __is_pod
- __has_user_destructor
helpviewer_keywords:
- __is_class keyword [C++]
- __is_pod keyword [C++]
- __is_delegate keyword [C++]
- __is_value_class keyword [C++]
- __has_copy keyword [C++]
- __has_nothrow_copy keyword [C++]
- __is_interface_class keyword [C++]
- __is_sealed keyword [C++]
- __is_convertible_to keyword [C++]
- __is_ref_class keyword [C++]
- __has_trivial_copy keyword [C++]
- __has_user_destructor keyword [C++]
- __is_abstract keyword [C++]
- __is_empty keyword [C++]
- __has_trivial_assign keyword [C++]
- __has_nothrow_constructor keyword [C++]
- __is_ref_array keyword [C++]
- __is_base_of keyword [C++]
- __has_nothrow_assign keyword [C++]
- __has_virtual_destructor keyword [C++]
- __has_finalizer keyword [C++]
- __is_union keyword [C++]
- __has_assign keyword [C++]
- __has_trivial_destructor keyword [C++]
- __is_polymorphic keyword [C++]
- __is_enum keyword [C++]
- __is_simple_value_class keyword [C++]
- __has_trivial_constructor keyword [C++]
ms.assetid: cd440630-0394-48c0-a16b-1580b6ef5844
ms.openlocfilehash: 5cd4d7feef01d1b7bedd407357c618ba208d06f4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536189"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>型の特徴のコンパイラ サポート (C +/cli および C++/cli CX)

Microsoft C コンパイラがサポート*特徴の入力*c++/cli および C++/cli CX 拡張機能、コンパイル時に、型のさまざまな特性を示します。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="remarks"></a>Remarks

型の特徴は、ライブラリを記述するプログラマにとって特に便利です。

次の一覧には、コンパイラでサポートされている型の特徴が含まれています。 すべての特徴の戻り値の型**false**型の特徴の名前で指定された条件が満たされていない場合。

(C + のみで、以下のコード例が記述された/cli CLI。 対応する型の特徴が c++ もサポートされていますが、/cli CX 明記しない限り、します。 「プラットフォーム型」と Windows ランタイム型または共通言語ランタイム型のいずれかです。)

- `__has_assign(` *型* `)`

   返します**true**プラットフォーム型またはネイティブ型にコピー代入演算子がある場合。

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(` *型* `)`

   返します**true**プラットフォーム型またはネイティブ型にコピー コンス トラクターがある場合。

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(` *型* `)`

   (C + ではサポートされていません/cli CX)。返します**true** CLR 型にファイナライザーがある場合。 参照してください[する方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)詳細についてはします。

    ```cpp
    using namespace System;
    ref struct R {
    ~R() {}
    protected:
    !R() {}
    };

    int main() {
    Console::WriteLine(__has_finalizer(R));
    }
    ```

- `__has_nothrow_assign(` *型* `)`

   返します**true**コピー代入演算子を空の例外の仕様がある場合。

    ```cpp
    #include <stdio.h>
    struct S {
    void operator=(S& r) throw() {}
    };

    int main() {
    __has_nothrow_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_constructor(` *型* `)`

   返します**true**場合、既定のコンス トラクターは、空の例外の仕様。

    ```cpp
    #include <stdio.h>
    struct S {
    S() throw() {}
    };

    int main() {
    __has_nothrow_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_nothrow_copy(` *型* `)`

   返します**true**場合、コピー コンス トラクターは、空の例外の仕様。

    ```cpp
    #include <stdio.h>
    struct S {
    S(S& r) throw() {}
    };

    int main() {
    __has_nothrow_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_assign(` *型* `)`

   返します**true**型が単純なコンパイラによって生成された代入演算子。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(` *型* `)`

   返します**true**型が単純なコンパイラによって生成されたコンス トラクター。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(` *型* `)`

   返します**true**型、単純なコンパイラによって生成されたコピー コンス トラクターがある場合。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(` *型* `)`

   返します**true**型に単純なコンパイラによって生成されたデストラクターがある場合。

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(` *型* `)`

   返します**true**プラットフォーム型またはネイティブ型にユーザーが宣言したデストラクターがある場合。

    ```cpp
    // has_user_destructor.cpp

    using namespace System;
    ref class R {
    ~R() {}
    };

    int main() {
    Console::WriteLine(__has_user_destructor(R));
    }
    ```

- `__has_virtual_destructor(` *型* `)`

   返します**true**型仮想デストラクターがある場合。

   `__has_virtual_destructor` はプラットフォーム型でも機能します。また、プラットフォーム型のユーザー定義のデストラクターは仮想デストラクターです。

    ```cpp
    // has_virtual_destructor.cpp
    #include <stdio.h>
    struct S {
    virtual ~S() {}
    };

    int main() {
    __has_virtual_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_abstract(` *型* `)`

   返します**true**型が抽象型である場合。 ネイティブ抽象型の詳細については、次を参照してください。[抽象クラス](../cpp/abstract-classes-cpp.md)します。

   `__is_abstract` はプラットフォーム型でも機能します。 1 つ以上の抽象メンバーを持つ参照型と同様に、1 つ以上のメンバーを持つインターフェイスは抽象型です。 プラットフォームの種類の詳細については、次を参照してください。[抽象](../windows/abstract-cpp-component-extensions.md)します。

    ```cpp
    // is_abstract.cpp
    #include <stdio.h>
    struct S {
    virtual void Test() = 0;
    };

    int main() {
    __is_abstract(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_base_of(` `base` `,` `derived` `)`

   返します**true**最初の型が 2 番目の型の基底クラスの場合は、場合の両方の種類は同じです。

   `__is_base_of` はプラットフォーム型でも機能します。 返されますたとえば、 **true**最初の型がある場合、[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)され、2 番目の型がインターフェイスを実装します。

    ```cpp
    // is_base_of.cpp
    #include <stdio.h>
    struct S {};
    struct T : public S {};

    int main() {
    __is_base_of(S, T) == true ?
    printf("true\n") : printf("false\n");

    __is_base_of(S, S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_class(` *型* `)`

   返します**true**型がネイティブ クラスまたは構造体である場合。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   返します**true**最初の型は、2 番目の型に変換できる場合。

    ```cpp
    #include <stdio.h>
    struct S {};
    struct T : public S {};

    int main() {
    S * s = new S;
    T * t = new T;
    s = t;
    __is_convertible_to(T, S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_delegate(` *型* `)`

   返します**true**場合`type`デリゲートです。 詳細については、次を参照してください。[デリゲート (C +/cli および C++/cli CX)](../windows/delegate-cpp-component-extensions.md)します。

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(` *型* `)`

   返します**true**型のインスタンス データ メンバーがありません。

    ```cpp
    #include <stdio.h>
    struct S {
    int Test() {}
    static int i;
    };
    int main() {
    __is_empty(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_enum(` *型* `)`

   返します**true**型がネイティブ列挙型である場合。

    ```cpp
    // is_enum.cpp
    #include <stdio.h>
    enum E { a, b };

    struct S {
    enum E2 { c, d };
    };

    int main() {
    __is_enum(E) == true ?
    printf("true\n") : printf("false\n");

    __is_enum(S::E2) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_interface_class(` *型* `)`

   返します**true**プラットフォーム インターフェイスが渡された場合。 詳細については、次を参照してください。[インターフェイス クラス](../windows/interface-class-cpp-component-extensions.md)します。

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(` *型* `)`

   返します**true**かどうか、型は、クラスまたはなしのコンス トラクターとの和集合またはプライベートまたはプロテクトの非静的メンバー、基本クラス、および仮想関数はありません。 POD 型の詳細については、C++ 標準のセクション 8.5.1/1、9/4、3.9/10 を参照してください。

   `__is_pod` は基本型の場合に false を返します。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(` *型* `)`

   返します**true**ネイティブ型に仮想関数がある場合。

    ```cpp
    #include <stdio.h>
    struct S {
    virtual void Test(){}
    };

    int main() {
    __is_polymorphic(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_ref_array(` *型* `)`

   返します**true**プラットフォーム配列が渡された場合。 詳細については、次を参照してください。[配列](../windows/arrays-cpp-component-extensions.md)します。

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(` *型* `)`

   返します**true**参照クラスに渡された場合。 ユーザー定義の参照型の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)します。

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(` *型* `)`

   返します**true**プラットフォームまたは封印されたマークされているネイティブ型に渡された場合。 詳細については、次を参照してください。[シール](../windows/sealed-cpp-component-extensions.md)します。

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(` *型* `)`

   返します**true**ガベージ コレクション ヒープへの参照が含まれていない値型が渡された場合。 ユーザー定義の値の種類の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)します。

    ```cpp
    using namespace System;
    ref class R {};
    value struct V {};
    value struct V2 {
    R ^ r;   // not a simnple value type
    };

    int main() {
    Console::WriteLine(__is_simple_value_class(V));
    Console::WriteLine(__is_simple_value_class(V2));
    }
    ```

- `__is_union(` *型* `)`

   返します**true**型が共用体である場合。

    ```cpp
    #include <stdio.h>
    union A {
    int i;
    float f;
    };

    int main() {
    __is_union(A) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_value_class(` *型* `)`

   返します**true**値の型が渡された場合。 ユーザー定義の値の種類の詳細については、次を参照してください。[クラスと構造体](../windows/classes-and-structs-cpp-component-extensions.md)します。

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>Remarks

`__has_finalizer(`*型*`)`このプラットフォームがファイナライザーをサポートしていないために、型の特徴がサポートされていません。

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>Remarks

(この機能のプラットフォーム固有の解説はありません。)

### <a name="requirements"></a>必要条件

コンパイラ オプション: `/clr`

### <a name="examples"></a>使用例

**例**

次のコード例は `/clr` コンパイルのコンパイラ型の特徴を公開するときは、クラス テンプレートを使用する方法を示します。 詳細については、次を参照してください。 [Windows ランタイムおよびマネージ テンプレート](../windows/windows-runtime-and-managed-templates-cpp-component-extensions.md)します。

```cpp
// compiler_type_traits.cpp
// compile with: /clr
using namespace System;

template <class T>
ref struct is_class {
   literal bool value = __is_ref_class(T);
};

ref class R {};

int main () {
   if (is_class<R>::value)
      Console::WriteLine("R is a ref class");
   else
      Console::WriteLine("R is not a ref class");
}
```

```Output
R is a ref class
```

## <a name="see-also"></a>関連項目

[Component Extensions for .NET と UWP](../windows/component-extensions-for-runtime-platforms.md)