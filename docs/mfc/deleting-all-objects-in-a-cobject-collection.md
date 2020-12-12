---
description: 詳細については、「CObject コレクション内のすべてのオブジェクトの削除」を参照してください。
title: CObject コレクションの全オブジェクトの削除
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
ms.openlocfilehash: 674253d06925bdf29e5606692a73911878f6c393
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291013"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject コレクションの全オブジェクトの削除

この記事では、コレクションオブジェクト自体を削除せずに、コレクション内のすべてのオブジェクトを削除する方法について説明します。

のコレクション (またはから派生したオブジェクト) 内のすべてのオブジェクトを削除するには、 `CObject` `CObject` 「 [コレクションのすべてのメンバーにアクセス](accessing-all-members-of-a-collection.md) する」の記事で説明されているイテレーション手法のいずれかを使用して、各オブジェクトを順に削除します。

> [!CAUTION]
> コレクション内のオブジェクトは共有できます。 つまり、コレクションはオブジェクトへのポインターを保持しますが、プログラムの他の部分が同じオブジェクトへのポインターを持つ場合もあります。 オブジェクトを削除しないように注意する必要があります。この場合、すべての部分がオブジェクトの使用を終了するまで、そのオブジェクトが共有されます。

この記事では、でオブジェクトを削除する方法について説明します。

- [リスト](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [配列](#_core_to_delete_all_elements_in_an_array)

- [マップ](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a> CObject へのポインターのリストに含まれるすべてのオブジェクトを削除するには

1. およびを使用し `GetHeadPosition` `GetNext` て、リストを反復処理します。

1. **`delete`** 反復処理で発生した各オブジェクトを削除するには、演算子を使用します。

1. 関数を呼び出して、 `RemoveAll` これらの要素に関連付けられているオブジェクトが削除された後、リストからすべての要素を削除します。

次の例は、オブジェクトのリストからすべてのオブジェクトを削除する方法を示して `CPerson` います。 リスト内の各オブジェクトは、 `CPerson` ヒープに最初に割り当てられたオブジェクトへのポインターです。

[!code-cpp[NVC_MFCCollections#17](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

最後の関数呼び出しは、リスト `RemoveAll` からすべての要素を削除するリストメンバー関数です。 このメンバー関数は、 `RemoveAt` 1 つの要素を削除します。

要素のオブジェクトを削除し、要素自体を削除することの違いに注意してください。 リストから要素を削除すると、そのリストのオブジェクトへの参照だけが削除されます。 オブジェクトはまだメモリに存在します。 オブジェクトを削除すると、そのオブジェクトは存在しなくなり、メモリが解放されます。 そのため、要素のオブジェクトが削除された直後に要素を削除し、リストが存在しないオブジェクトにアクセスしようとしないようにすることが重要です。

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a> 配列内のすべての要素を削除するには

1. `GetSize`および整数のインデックス値を使用して、配列を反復処理します。

1. **`delete`** 反復処理で見つかった各要素を削除するには、演算子を使用します。

1. 関数を呼び出して、 `RemoveAll` 削除された配列からすべての要素を削除します。

   配列のすべての要素を削除するコードは次のとおりです。

   [!code-cpp[NVC_MFCCollections#18](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

上記のリストの例と同様に、を呼び出して、 `RemoveAll` 配列内のすべての要素を削除することも、個々の要素を削除することもでき `RemoveAt` ます。

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a> マップ内のすべての要素を削除するには

1. およびを使用し `GetStartPosition` `GetNextAssoc` て、配列を反復処理します。

1. **`delete`** 反復処理で見つかった各マップ要素のキーまたは値を削除するには、演算子を使用します。

1. 関数を呼び出して、 `RemoveAll` 削除されたすべての要素をマップから削除します。

   コレクションのすべての要素を削除するコードを次に示し `CMap` ます。 マップ内の各要素には、キーとしての文字列と、 `CPerson` 値としてのオブジェクト (から派生) があり `CObject` ます。

   [!code-cpp[NVC_MFCCollections#19](codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

を呼び出して、マップ内のすべての要素を削除することも、指定した `RemoveAll` `RemoveKey` キーを持つ個々の要素を削除することもできます。

## <a name="see-also"></a>関連項目

[コレクションのすべてのメンバーへのアクセス](accessing-all-members-of-a-collection.md)
