---
title: STL/CLR ライブラリ リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8cab573b0c1de57ef2629f662108098095b722eb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171823"
---
# <a name="stlclr-library-reference"></a>STL/CLR ライブラリ リファレンス
STL/CLR ライブラリは、C++ と .NET Framework 共通言語ランタイム (CLR) で使用するための C++ 標準ライブラリのサブセットのパッケージ化します。 Stl/clr、すべてのコンテナー、反復子、および管理された環境で、標準ライブラリのアルゴリズムを使用することができます。  
  
 STL/CLR を使用するには  
  
-   ヘッダーを含める、 **cliext**通常と同等の C++ 標準ライブラリではなくサブディレクトリが含まれています。  
  
-   ライブラリ名は、`cliext::` ではなく `std::` で修飾します。  
  
 STL/CLR は、.NET アセンブリでのアセンブリ間シナリオで使用して、ジェネリック型とインターフェイスを公開**Microsoft.VisualC.STLCLR.dll**です。 この DLL は、.NET Framework 3.5 に含まれています。 STL/CLR を使用するアプリケーションを再配布する場合、.NET Framework 3.5 とプロジェクトで使用する他のすべての Visual C++ ライブラリをセットアップ プロジェクトの依存関係セクションに含める必要があります。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [cliext 名前空間](../dotnet/cliext-namespace.md)  
 STL/CLR ライブラリのすべての型を含む名前空間について説明します。  
  
 [STL/CLR コンテナー](../dotnet/stl-clr-containers.md)  
 コンテナー要素を挿入できる要素の種類、所有権の問題の要件も含め、C++ 標準ライブラリ内にあるコンテナーの概要を示します。  
  
 [STL/CLR コンテナー要素の要件](../dotnet/requirements-for-stl-clr-container-elements.md)  
 C++ 標準ライブラリのコンテナーに挿入されるすべての参照型の最小要件について説明します。  
  
 [方法: .NET コレクションを STL/CLR コンテナーに変換する](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)  
 .NET コレクションを STL/CLR コンテナーに変換する方法について説明します。  
  
 [方法: STL/CLR コンテナーを .NET コレクションに変換する](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)  
 STL/CLR コンテナーを .NET コレクションに変換する方法について説明します。  
  
 [方法: アセンブリから STL/CLR コンテナーを公開する](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)  
 C++ アセンブリで記述された複数の STL/CLR コンテナー要素を表示する方法を示します。  
  
 また、このセクションでは STL/CLR の次のコンポーネントについても説明します。  
  
|||  
|-|-|  
|[adapter (STL/CLR)](../dotnet/adapter-stl-clr.md)|[algorithm (STL/CLR)](../dotnet/algorithm-stl-clr.md)|  
|[deque (STL/CLR)](../dotnet/deque-stl-clr.md)|[for each、in](../dotnet/for-each-in.md)|  
|[functional (STL/CLR)](../dotnet/functional-stl-clr.md)|[hash_map (STL/CLR)](../dotnet/hash-map-stl-clr.md)|  
|[hash_multimap (STL/CLR)](../dotnet/hash-multimap-stl-clr.md)|[hash_multiset (STL/CLR)](../dotnet/hash-multiset-stl-clr.md)|  
|[hash_set (STL/CLR)](../dotnet/hash-set-stl-clr.md)|[list (STL/CLR)](../dotnet/list-stl-clr.md)|  
|[map (STL/CLR)](../dotnet/map-stl-clr.md)|[multimap (STL/CLR)](../dotnet/multimap-stl-clr.md)|  
|[multiset (STL/CLR)](../dotnet/multiset-stl-clr.md)|[numeric (STL/CLR)](../dotnet/numeric-stl-clr.md)|  
|[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)|[queue (STL/CLR)](../dotnet/queue-stl-clr.md)|  
|[set (STL/CLR)](../dotnet/set-stl-clr.md)|[stack (STL/CLR)](../dotnet/stack-stl-clr.md)|  
|[utility (STL/CLR)](../dotnet/utility-stl-clr.md)|[vector (STL/CLR)](../dotnet/vector-stl-clr.md)|  
  
## <a name="see-also"></a>関連項目  
 [.NET 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)