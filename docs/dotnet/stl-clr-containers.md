---
description: 詳細については、「STL/CLR コンテナー」を参照してください。
title: STL/CLR コンテナー
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
ms.openlocfilehash: 945533f616abe37763d9963d46d87f02a3c077fa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335339"
---
# <a name="stlclr-containers"></a>STL/CLR コンテナー

STL/CLR ライブラリは、C++ 標準ライブラリと同様のコンテナーで構成されていますが、.NET Framework のマネージ環境内で実行されます。 これは、実際の C++ 標準ライブラリを使用して最新の状態に保たれることはなく、従来のサポートのために維持されます。

このドキュメントでは、コンテナー要素の要件、コンテナーに挿入できる要素の種類、コンテナー内の要素の所有権に関する問題など、STL/CLR のコンテナーの概要について説明します。 必要に応じて、ネイティブ C++ 標準ライブラリと STL/CLR の違いについて説明します。

## <a name="requirements-for-container-elements"></a>コンテナー要素の要件

STL/CLR コンテナーに挿入されるすべての要素は、特定のガイドラインに従う必要があります。 詳細については、「 [STL/CLR コンテナー要素の要件](../dotnet/requirements-for-stl-clr-container-elements.md)」を参照してください。

## <a name="valid-container-elements"></a>有効なコンテナー要素

STL/CLR コンテナーは、次の2種類の要素のいずれかを保持できます。

- 型を参照するハンドル。

- 参照型。

- ボックス化解除した値の型。

任意の STL/CLR コンテナーにボックス化された値型を挿入することはできません。

### <a name="handles-to-reference-types"></a>型を参照するハンドル

参照型へのハンドルを、STL/CLR コンテナーに挿入できます。 CLR を対象とする C++ のハンドルは、ネイティブ C++ のポインターに似ています。 詳細については、「 [オブジェクト演算子へのハンドル (^)](../extensions/handle-to-object-operator-hat-cpp-component-extensions.md)」を参照してください。

#### <a name="example"></a>例

次の例では、Employee オブジェクトへのハンドルを [cliext:: set](../dotnet/set-stl-clr.md)に挿入する方法を示します。

```cpp
// cliext_container_valid_reference_handle.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee^ empl1419 = gcnew Employee();
    empl1419->Name = L"Darin Lockert";
    empl1419->EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee^>^ emplSet = gcnew set<Employee^>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="reference-types"></a>参照型

参照型へのハンドルではなく、参照型を STL/CLR コンテナーに挿入することもできます。 主な違いは、参照型のコンテナーを削除すると、そのコンテナー内のすべての要素に対してデストラクターが呼び出されることです。 型を参照するハンドルのコンテナーでは、これらの要素のデストラクターは呼び出されません。

#### <a name="example"></a>例

次の例は、に Employee オブジェクトを挿入する方法を示して `cliext::set` います。

```cpp
// cliext_container_valid_reference.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

ref class Employee
{
public:
    // STL/CLR containers might require a public constructor, so it
    // is a good idea to define one.
    Employee() :
        name(nullptr),
        employeeNumber(0) { }

    // All STL/CLR containers require a public copy constructor.
    Employee(const Employee% orig) :
        name(orig.name),
        employeeNumber(orig.employeeNumber) { }

    // All STL/CLR containers require a public assignment operator.
    Employee% operator=(const Employee% orig)
    {
        if (this != %orig)
        {
            name = orig.name;
            employeeNumber = orig.employeeNumber;
        }

        return *this;
    }

    // All STL/CLR containers require a public destructor.
    ~Employee() { }

    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee^ empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl->EmployeeNumber, empl->Name);
    }

    return 0;
}
```

### <a name="unboxed-value-types"></a>ボックス化解除した値型

また、ボックス化が解除された値型を STL/CLR コンテナーに挿入することもできます。 ボックス化が解除された値型は、参照型に *ボックス* 化されていない値型です。

値型の要素には、などの標準値型のいずれかを指定することも、 **`int`** ユーザー定義の値型 (など) を指定することもでき **`value class`** ます。 詳細については、「[クラスと構造体](../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください。

#### <a name="example"></a>例

次の例では、Employee クラスを値型にすることによって、最初の例を変更します。 この値型は、最初の例と同様にに挿入され `cliext::set` ます。

```cpp
// cliext_container_valid_valuetype.cpp
// compile with: /clr

#include <cliext/set>

using namespace cliext;
using namespace System;

value class Employee
{
public:
    // Associative containers such as maps and sets
    // require a comparison operator to be defined
    // to determine proper ordering.
    bool operator<(const Employee^ rhs)
    {
        return (employeeNumber < rhs->employeeNumber);
    }

    // The employee's name.
    property String^ Name
    {
        String^ get() { return name; }
        void set(String^ value) { name = value; }
    }

    // The employee's employee number.
    property int EmployeeNumber
    {
        int get() { return employeeNumber; }
        void set(int value) { employeeNumber = value; }
    }

private:
    String^ name;
    int employeeNumber;
};

int main()
{
    // Create a new employee object.
    Employee empl1419;
    empl1419.Name = L"Darin Lockert";
    empl1419.EmployeeNumber = 1419;

    // Add the employee to the set of all employees.
    set<Employee>^ emplSet = gcnew set<Employee>();
    emplSet->insert(empl1419);

    // List all employees of the company.
    for each (Employee empl in emplSet)
    {
        Console::WriteLine("Employee Number {0}: {1}",
            empl.EmployeeNumber, empl.Name);
    }

    return 0;
}
```

値型へのハンドルをコンテナーに挿入しようとすると、 [コンパイラエラー C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md) が生成されます。

### <a name="performance-and-memory-implications"></a>パフォーマンスとメモリの影響

型または値型をコンテナー要素として参照するためにハンドルを使用するかどうかを決定する際には、いくつかの要因を考慮する必要があります。 値型を使用する場合は、要素がコンテナーに挿入されるたびに要素のコピーが作成されることに注意してください。 小さいオブジェクトの場合、これは問題にはなりませんが、挿入されるオブジェクトが大きい場合はパフォーマンスが低下する可能性があります。 また、値型を使用している場合、各コンテナーには要素の独自のコピーが含まれるため、1つの要素を複数のコンテナーに同時に格納することはできません。

代わりに、ハンドルを使用して型を参照する場合、要素をコンテナーに挿入するときにコピーを作成する必要がないため、パフォーマンスが向上する可能性があります。 また、値型とは異なり、同じ要素を複数のコンテナーに存在させることができます。 ただし、ハンドルを使用する場合は、ハンドルが有効であること、およびそのハンドルが参照するオブジェクトがプログラム内の他の場所で削除されていないことを確認する必要があります。

## <a name="ownership-issues-with-containers"></a>コンテナーの所有権に関する問題

STL/CLR 内のコンテナーは、値のセマンティクスで動作します。 コンテナーに要素を挿入するたびに、その要素のコピーが挿入されます。 参照に似たセマンティクスを取得する場合は、オブジェクト自体ではなく、オブジェクトへのハンドルを挿入できます。

ハンドルオブジェクトのコンテナーの clear または erase メソッドを呼び出すと、ハンドルが参照するオブジェクトがメモリから解放されません。 オブジェクトを明示的に削除する必要があります。これらのオブジェクトはマネージヒープに存在するため、オブジェクトが使用されなくなったと判断した後に、ガベージコレクターによるメモリの解放を許可する必要があります。

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリリファレンス](../standard-library/cpp-standard-library-reference.md)
