---
title: STL/CLR ライブラリ リファレンス
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: e6804dab814eca4ecc5fd23c74cbbb21eac3be77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839700"
---
# <a name="stlclr-library-reference"></a>STL/CLR ライブラリ リファレンス

STL/CLR ライブラリには、c++ および .NET Framework 共通言語ランタイム (CLR) と共に使用するための C++ 標準ライブラリコンテナーと同様のインターフェイスが用意されています。 STL/CLR は、C++ 標準ライブラリの Microsoft 実装とは完全に分離されています。 STL/CLR は従来のサポートのために保持されていますが、C++ 標準では最新の状態に保たれていません。 可能な限り、STL/CLR の代わりにネイティブ [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md) コンテナーを使用することを強くお勧めします。

STL/CLR を使用するには

- 通常の C++ 標準ライブラリに相当するものではなく、 **cliext** インクルードサブディレクトリのヘッダーをインクルードします。

- ライブラリ名は、`cliext::` ではなく `std::` で修飾します。

STL/CLR ライブラリには、C++ および .NET Framework 共通言語ランタイム (CLR) と共に使用するための STL に似たインターフェイスが用意されています。 このライブラリは従来のサポートのために保持されていますが、C++ 標準では最新の状態に保たれていません。 STL/CLR ではなく、ネイティブ [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md) コンテナーを使用することを強くお勧めします。

## <a name="in-this-section"></a>このセクションの内容

[cliext 名前空間](../dotnet/cliext-namespace.md)<br/>
STL/CLR ライブラリのすべての型を含む名前空間について説明します。

[STL/CLR コンテナー](../dotnet/stl-clr-containers.md)<br/>
コンテナー要素の要件、挿入できる要素の種類、所有権の問題など、C++ 標準ライブラリにあるコンテナーの概要について説明します。

[STL/CLR コンテナー要素の要件](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
C++ 標準ライブラリコンテナーに挿入されるすべての参照型の最小要件について説明します。

[方法: .NET コレクションを STL/CLR コンテナーに変換する](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
.NET コレクションを STL/CLR コンテナーに変換する方法について説明します。

[方法: STL/CLR コンテナーから .NET コレクションに変換する](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
STL/CLR コンテナーを .NET コレクションに変換する方法について説明します。

[方法: アセンブリから STL/CLR コンテナーを公開する](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
C++ アセンブリで記述された複数の STL/CLR コンテナー要素を表示する方法を示します。

また、このセクションでは STL/CLR の次のコンポーネントについても説明します。

:::row:::
   :::column span="":::
      [`adapter` (STL/CLR)](../dotnet/adapter-stl-clr.md)\
      [`algorithm` (STL/CLR)](../dotnet/algorithm-stl-clr.md)\
      [`deque` (STL/CLR)](../dotnet/deque-stl-clr.md)\
      [`for each`, `in`](../dotnet/for-each-in.md)\
      [`functional` (STL/CLR)](../dotnet/functional-stl-clr.md)\
      [`hash_map` (STL/CLR)](../dotnet/hash-map-stl-clr.md)\
      [`hash_multimap` (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)\
      [`hash_multiset` (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)\
      [`hash_set` (STL/CLR)](../dotnet/hash-set-stl-clr.md)\
      [`list` (STL/CLR)](../dotnet/list-stl-clr.md)\
   :::column-end:::
   :::column span="":::
      [`map` (STL/CLR)](../dotnet/map-stl-clr.md)\
      [`multimap` (STL/CLR)](../dotnet/multimap-stl-clr.md)\
      [`multiset` (STL/CLR)](../dotnet/multiset-stl-clr.md)\
      [`numeric` (STL/CLR)](../dotnet/numeric-stl-clr.md)\
      [`priority_queue` (STL/CLR)](../dotnet/priority-queue-stl-clr.md)\
      [`queue` (STL/CLR)](../dotnet/queue-stl-clr.md)\
      [`set` (STL/CLR)](../dotnet/set-stl-clr.md)\
      [`stack` (STL/CLR)](../dotnet/stack-stl-clr.md)\
      [`utility` (STL/CLR)](../dotnet/utility-stl-clr.md)\
      [`vector` (STL/CLR)](../dotnet/vector-stl-clr.md)\
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>関連項目

[C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)
