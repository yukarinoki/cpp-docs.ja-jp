---
description: 詳細については、「ATL コレクションと列挙子」を参照してください。
title: ATL のコレクションと列挙子
ms.date: 11/04/2016
helpviewer_keywords:
- enumerator interfaces
- collections, ATL classes
- enumerators, ATL classes
- collection interfaces
ms.assetid: b2d37119-3ab2-4e0a-b65b-f377f07e4098
ms.openlocfilehash: 92e9ab3df52219812d72ae5cb811f57a3ecf4fad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166006"
---
# <a name="atl-collections-and-enumerators"></a>ATL のコレクションと列挙子

は、 `collection` データ項目のグループ (生データまたはその他のオブジェクト) へのアクセスを可能にするインターフェイスを提供する COM オブジェクトです。 オブジェクトのグループへのアクセスを提供するための標準に従うインターフェイスを、 *コレクションインターフェイス* と呼びます。

コレクションインターフェイスは、少なくともコレクション内の項目数を `Count` 返すプロパティ、 `Item` インデックスに基づいてコレクションから項目を返すプロパティ、および `_NewEnum` コレクションの列挙子を返すプロパティを提供する必要があります。 必要に応じて、コレクションインターフェイスは、 `Add` `Remove` コレクションへの項目の挿入または削除を許可するメソッドとメソッド、および `Clear` すべての項目を削除するメソッドを提供できます。

`enumerator`は、コレクション内の項目を反復処理するためのインターフェイスを提供する COM オブジェクトです。 列挙子インターフェイスは、、、 `Next` `Skip` `Reset` 、およびの4つの必須メソッドを使用して、コレクションの要素へのシリアルアクセスを提供し `Clone` ます。

列挙子インターフェイスの詳細については、 [IEnumString](/windows/win32/api/objidl/nn-objidl-ienumstring) インターフェイスなどの参照コンテンツを参照してください。

## <a name="in-this-section"></a>このセクションの内容

[ATL コレクションと列挙子クラス](../atl/atl-collection-and-enumerator-classes.md)<br/>
コレクションと列挙子の実装に役立つ ATL クラスへのリンクを簡単に説明し、提供します。

[コレクションと列挙子のインターフェイスの設計原則](../atl/design-principles-for-collection-and-enumerator-interfaces.md)<br/>
各種類のインターフェイスの背後にあるさまざまな設計原則について説明します。

[C++ 標準 Library-Based コレクションの実装](../atl/implementing-an-stl-based-collection.md)<br/>
C++ 標準ライブラリベースのコレクションの実装について説明する拡張例です。

## <a name="related-sections"></a>関連項目

[ATL](../atl/active-template-library-atl-concepts.md)<br/>
Active Template Library を使用してプログラミングする方法に関する概念説明のトピックへのリンクを提供します。

[ATLCollections サンプル](../overview/visual-cpp-samples.md)<br/>
との使用方法、 `ICollectionOnSTLImpl` `CComEnumOnSTL` およびカスタムコピーポリシークラスの実装方法を示すサンプル。

## <a name="see-also"></a>関連項目

[概念](../atl/active-template-library-atl-concepts.md)
