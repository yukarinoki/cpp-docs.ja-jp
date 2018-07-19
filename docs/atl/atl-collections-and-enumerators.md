---
title: ATL のコレクションと列挙子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9837b42148062bdd2c44855c129f085ca47cdec0
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848795"
---
# <a name="atl-collections-and-enumerators"></a>ATL のコレクションと列挙子
A `collection` (生データまたはその他のオブジェクト) のデータ項目のグループにアクセスできるようにするインターフェイスを提供する COM オブジェクトです。 呼ばれるオブジェクトのグループへのアクセスを提供することは、一定の基準に従ってインターフェイスを*コレクション インターフェイス*します。  
  
 コレクション インターフェイスを提供する必要がありますには、少なくとも、`Count`プロパティをコレクション内の項目の数を返す、`Item`をインデックスに基づいてコレクションから項目を返すプロパティと`_NewEnum`を返すプロパティをコレクションの列挙子。 コレクション インターフェイスを提供できます必要に応じて、`Add`と`Remove`項目を挿入したり、コレクションから削除されるようにするメソッドと`Clear`すべての項目を削除する方法。  
  
 `enumerator`はコレクション内の項目を反復処理するインターフェイスを提供する COM オブジェクトです。 列挙子インターフェイスが必要な 4 つのメソッドを使用して、コレクションの要素にシリアル アクセスを提供します。 `Next`、 `Skip`、 `Reset`、および`Clone`します。  
  
 典型的な (ただし、まったく架空の) について学びますの詳細については、列挙子インターフェイスは[として](https://msdn.microsoft.com/library/ms680089.aspx)インターフェイス。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ATL のコレクションと列挙子クラス](../atl/atl-collection-and-enumerator-classes.md)  
 簡単な説明し、コレクションと列挙子を実装するのに役立つ ATL クラスへのリンクを提供します。  
  
 [コレクションと列挙子インターフェイスのデザインの原則](../atl/design-principles-for-collection-and-enumerator-interfaces.md)  
 インターフェイスの種類ごとの背後にあるさまざまな設計原則をについて説明します。  
  
 [C++ 標準ライブラリに基づくコレクションの実装](../atl/implementing-an-stl-based-collection.md)  
 C++ 標準ライブラリに基づくコレクションの実装を説明する詳細な例です。  
  
## <a name="related-sections"></a>関連項目  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。  
  
 [ATLCollections サンプル](../visual-cpp-samples.md)  
 使用方法を示すサンプル`ICollectionOnSTLImpl`と`CComEnumOnSTL`、およびカスタム コピー ポリシー クラスの実装。  
  
## <a name="see-also"></a>関連項目  
 [概念](../atl/active-template-library-atl-concepts.md)

