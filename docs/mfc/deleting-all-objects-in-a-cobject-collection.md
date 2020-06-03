---
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
ms.openlocfilehash: 303b8a566a730c5abd06d51fb7977174e19a6435
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370535"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject コレクションの全オブジェクトの削除

この資料では、コレクション内のすべてのオブジェクトを削除する方法について説明します (コレクション オブジェクト自体を削除せずに)。

s (または派生`CObject``CObject`したオブジェクト) のコレクション内のすべてのオブジェクトを削除するには、「コレクションのすべての[メンバーにアクセスする](../mfc/accessing-all-members-of-a-collection.md)」で説明されている反復テクニックのいずれかを使用して各オブジェクトを削除します。

> [!CAUTION]
> コレクション内のオブジェクトは共有できます。 つまり、コレクションはオブジェクトへのポインターを保持しますが、プログラムの他の部分も同じオブジェクトへのポインターを持つ場合があります。 すべてのパーツがオブジェクトの使用を終了するまで、共有されているオブジェクトを削除しないように注意する必要があります。

この記事では、次のオブジェクトを削除する方法について説明します。

- [リスト](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)

- [配列](#_core_to_delete_all_elements_in_an_array)

- [地図](#_core_to_delete_all_elements_in_a_map)

#### <a name="to-delete-all-objects-in-a-list-of-pointers-to-cobject"></a><a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>CObject へのポインタのリスト内のすべてのオブジェクトを削除するには

1. を`GetHeadPosition`使用`GetNext`して、リストを反復処理します。

1. **delete**演算子を使用して、反復処理で検出された各オブジェクトを削除します。

1. この関数`RemoveAll`を呼び出して、その要素に関連付けられたオブジェクトが削除された後で、リストからすべての要素を削除します。

オブジェクトのリストからすべてのオブジェクトを削除する方法を次の`CPerson`例に示します。 リスト内の各オブジェクトは、最初に`CPerson`ヒープに割り当てられたオブジェクトへのポインターです。

[!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]

最後の関数呼び`RemoveAll`出しは、リストからすべての要素を削除するリスト メンバー関数です。 メンバー関数`RemoveAt`は、1 つの要素を削除します。

要素のオブジェクトを削除することと、要素自体を削除する場合の違いに注意してください。 リストから要素を削除すると、リストのオブジェクトへの参照が削除されるだけです。 オブジェクトはメモリに存在します。 オブジェクトを削除すると、そのオブジェクトは存在しなくなり、そのメモリは再利用されます。 したがって、要素のオブジェクトが削除された直後に要素を削除し、リストが存在しないオブジェクトにアクセスしないようにすることが重要です。

#### <a name="to-delete-all-elements-in-an-array"></a><a name="_core_to_delete_all_elements_in_an_array"></a>配列内のすべての要素を削除するには

1. 配列`GetSize`を反復処理するには、整数のインデックス値を使用します。

1. **delete**演算子を使用して、反復処理で検出された各要素を削除します。

1. 要素を`RemoveAll`削除した後、配列からすべての要素を削除するには、関数を呼び出します。

   配列のすべての要素を削除するコードは次のとおりです。

   [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]

上記のリスト例と同様に、配列内`RemoveAll`のすべての要素を削除したり、個々の`RemoveAt`要素を削除したりするために呼び出すことができます。

#### <a name="to-delete-all-elements-in-a-map"></a><a name="_core_to_delete_all_elements_in_a_map"></a>マップ内のすべての要素を削除するには

1. 配列`GetStartPosition`を`GetNextAssoc`反復処理するには、 と を使用します。

1. **delete**演算子を使用して、各マップ要素のキーや値を、反復処理で検出されたとおりに削除します。

1. 要素が`RemoveAll`削除された後に、マップからすべての要素を削除するには、関数を呼び出します。

   `CMap`コレクションのすべての要素を削除するコードは次のとおりです。 マップ内の各要素には、キーとして文字列が、`CPerson`値としてオブジェクト (`CObject`から派生) があります。

   [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]

マップ内のすべての`RemoveAll`要素を削除したり、指定したキー`RemoveKey`を持つ個々の要素を削除したりするために呼び出すことができます。

## <a name="see-also"></a>関連項目

[コレクションのすべてのメンバーへのアクセス](../mfc/accessing-all-members-of-a-collection.md)
