---
title: コレクションの全メンバーへのアクセス
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, collections
- enumerations [MFC]
- enumerating collections [MFC]
- collections [MFC], accessing
- collection classes [MFC]
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
- ', '
ms.assetid: 7bbae518-062e-4393-81f9-b22abd2e5f59
ms.openlocfilehash: 0d8b5491ee5321171ef358308f3c1548e43953d3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616496"
---
# <a name="accessing-all-members-of-a-collection"></a>コレクションの全メンバーへのアクセス

MFC の配列コレクション クラスでは、テンプレート クラスでも非テンプレート クラスでも、インデックスを使って要素にアクセスします。 MFC のリスト コレクション クラスおよびマップ コレクション クラスでは、テンプレート クラスでも非テンプレート クラスでも、 **POSITION** 型のインジケーターを使ってコレクション内の位置を指定します。 そのコレクションの 1 つ以上のメンバーにアクセスするには、まず、ポジション インジケーターを初期化し、次にそのポジションを繰り返しコレクションに渡して、次の要素の位置を問い合わせます。 コレクションは、反復の進行に関する状態情報を保持していません。 この情報は、ポジション インジケーターで保持されます。 ただし、特定のポジションについては、コレクションはそのポジションの次の要素を返します。

次に、MFC が提供する代表的な 3 種類のコレクションに対する反復処理について説明します。

- [配列の反復処理](#_core_to_iterate_an_array)

- [リストの反復処理](#_core_to_iterate_a_list)

- [マップの反復処理](#_core_to_iterate_a_map)

### <a name="to-iterate-an-array"></a><a name="_core_to_iterate_an_array"></a>配列を反復処理するには

1. 連続したインデックス番号を使用して、 `GetAt` メンバー関数を呼び出します。

   [!code-cpp[NVC_MFCCollections#12](codesnippet/cpp/accessing-all-members-of-a-collection_1.cpp)]

   この例では、 `CPerson` オブジェクトへのポインターを格納する型付きポインター配列を使っています。 この配列は、定義済みの非テンプレート クラスである `CObArray`クラスから派生しています。 `GetAt` は `CPerson` オブジェクトへのポインターを返します。 型付きポインター コレクション クラスの場合は、配列でもリストでも、最初のパラメーターで基本クラスを指定し、2 番目のパラメーターで格納するデータの型を指定します。

   `CTypedPtrArray`また、クラスは **[]** 演算子をオーバーロードして、配列の要素にアクセスするために通常の配列添字構文を使用できるようにします。 上記**の for**ループの本体のステートメントの代わりに、

   [!code-cpp[NVC_MFCCollections#13](codesnippet/cpp/accessing-all-members-of-a-collection_2.cpp)]

   この演算子は **const** バージョンと非**const** バージョンがあります。 **const** バージョンは、 **const** の配列に対して呼び出され、代入ステートメントの右側にのみ表示されます。

### <a name="to-iterate-a-list"></a><a name="_core_to_iterate_a_list"></a>リストを反復処理するには

1. リスト内の項目を順に処理するには、 `GetHeadPosition` メンバー関数と `GetNext` メンバー関数を使用します。

   [!code-cpp[NVC_MFCCollections#14](codesnippet/cpp/accessing-all-members-of-a-collection_3.cpp)]

   この例では、型付きポインター リストを使用して、 `CPerson` オブジェクトへのポインターを格納します。 リストの宣言は、「 [配列を反復処理するには](#_core_to_iterate_an_array) 」の配列に対する宣言に似ていますが、 `CObList`クラスから派生しています。 `GetNext` は `CPerson` オブジェクトへのポインターを返します。

### <a name="to-iterate-a-map"></a><a name="_core_to_iterate_a_map"></a>マップを反復処理するには

1. `GetStartPosition` を使用してマップの先頭位置に移動し、 `GetNextAssoc` を使用して、次のキーと値をマップから順次取得します。次に例を示します。

   [!code-cpp[NVC_MFCCollections#15](codesnippet/cpp/accessing-all-members-of-a-collection_4.cpp)]

   この例では、型付きポインター コレクションではなく、簡単なマップ テンプレートを使用しています。このテンプレートは、 `CString` 型のキーを使用し、 `CPerson` オブジェクトへのポインターを格納します。 `GetNextAssoc`などのアクセス関数を使用すると、 `CPerson` オブジェクトへのポインターが返されます。 非テンプレート マップ コレクションを使用すると、返された `CObject` ポインターを、 `CPerson`へのポインターにキャストする必要があります。

    > [!NOTE]
    >  非テンプレート マップの場合、コンパイラには、 `CObject` の最後のパラメーターとして `GetNextAssoc`ポインターへの参照が必要です。 入力時には、ポインターをその型にキャストする必要があります。次に例を示します。

   テンプレートを使用すると、よりシンプルなソリューションが実現し、タイプ セーフもさらに確実になります。 テンプレートを使用しないコードは、次のようにより複雑になります。

   [!code-cpp[NVC_MFCCollections#16](codesnippet/cpp/accessing-all-members-of-a-collection_5.cpp)]

詳細については、「 [CObject コレクションの全オブジェクトの削除](deleting-all-objects-in-a-cobject-collection.md)」を参照してください。

## <a name="see-also"></a>関連項目

[コレクション](collections.md)
