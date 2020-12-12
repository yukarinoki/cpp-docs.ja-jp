---
description: '詳細情報: 型の特徴のコンパイラサポート (C++/CLI および C++/CX)'
title: 型の特徴のコンパイラ サポート (C++/CLI および C++/CX)
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
ms.openlocfilehash: ec9efe1305a844779b4848cbae155d2946488d11
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176926"
---
# <a name="compiler-support-for-type-traits-ccli-and-ccx"></a>型の特徴のコンパイラ サポート (C++/CLI および C++/CX)

Microsoft C++ コンパイラでは、C++/CLI と C++/CX の拡張機能に対して、コンパイル時に型のさまざまな特性を示す "*型の特徴*" をサポートしています。

## <a name="all-runtimes"></a>すべてのランタイム

### <a name="remarks"></a>解説

型の特徴は、ライブラリを記述するプログラマにとって特に便利です。

次の一覧に、コンパイラによってサポートされる型の特徴が含まれています。 型 **`false`** の特徴の名前で指定された条件が満たされない場合は、すべての型の特徴が返されます。

(次の一覧のコード例は、C++/CLI のみで記述されています。 ただし、特に明記されていない限り、対応する型の特徴は C++/CX でもサポートされています。 "プラットフォーム型" という用語は、Windows Runtime の型または共通言語ランタイムの型を示します。)

- `__has_assign(`*型*`)`

   **`true`** プラットフォームまたはネイティブ型にコピー代入演算子がある場合は、を返します。

    ```cpp
    ref struct R {
    void operator=(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_assign(R));
    }
    ```

- `__has_copy(`*型*`)`

   **`true`** プラットフォームまたはネイティブ型にコピーコンストラクターがある場合は、を返します。

    ```cpp
    ref struct R {
    R(R% r) {}
    };

    int main() {
    System::Console::WriteLine(__has_copy(R));
    }
    ```

- `__has_finalizer(`*型*`)`

   (C++/CX ではサポートされていません)。 **`true`** CLR 型にファイナライザーがある場合は、を返します。 詳細については、「 [方法: クラスと構造体を定義および使用する (C++/cli)」の「デストラクターとファイナライザー](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers) 」を参照してください。

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

- `__has_nothrow_assign(`*型*`)`

   **`true`** コピー代入演算子に空の例外指定がある場合は、を返します。

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

- `__has_nothrow_constructor(`*型*`)`

   **`true`** 既定のコンストラクターに空の例外指定がある場合は、を返します。

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

- `__has_nothrow_copy(`*型*`)`

   **`true`** コピーコンストラクターに空の例外指定がある場合は、を返します。

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

- `__has_trivial_assign(`*型*`)`

   **`true`** 型に自明なコンパイラで生成された代入演算子がある場合は、を返します。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_assign(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_constructor(`*型*`)`

   **`true`** 型に自明なコンパイラで生成されたコンストラクターがある場合は、を返します。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_constructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_copy(`*型*`)`

   **`true`** 型に自明なコンパイラで生成されたコピーコンストラクターがある場合は、を返します。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_copy(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_trivial_destructor(`*型*`)`

   **`true`** 型に自明なコンパイラで生成されたデストラクターがある場合は、を返します。

    ``` cpp
    // has_trivial_destructor.cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __has_trivial_destructor(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__has_user_destructor(`*型*`)`

   **`true`** プラットフォームまたはネイティブ型にユーザーが宣言したデストラクターがある場合は、を返します。

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

- `__has_virtual_destructor(`*型*`)`

   **`true`** 型に仮想デストラクターがある場合は、を返します。

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

- `__is_abstract(`*型*`)`

   **`true`** 型が抽象型である場合はを返します。 ネイティブ抽象型の詳細については、「[抽象クラス](../cpp/abstract-classes-cpp.md)」を参照してください。

   `__is_abstract` はプラットフォーム型でも機能します。 1 つ以上の抽象メンバーを持つ参照型と同様に、1 つ以上のメンバーを持つインターフェイスは抽象型です。 抽象プラットフォーム型の詳細については、「[abstract](abstract-cpp-component-extensions.md)」を参照してください。

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

   **`true`** 最初の型が2番目の型の基本クラスであり、両方の型が同じである場合は、を返します。

   `__is_base_of` はプラットフォーム型でも機能します。 たとえば、 **`true`** 最初の型が [インターフェイスクラス](interface-class-cpp-component-extensions.md) で、2番目の型がインターフェイスを実装している場合は、が返されます。

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

- `__is_class(`*型*`)`

   **`true`** 型がネイティブクラスまたは構造体である場合は、を返します。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_class(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_convertible_to(` `from` `,`  `to` `)`

   **`true`** 最初の型を2番目の型に変換できる場合はを返します。

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

- `__is_delegate(`*型*`)`

   **`true`** がデリゲートである場合は、を返し `type` ます。 デリゲートの詳細については、「[delegate (C++/CLI and C++/CX)](delegate-cpp-component-extensions.md)」を参照してください。

    ```cpp
    delegate void MyDel();
    int main() {
    System::Console::WriteLine(__is_delegate(MyDel));
    }
    ```

- `__is_empty(`*型*`)`

   **`true`** 型にインスタンスデータメンバーがない場合は、を返します。

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

- `__is_enum(`*型*`)`

   **`true`** 型がネイティブ列挙型である場合はを返します。

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

- `__is_interface_class(`*型*`)`

   **`true`** プラットフォームインターフェイスが渡された場合は、を返します。 詳細については、「[インターフェイス クラス](interface-class-cpp-component-extensions.md)」を参照してください。

    ```cpp
    // is_interface_class.cpp

    using namespace System;
    interface class I {};
    int main() {
    Console::WriteLine(__is_interface_class(I));
    }
    ```

- `__is_pod(`*型*`)`

   **`true`** 型がコンストラクターのないクラスまたは共用体、プライベートまたは保護された非静的メンバー、基底クラス、および仮想関数がない場合は、を返します。 POD 型の詳細については、C++ 標準のセクション 8.5.1/1、9/4、3.9/10 を参照してください。

   `__is_pod` は基本型の場合に false を返します。

    ```cpp
    #include <stdio.h>
    struct S {};

    int main() {
    __is_pod(S) == true ?
    printf("true\n") : printf("false\n");
    }
    ```

- `__is_polymorphic(`*型*`)`

   **`true`** ネイティブ型に仮想関数がある場合は、を返します。

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

- `__is_ref_array(`*型*`)`

   **`true`** プラットフォーム配列が渡された場合は、を返します。 詳細については、「[配列](arrays-cpp-component-extensions.md)」を参照してください。

    ```cpp
    using namespace System;
    int main() {
    array<int>^ x = gcnew array<int>(10);
    Console::WriteLine(__is_ref_array(array<int>));
    }
    ```

- `__is_ref_class(`*型*`)`

   **`true`** 参照クラスが渡された場合は、を返します。 ユーザー定義の参照型の詳細については、[クラスと構造体](classes-and-structs-cpp-component-extensions.md)に関する記事を参照してください。

    ```cpp
    using namespace System;
    ref class R {};
    int main() {
    Console::WriteLine(__is_ref_class(Buffer));
    Console::WriteLine(__is_ref_class(R));
    }
    ```

- `__is_sealed(`*型*`)`

   **`true`** Sealed とマークされたプラットフォームまたはネイティブ型が渡された場合は、を返します。 詳細については、「[sealed](sealed-cpp-component-extensions.md)」を参照してください。

    ```cpp
    ref class R sealed{};
    int main() {
    System::Console::WriteLine(__is_sealed(R));
    }
    ```

- `__is_simple_value_class(`*型*`)`

   **`true`** ガベージコレクションヒープへの参照を含まない値型が渡された場合は、を返します。 ユーザー定義の値型の詳細については、[クラスと構造体](classes-and-structs-cpp-component-extensions.md)に関する記事を参照してください。

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

- `__is_union(`*型*`)`

   **`true`** 型が共用体の場合はを返します。

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

- `__is_value_class(`*型*`)`

   **`true`** 値型が渡された場合はを返します。 ユーザー定義の値型の詳細については、[クラスと構造体](classes-and-structs-cpp-component-extensions.md)に関する記事を参照してください。

    ```cpp
    value struct V {};

    int main() {
    System::Console::WriteLine(__is_value_class(V));
    }
    ```

## <a name="windows-runtime"></a>Windows ランタイム

### <a name="remarks"></a>解説

`__has_finalizer(`*型* の `)` 特徴はサポートされていません。このプラットフォームではファイナライザーがサポートされていません。

### <a name="requirements"></a>要件

コンパイラ オプション: `/ZW`

## <a name="common-language-runtime"></a>共通言語ランタイム

### <a name="remarks"></a>解説

(この機能のプラットフォーム固有の解説はありません。)

### <a name="requirements"></a>要件

コンパイラ オプション: `/clr`

### <a name="examples"></a>例

**例**

次のコード例は `/clr` コンパイルのコンパイラ型の特徴を公開するときは、クラス テンプレートを使用する方法を示します。 詳細については、「[Windows ランタイムおよびマネージド テンプレート (C++/CLI および C++/CX)](windows-runtime-and-managed-templates-cpp-component-extensions.md)」を参照してください。

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

[.NET および UWP 用のコンポーネントの拡張機能](component-extensions-for-runtime-platforms.md)
