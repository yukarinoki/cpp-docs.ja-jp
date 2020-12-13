---
description: '詳細については、「方法: アセンブリから STL/CLR コンテナーを公開する」を参照してください。'
title: '方法: アセンブリから STL/CLR コンテナーを公開する'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, cross-assembly issues
ms.assetid: 87efb41b-3db3-4498-a2e7-f3ef8a99f04d
ms.openlocfilehash: a4ed92af956def030c80f8f303f0a7501c4944c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134980"
---
# <a name="how-to-expose-an-stlclr-container-from-an-assembly"></a>方法: アセンブリから STL/CLR コンテナーを公開する

やなどの STL/CLR `list` コンテナー `map` は、テンプレート ref クラスとして実装されます。 C++ テンプレートはコンパイル時にインスタンス化されるため、シグネチャがまったく同じで、アセンブリが異なる2つのテンプレートクラスは、実際には異なる型になります。 つまり、テンプレートクラスは、アセンブリの境界を越えて使用することはできません。

アセンブリ間の共有を可能にするために、STL/CLR コンテナーはジェネリックインターフェイスを実装し <xref:System.Collections.Generic.ICollection%601> ます。 このジェネリックインターフェイスを使用すると、C++、C#、および Visual Basic を含むジェネリックをサポートするすべての言語で、STL/CLR コンテナーにアクセスできます。

このトピックでは、という名前の C++ アセンブリに記述された複数の STL/CLR コンテナーの要素を表示する方法について説明し `StlClrClassLibrary` ます。 にアクセスする2つのアセンブリを示し `StlClrClassLibrary` ます。 最初のアセンブリは C++ で記述され、2番目のアセンブリは C# で記述されています。

両方のアセンブリが C++ で記述されている場合は、その typedef を使用して、コンテナーのジェネリックインターフェイスにアクセスでき `generic_container` ます。 たとえば、型のコンテナーがある場合、 `cliext::vector<int>` そのジェネリックインターフェイスはです `cliext::vector<int>::generic_container` 。 同様に、のように、typedef を使用してジェネリックインターフェイスの反復子を取得することもできます `generic_iterator` `cliext::vector<int>::generic_iterator` 。

これらの typedef は C++ ヘッダーファイルで宣言されているため、他の言語で記述されたアセンブリでは使用できません。 したがって、 `cliext::vector<int>` C# またはその他の .net 言語でのジェネリックインターフェイスにアクセスするには、を使用し `System.Collections.Generic.ICollection<int>` ます。 このコレクションを反復処理するには、ループを使用し `foreach` ます。

次の表は、各 STL/CLR コンテナーが実装するジェネリックインターフェイスを示しています。

|STL/CLR コンテナー|ジェネリックインターフェイス|
|------------------------|-----------------------|
|`deque<T>`|`ICollection<T>`|
|`hash_map<K, V>`|`IDictionary<K, V>`|
|`hash_multimap<K, V>`|`IDictionary<K, V>`|
|`hash_multiset<T>`|`ICollection<T>`|
|`hash_set<T>`|`ICollection<T>`|
|`list<T>`|`ICollection<T>`|
|`map<K, V>`|`IDictionary<K, V>`|
|`multimap<K, V>`|`IDictionary<K, V>`|
|`multiset<T>`|`ICollection<T>`|
|`set<T>`|`ICollection<T>`|
|`vector<T>`|`ICollection<T>`|

> [!NOTE]
> `queue`、 `priority_queue` 、およびコンテナーは `stack` 反復子をサポートしていないため、ジェネリックインターフェイスを実装せず、アセンブリ間でアクセスすることはできません。

## <a name="example-1"></a>例 1

### <a name="description"></a>説明

この例では、プライベート STL/CLR メンバーデータを含む C++ クラスを宣言します。 次に、パブリックメソッドを宣言して、クラスのプライベートコレクションへのアクセスを許可します。 これは2つの異なる方法で行われます。1つは C++ クライアント用で、もう1つは他の .NET クライアント用です。

### <a name="code"></a>コード

```cpp
// StlClrClassLibrary.h
#pragma once

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/stack>
#include <cliext/vector>

using namespace System;
using namespace System::Collections::Generic;
using namespace cliext;

namespace StlClrClassLibrary {

    public ref class StlClrClass
    {
    public:
        StlClrClass();

        // These methods can be called by a C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        deque<wchar_t>::generic_container ^GetDequeCpp();
        list<float>::generic_container ^GetListCpp();
        map<int, String ^>::generic_container ^GetMapCpp();
        set<double>::generic_container ^GetSetCpp();
        vector<int>::generic_container ^GetVectorCpp();

        // These methods can be called by a non-C++ class
        // in another assembly to get access to the
        // private STL/CLR types defined below.
        ICollection<wchar_t> ^GetDequeCs();
        ICollection<float> ^GetListCs();
        IDictionary<int, String ^> ^GetMapCs();
        ICollection<double> ^GetSetCs();
        ICollection<int> ^GetVectorCs();

    private:
        deque<wchar_t> ^aDeque;
        list<float> ^aList;
        map<int, String ^> ^aMap;
        set<double> ^aSet;
        vector<int> ^aVector;
    };
}
```

## <a name="example-2"></a>例 2

### <a name="description"></a>説明

この例では、例1で宣言したクラスを実装します。 このクラスライブラリをクライアントが使用できるようにするには、マニフェストツール **mt.exe** を使用してマニフェストファイルを DLL に埋め込みます。 詳細については、コードのコメントを参照してください。

マニフェストツールとサイドバイサイドアセンブリの詳細については、「 [C/c + + 分離アプリケーションと Side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)」を参照してください。

### <a name="code"></a>コード

```cpp
// StlClrClassLibrary.cpp
// compile with: /clr /LD /link /manifest
// post-build command: (attrib -r StlClrClassLibrary.dll & mt /manifest StlClrClassLibrary.dll.manifest /outputresource:StlClrClassLibrary.dll;#2 & attrib +r StlClrClassLibrary.dll)

#include "StlClrClassLibrary.h"

namespace StlClrClassLibrary
{
    StlClrClass::StlClrClass()
    {
        aDeque = gcnew deque<wchar_t>();
        aDeque->push_back(L'a');
        aDeque->push_back(L'b');

        aList = gcnew list<float>();
        aList->push_back(3.14159f);
        aList->push_back(2.71828f);

        aMap = gcnew map<int, String ^>();
        aMap[0] = "Hello";
        aMap[1] = "World";

        aSet = gcnew set<double>();
        aSet->insert(3.14159);
        aSet->insert(2.71828);

        aVector = gcnew vector<int>();
        aVector->push_back(10);
        aVector->push_back(20);
    }

    deque<wchar_t>::generic_container ^StlClrClass::GetDequeCpp()
    {
        return aDeque;
    }

    list<float>::generic_container ^StlClrClass::GetListCpp()
    {
        return aList;
    }

    map<int, String ^>::generic_container ^StlClrClass::GetMapCpp()
    {
        return aMap;
    }

    set<double>::generic_container ^StlClrClass::GetSetCpp()
    {
        return aSet;
    }

    vector<int>::generic_container ^StlClrClass::GetVectorCpp()
    {
        return aVector;
    }

    ICollection<wchar_t> ^StlClrClass::GetDequeCs()
    {
        return aDeque;
    }

    ICollection<float> ^StlClrClass::GetListCs()
    {
        return aList;
    }

    IDictionary<int, String ^> ^StlClrClass::GetMapCs()
    {
        return aMap;
    }

    ICollection<double> ^StlClrClass::GetSetCs()
    {
        return aSet;
    }

    ICollection<int> ^StlClrClass::GetVectorCs()
    {
        return aVector;
    }
}
```

## <a name="example-3"></a>例 3

### <a name="description"></a>説明

この例では、例1および2で作成したクラスライブラリを使用する C++ クライアントを作成します。 このクライアントは、 `generic_container` STL/CLR コンテナーの typedef を使用して、コンテナーを反復処理し、その内容を表示します。

### <a name="code"></a>コード

```cpp
// CppConsoleApp.cpp
// compile with: /clr /FUStlClrClassLibrary.dll

#include <cliext/deque>
#include <cliext/list>
#include <cliext/map>
#include <cliext/set>
#include <cliext/vector>

using namespace System;
using namespace StlClrClassLibrary;
using namespace cliext;

int main(array<System::String ^> ^args)
{
    StlClrClass theClass;

    Console::WriteLine("cliext::deque contents:");
    deque<wchar_t>::generic_container ^aDeque = theClass.GetDequeCpp();
    for each (wchar_t wc in aDeque)
    {
        Console::WriteLine(wc);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::list contents:");
    list<float>::generic_container ^aList = theClass.GetListCpp();
    for each (float f in aList)
    {
        Console::WriteLine(f);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::map contents:");
    map<int, String ^>::generic_container ^aMap = theClass.GetMapCpp();
    for each (map<int, String ^>::value_type rp in aMap)
    {
        Console::WriteLine("{0} {1}", rp->first, rp->second);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::set contents:");
    set<double>::generic_container ^aSet = theClass.GetSetCpp();
    for each (double d in aSet)
    {
        Console::WriteLine(d);
    }
    Console::WriteLine();

    Console::WriteLine("cliext::vector contents:");
    vector<int>::generic_container ^aVector = theClass.GetVectorCpp();
    for each (int i in aVector)
    {
        Console::WriteLine(i);
    }
    Console::WriteLine();

    return 0;
}
```

### <a name="output"></a>出力

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="example-4"></a>例 4

### <a name="description"></a>説明

この例では、例1および2で作成したクラスライブラリを使用する C# クライアントを作成します。 このクライアントは、 <xref:System.Collections.Generic.ICollection%601> STL/CLR コンテナーのメソッドを使用して、コンテナーを反復処理し、その内容を表示します。

### <a name="code"></a>コード

```csharp
// CsConsoleApp.cs
// compile with: /r:Microsoft.VisualC.STLCLR.dll /r:StlClrClassLibrary.dll /r:System.dll

using System;
using System.Collections.Generic;
using StlClrClassLibrary;
using cliext;

namespace CsConsoleApp
{
    class Program
    {
        static int Main(string[] args)
        {
            StlClrClass theClass = new StlClrClass();

            Console.WriteLine("cliext::deque contents:");
            ICollection<char> iCollChar = theClass.GetDequeCs();
            foreach (char c in iCollChar)
            {
                Console.WriteLine(c);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::list contents:");
            ICollection<float> iCollFloat = theClass.GetListCs();
            foreach (float f in iCollFloat)
            {
                Console.WriteLine(f);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::map contents:");
            IDictionary<int, string> iDict = theClass.GetMapCs();
            foreach (KeyValuePair<int, string> kvp in iDict)
            {
                Console.WriteLine("{0} {1}", kvp.Key, kvp.Value);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::set contents:");
            ICollection<double> iCollDouble = theClass.GetSetCs();
            foreach (double d in iCollDouble)
            {
                Console.WriteLine(d);
            }
            Console.WriteLine();

            Console.WriteLine("cliext::vector contents:");
            ICollection<int> iCollInt = theClass.GetVectorCs();
            foreach (int i in iCollInt)
            {
                Console.WriteLine(i);
            }
            Console.WriteLine();

            return 0;
        }
    }
}
```

### <a name="output"></a>出力

```Output
cliext::deque contents:
a
b

cliext::list contents:
3.14159
2.71828

cliext::map contents:
0 Hello
1 World

cliext::set contents:
2.71828
3.14159

cliext::vector contents:
10
20
```

## <a name="see-also"></a>関連項目

[STL/CLR ライブラリリファレンス](../dotnet/stl-clr-library-reference.md)
