---
title: リファレンス (C++ AMP) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8c39528bf3b1e6c9235e4b2daabcd8bbddd0d52f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33685893"
---
# <a name="reference-c-amp"></a>リファレンス (C++ AMP)
このセクションでは、C++ Accelerated Massive Parallelism (C++ AMP) ランタイムに関する参照情報について説明します。  
  
> [!NOTE]
>  C++ 言語の標準では、ライブラリなどの実装用として、アンダースコア (`_`) 文字で始まる識別子の使用が予約されています。 コード内でアンダースコアで始まる名前を使用しないでください。 この規則に従った名前を持つコード要素の動作は永続的に保証されたものではなく、今後のリリースで変更されることがあります。 そのため、このようなコード要素はこのドキュメントから除外されています。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)  
 データ並列ハードウェアでの C++ コードの高速化を有効にするクラスと関数を提供します。  
  
 [Concurrency::direct3d 名前空間](concurrency-direct3d-namespace.md)  
 D3D の相互運用性をサポートする関数を提供します。 AMP コードでの計算に D3D のリソースをシームレスに使用できるようになり、AMP で作成したリソースを D3D コードで使用することができ、冗長な中間コピーを作成する必要がありません。 C++ AMP を使用して、DirectX アプリケーションの計算中心のセクションの処理をインクリメントに加速し、AMP の計算から生成されるデータに対して D3D API を使用することができます。  
  
 [Concurrency::fast_math 名前空間](concurrency-fast-math-namespace.md)  
 `fast_math` 名前空間の関数は C99 に準拠していません。 各関数の各単精度のバージョンのみが用意されています。 これらの関数は DirectX 組み込み関数を使用します。これは、`precise_math` 名前空間の対応する関数よりも高速で、アクセラレータでの倍精度の拡張サポートを必要としませんが、正確さに欠けます。 C99 コードとのソース レベルの互換性のための各関数には 2 つのバージョンがあります。どちらのバージョンも単精度の値を受け取り、返します。  
  
 [Concurrency::graphics 名前空間](concurrency-graphics-namespace.md)  
 グラフィックス プログラミング用に設計された型と関数を提供します。  
  
 [Concurrency::precise_math 名前空間](concurrency-precise-math-namespace.md)  
 `precise_math` 名前空間の関数は C99 に準拠しています。 各関数の単精度バージョンと倍精度のバージョンの両方が含まれます。 単精度関数を含む、これらの関数ではアクセラレータでの倍精度の拡張サポートが必要です。  
  
## <a name="related-sections"></a>関連項目  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C++ AMP は、独立したグラフィックス カードの GPU (graphics processing unit) などの一般的なデータ並列ハードウェアを活用して、C++ コードの実行を高速化します。





