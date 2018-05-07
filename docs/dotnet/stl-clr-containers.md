---
title: STL/CLR コンテナー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR, containers
- containers, STL/CLR
ms.assetid: 34ca8031-2041-46b9-aed9-29082d1972ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ce6a2f096e5ee24716fcffd89411ffdf926a59aa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="stlclr-containers"></a>STL/CLR コンテナー
STL/CLR ライブラリ、C++ 標準ライブラリ内にある同じコンテナーが、.NET Framework の管理対象環境内で実行されます。 場合は、C++ 標準ライブラリに慣れて既に STL/CLR、引き続き共通言語ランタイム (CLR) ターゲットをコードのアップグレード中に作成したスキルを使用する最適な方法です。  
  
 このドキュメントでは、コンテナーの要素、要素のコンテナーに挿入できること、およびコンテナー内の要素と、所有権の問題の種類の要件など、STL/CLR 内のコンテナーの概要を示します。 必要に応じて、ネイティブの C++ 標準ライブラリおよび STL/CLR 間の相違点が説明されています。  
  
## <a name="requirements-for-container-elements"></a>コンテナー要素の要件  
 C++ 標準ライブラリのコンテナーに挿入されるすべての要素は、特定のガイドラインに従う必要があります。 詳細については、次を参照してください。 [STL/CLR コンテナー要素の要件](../dotnet/requirements-for-stl-clr-container-elements.md)です。  
  
## <a name="valid-container-elements"></a>有効なコンテナー要素  
 STL/CLR コンテナーには、2 種類の要素のいずれかを保持できます。  
  
-   参照型を処理します。  
  
-   参照型。  
  
-   ボックス化解除された値の型。  
  
 ボックス化された値の型は、任意の STL/CLR コンテナーに挿入できません。  
  
### <a name="handles-to-reference-types"></a>参照型へのハンドル  
 STL/CLR コンテナーには、参照型へのハンドルを挿入できます。 CLR を対象とする C++ では、ハンドルは、ネイティブ C++ でのポインターに似ています。 詳細については、次を参照してください。[オブジェクト演算子 (^) へのハンドル](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)です。  
  
#### <a name="example"></a>例  
 次の例に Employee オブジェクトへのハンドルを挿入する方法を示しています、 [cliext::set](../dotnet/set-stl-clr.md)です。  
  
```  
// cliext_container_valid_reference_handle.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
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
 STL/CLR コンテナーには参照型 (参照型へのハンドルではなく) を挿入することもできます。 ここでの主な違いは、参照型のコンテナーが削除されると、デストラクターがそのコンテナー内のすべての要素に対して呼び出されます。 参照型へのハンドルのコンテナー内のこれらの要素のデストラクターは呼び出せません。  
  
#### <a name="example"></a>例  
 次の例に Employee オブジェクトを挿入する方法を示しています、`cliext::set`です。  
  
```  
// cliext_container_valid_reference.cpp  
// compile with: /clr  
  
#include <cliext/set>  
  
using namespace cliext;  
using namespace System;  
  
ref class Employee  
{  
public:  
    // C++ Standard Library containers might require a public constructor, so it  
    // is a good idea to define one.  
    Employee() :  
        name(nullptr),  
        employeeNumber(0) { }  
  
    // All C++ Standard Library containers require a public copy constructor.  
    Employee(const Employee% orig) :  
        name(orig.name),  
        employeeNumber(orig.employeeNumber) { }  
  
    // All C++ Standard Library containers require a public assignment operator.  
    Employee% operator=(const Employee% orig)  
    {  
        if (this != %orig)  
        {  
            name = orig.name;  
            employeeNumber = orig.employeeNumber;  
        }  
  
        return *this;  
    }  
  
    // All C++ Standard Library containers require a public destructor.  
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
  
### <a name="unboxed-value-types"></a>ボックス化解除された値の型  
 STL/CLR コンテナーに unboxed 値型を挿入することもできます。 Unboxed 値型はされていません。 値の型*手書き*参照型にします。  
  
 値型の要素がある標準の値の型のいずれかなど、 `int`、か、またはユーザー定義の値の型をなどあるできます、`value class`です。 詳細については、次を参照してください[クラスと構造体。](../windows/classes-and-structs-cpp-component-extensions.md)  
  
#### <a name="example"></a>例  
 次の例では、値の型をクラス、従業員をすることで、最初の例を変更します。 この値の型が、挿入、`cliext::set`最初の例と同様です。  
  
```  
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
  
 場合は、コンテナー内に値型へのハンドルを挿入しようとする[コンパイラ エラー C3225](../error-messages/compiler-errors-2/compiler-error-c3225.md)が生成されます。  
  
### <a name="performance-and-memory-implications"></a>パフォーマンスとメモリの問題  
 型または値型のコンテナー要素として参照するハンドルを使用するかどうかを決定するときは、いくつかの要因を考慮する必要があります。 値の型を使用する場合、コンテナーに要素が挿入されるたびに、要素のコピーが作成されたことを注意してください。 小さいオブジェクトは、これは、問題をしないでが挿入されるオブジェクトが大きい場合は、パフォーマンスが低下する可能性があります。 また、値の型を使用している場合、各コンテナーは、要素のコピーを必要があるため、同時に複数のコンテナーに 1 つの要素を格納することもできません。  
  
 代わりに型を参照するハンドルを使用する場合、コンテナーに挿入するときに、要素のコピーを作成する必要はないためにパフォーマンスが向上する可能性があります。 またとは異なり、値型で同じ要素に存在できます複数のコンテナー。 ただし、ハンドルを使用する場合は、する必要があります注意ハンドルが有効であると、それが参照するオブジェクトが削除されていないこと別の場所、プログラムを確認してください。  
  
## <a name="ownership-issues-with-containers"></a>コンテナーの所有権の問題  
 STL/CLR コンテナーは、値のセマンティクスで機能します。 コンテナーに要素を挿入するたびに、その要素のコピーが挿入されます。 参照のようなセマンティクスを取得する場合は、オブジェクト自体ではなく、オブジェクトへのハンドルを挿入することができます。  
  
 クリア テキストの呼び出しまたはハンドル オブジェクトのコンテナーのメソッドを消去すると、ハンドルが参照するオブジェクトがメモリから解放されません。 必要がありますか、明示的にオブジェクトを削除したり、これらのオブジェクトが、マネージ ヒープ上にあるため、オブジェクトが使用されていないことを決定したら、メモリを解放するガベージ コレクターを許可します。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリ リファレンス](../standard-library/cpp-standard-library-reference.md)