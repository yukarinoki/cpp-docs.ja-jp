---
title: '方法: .NET コレクションを STL/CLR コンテナーに変換する'
ms.date: 11/04/2016
helpviewer_keywords:
- STL/CLR, converting from .NET collections
- STL/CLR Containers [STL/CLR]
ms.assetid: bb927c48-78e8-4150-bd0b-787c651f4a87
ms.openlocfilehash: a7b2ee94f02e663690287ecfa6bc8a7230830a95
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686458"
---
# <a name="how-to-convert-from-a-net-collection-to-a-stlclr-container"></a>方法: .NET コレクションを STL/CLR コンテナーに変換する

このトピックでは、.NET コレクションを同等の STL/CLR コンテナーに変換する方法について説明します。 例として、.NET を <xref:System.Collections.Generic.List%601> stl/clr[ベクター](../dotnet/vector-stl-clr.md)に変換する方法と、.net を stl/clr マップに変換する方法について説明し <xref:System.Collections.Generic.Dictionary%602> ますが、この手順はすべてのコレクションとコンテナーに似ています。 [map](../dotnet/map-stl-clr.md)

### <a name="to-create-a-container-from-a-collection"></a>コレクションからコンテナーを作成するには

1. コレクション全体を変換するには、STL/CLR コンテナーを作成し、そのコレクションをコンストラクターに渡します。

   最初の例では、この手順を示します。

\- または -

1. [Collection_adapter](../dotnet/collection-adapter-stl-clr.md)オブジェクトを作成して、ジェネリック STL/CLR コンテナーを作成します。 このテンプレートクラスは、引数として .NET コレクションインターフェイスを受け取ります。 サポートされているインターフェイスを確認するには、「 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)」を参照してください。

1. .NET コレクションの内容をコンテナーにコピーします。 これは、STL/CLR [アルゴリズム](../dotnet/algorithm-stl-clr.md)を使用するか、.net コレクションを反復処理し、各要素のコピーを STL/clr コンテナーに挿入することによって行うことができます。

   2番目の例では、この手順を示します。

## <a name="examples"></a>例

この例では、ジェネリックを作成 <xref:System.Collections.Generic.List%601> し、そこに5つの要素を追加します。 次に、 `vector` を引数として受け取るコンストラクターを使用してを作成し <xref:System.Collections.Generic.IEnumerable%601> ます。

```cpp
// cliext_convert_list_to_vector.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/vector>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    List<int> ^primeNumbersColl = gcnew List<int>();
    primeNumbersColl->Add(2);
    primeNumbersColl->Add(3);
    primeNumbersColl->Add(5);
    primeNumbersColl->Add(7);
    primeNumbersColl->Add(11);

    cliext::vector<int> ^primeNumbersCont =
        gcnew cliext::vector<int>(primeNumbersColl);

    Console::WriteLine("The contents of the cliext::vector are:");
    cliext::vector<int>::const_iterator it;
    for (it = primeNumbersCont->begin(); it != primeNumbersCont->end(); it++)
    {
        Console::WriteLine(*it);
    }
}
```

```Output
The contents of the cliext::vector are:
2
3
5
7
11
```

この例では、ジェネリックを作成 <xref:System.Collections.Generic.Dictionary%602> し、そこに5つの要素を追加します。 次に、を作成し `collection_adapter` て、を <xref:System.Collections.Generic.Dictionary%602> 単純な STL/CLR コンテナーとしてラップします。 最後に、を作成 `map` し、を反復処理して、の内容 <xref:System.Collections.Generic.Dictionary%602> をにコピーし `map` `collection_adapter` ます。 このプロセスでは、関数を使用して新しいペアを作成 `make_pair` し、新しいペアをに直接挿入し `map` ます。

```cpp
// cliext_convert_dictionary_to_map.cpp
// compile with: /clr

#include <cliext/adapter>
#include <cliext/algorithm>
#include <cliext/map>

using namespace System;
using namespace System::Collections;
using namespace System::Collections::Generic;

int main(array<System::String ^> ^args)
{
    System::Collections::Generic::Dictionary<float, int> ^dict =
        gcnew System::Collections::Generic::Dictionary<float, int>();
    dict->Add(42.0, 42);
    dict->Add(13.0, 13);
    dict->Add(74.0, 74);
    dict->Add(22.0, 22);
    dict->Add(0.0, 0);

    cliext::collection_adapter<System::Collections::Generic::IDictionary<float, int>> dictAdapter(dict);
    cliext::map<float, int> aMap;
    for each (KeyValuePair<float, int> ^kvp in dictAdapter)
    {
        cliext::pair<float, int> aPair = cliext::make_pair(kvp->Key, kvp->Value);
        aMap.insert(aPair);
    }

    Console::WriteLine("The contents of the cliext::map are:");
    cliext::map<float, int>::const_iterator it;
    for (it = aMap.begin(); it != aMap.end(); it++)
    {
        Console::WriteLine("Key: {0:F} Value: {1}", it->first, it->second);
    }
}
```

```Output
The contents of the cliext::map are:
Key: 0.00 Value: 0
Key: 13.00 Value: 13
Key: 22.00 Value: 22
Key: 42.00 Value: 42
Key: 74.00 Value: 74
```

## <a name="see-also"></a>関連項目

[STL/CLR ライブラリリファレンス](../dotnet/stl-clr-library-reference.md)<br/>
[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)<br/>
[方法: STL/CLR コンテナーから .NET コレクションに変換する](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)
