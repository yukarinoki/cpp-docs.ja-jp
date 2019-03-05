---
title: ATL のコレクションと列挙子
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 690fc023b72b2606efc190aceb7c266a35a4ebb4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283049"
---
# <a name="atl-collections-and-enumerators"></a>ATL のコレクションと列挙子

A `collection` (生データまたはその他のオブジェクト) のデータ項目のグループにアクセスできるようにするインターフェイスを提供する COM オブジェクトです。 呼ばれるオブジェクトのグループへのアクセスを提供することは、一定の基準に従ってインターフェイスを*コレクション インターフェイス*します。

コレクション インターフェイスを提供する必要がありますには、少なくとも、`Count`プロパティをコレクション内の項目の数を返す、`Item`をインデックスに基づいてコレクションから項目を返すプロパティと`_NewEnum`を返すプロパティをコレクションの列挙子。 コレクション インターフェイスを提供できます必要に応じて、`Add`と`Remove`項目を挿入したり、コレクションから削除されるようにするメソッドと`Clear`すべての項目を削除する方法。

`enumerator`はコレクション内の項目を反復処理するインターフェイスを提供する COM オブジェクトです。 列挙子インターフェイスが必要な 4 つのメソッドを使用して、コレクションの要素にシリアル アクセスを提供します。 `Next`、 `Skip`、 `Reset`、および`Clone`します。

詳細については、読み取り、列挙子インターフェイスのリファレンス コンテンツを学習できます[IEnumString](/windows/desktop/api/objidl/nn-objidl-ienumstring)インターフェイス。

## <a name="in-this-section"></a>このセクションの内容

[ATL のコレクションと列挙子クラス](../atl/atl-collection-and-enumerator-classes.md)<br/>
簡単な説明し、コレクションと列挙子を実装するのに役立つ ATL クラスへのリンクを提供します。

[コレクションと列挙子インターフェイスのデザインの原則](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
インターフェイスの種類ごとの背後にあるさまざまな設計原則をについて説明します。

[C++ 標準ライブラリに基づくコレクションの実装](../atl/implementing-an-stl-based-collection.md)<br/>
C++ 標準ライブラリに基づくコレクションの実装を説明する詳細な例です。

## <a name="related-sections"></a>関連項目

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

[ATLCollections サンプル](../visual-cpp-samples.md)<br/>
使用方法を示すサンプル`ICollectionOnSTLImpl`と`CComEnumOnSTL`、およびカスタム コピー ポリシー クラスの実装。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
