---
title: '方法: STL/CLR コンテナーを .NET コレクションに変換する'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR Containers [STL/CLR]
- STL/CLR, converting to .NET collections
ms.assetid: 70b2dfd9-869c-4e0f-9a29-b1ee0cb0d107
ms.openlocfilehash: f7539b10ca6c503aede61d19de3d14fb9dcee8be
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545307"
---
# <a name="how-to-convert-from-a-stlclr-container-to-a-net-collection"></a>方法: STL/CLR コンテナーを .NET コレクションに変換する

このトピックでは、STL/CLR コンテナーを同等の .NET コレクションに変換する方法について説明します。 例として、STL/CLR[ベクター](../dotnet/vector-stl-clr.md)を .net <xref:System.Collections.Generic.ICollection%601> に変換する方法と、STL/clr[マップ](../dotnet/map-stl-clr.md)を .net <xref:System.Collections.Generic.IDictionary%602>に変換する方法について説明しますが、この手順はすべてのコレクションとコンテナーに似ています。

### <a name="to-create-a-collection-from-a-container"></a>コンテナーからコレクションを作成するには

1. 次のいずれかの操作を行います。

   - コンテナーの一部を変換するには、 [make_collection](../dotnet/make-collection-stl-clr.md)関数を呼び出し、.net コレクションにコピーする STL/CLR コンテナーの開始反復子と終了反復子を渡します。 このテンプレート関数は、テンプレート引数として STL/CLR 反復子を受け取ります。 最初の例では、このメソッドを示しています。

   - コンテナー全体を変換するには、適切な .NET コレクションインターフェイスまたはインターフェイスコレクションにコンテナーをキャストします。 2番目の例では、このメソッドを示します。

## <a name="example"></a>例

この例では、STL/CLR `vector` を作成し、そこに5つの要素を追加します。 次に、`make_collection` 関数を呼び出して .NET コレクションを作成します。 最後に、新しく作成されたコレクションの内容を表示します。

```cpp
// cliext_convert_vector_to_icollection.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/vector>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::vector<int> primeNumbersCont;
    primeNumbersCont.push_back(2);
    primeNumbersCont.push_back(3);
    primeNumbersCont.push_back(5);
    primeNumbersCont.push_back(7);
    primeNumbersCont.push_back(11);

    System::Collections::Generic::ICollection<int> ^iColl =
        make_collection<cliext::vector<int>::iterator>(
            primeNumbersCont.begin() + 1,
            primeNumbersCont.end() - 1);

    Console::WriteLine("The contents of the System::Collections::Generic::ICollection are:");
    for each (int i in iColl)
    {
        Console::WriteLine(i);
    }
}
```

```Output
The contents of the System::Collections::Generic::ICollection are:
3
5
7
```

## <a name="example"></a>例

この例では、STL/CLR `map` を作成し、そこに5つの要素を追加します。 次に、.NET <xref:System.Collections.Generic.IDictionary%602> を作成し、`map` を直接割り当てます。 最後に、新しく作成されたコレクションの内容を表示します。

```cpp
// cliext_convert_map_to_idictionary.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/map>

using namespace cliext;
using namespace System;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    cliext::map<float, int> ^aMap = gcnew cliext::map<float, int>;
    aMap->insert(cliext::make_pair<float, int>(42.0, 42));
    aMap->insert(cliext::make_pair<float, int>(13.0, 13));
    aMap->insert(cliext::make_pair<float, int>(74.0, 74));
    aMap->insert(cliext::make_pair<float, int>(22.0, 22));
    aMap->insert(cliext::make_pair<float, int>(0.0, 0));

    System::Collections::Generic::IDictionary<float, int> ^iDict = aMap;

    Console::WriteLine("The contents of the IDictionary are:");
    for each (KeyValuePair<float, int> ^kvp in iDict)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", kvp->Key, kvp->Value);
    }
}
```

```Output
The contents of the IDictionary are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>参照

[STL/CLR ライブラリ リファレンス](../dotnet/stl-clr-library-reference.md)<br/>
[方法: .NET コレクションを STL/CLR コンテナーに変換する](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
[range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)
