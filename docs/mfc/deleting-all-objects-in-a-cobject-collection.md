---
title: CObject コレクションのすべてのオブジェクトの削除 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- objects [MFC], deleting in collections
- objects in CObject collections, deleting
- CObject class [MFC], deleting in collection
- collection classes [MFC], deleting all objects
- CObject class collection
- objects in CObject collections
- collection classes [MFC], shared objects
ms.assetid: 81d2c1d5-a0a5-46e1-8ab9-82b45cf7afd2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f57e503e43bdb637b85e4642349203b9f2e8aa6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348824"
---
# <a name="deleting-all-objects-in-a-cobject-collection"></a>CObject コレクションの全オブジェクトの削除
この記事では、(コレクション オブジェクト自体を削除するには) なしのコレクション内のすべてのオブジェクトを削除する方法について説明します。  
  
 コレクション内のすべてのオブジェクトを削除する`CObject`s (またはから派生したオブジェクトの`CObject`)、記事に説明されているイテレーション手法のいずれかを使用する[のコレクションのすべてのメンバーをアクセスする](../mfc/accessing-all-members-of-a-collection.md)内の各オブジェクトを削除するにはオンにします。  
  
> [!CAUTION]
>  コレクション内のオブジェクトを共有することができます。 つまり、コレクション、オブジェクトへのポインターを保持するが、プログラムの他の部分は、同じオブジェクトへのポインターにもあります。 オブジェクトを使用してすべての部分が完了するまでに共有されているオブジェクトを削除しないように注意する必要があります。  
  
 この記事では、オブジェクトを削除する方法を示します。  
  
-   [一覧](#_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject)  
  
-   [配列](#_core_to_delete_all_elements_in_an_array)  
  
-   [マップ](#_core_to_delete_all_elements_in_a_map)  
  
#### <a name="_core_to_delete_all_objects_in_a_list_of_pointers_to_cobject"></a>  CObject へのポインターのリスト内のすべてのオブジェクトを削除するには  
  
1.  使用して`GetHeadPosition`と`GetNext`リストを反復処理します。  
  
2.  使用して、**削除**のイテレーションで検出された各オブジェクトを削除する演算子です。  
  
3.  呼び出す、`RemoveAll`それらの要素に関連付けられているオブジェクトが削除された後、一覧からすべての要素を削除する関数。  
  
 次の例は、の一覧からすべてのオブジェクトを削除する方法を示しています。`CPerson`オブジェクト。 リスト内の各オブジェクトはへのポインター、`CPerson`ヒープに割り当てられているオブジェクト。  
  
 [!code-cpp[NVC_MFCCollections#17](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_1.cpp)]  
  
 最後の関数呼び出し`RemoveAll`、一覧からすべての要素を削除するリスト メンバー関数です。 このメンバー関数は`RemoveAt`1 つの要素を削除します。  
  
 要素のオブジェクトを削除して、要素自体を削除する違いに注意してください。 リストから要素を削除すると、単なるリストのオブジェクトへの参照を削除します。 オブジェクトは、メモリに引き続き存在します。 オブジェクトを削除して消滅するので、メモリがクリアされます。 したがって、存在しなくなったオブジェクトにアクセスしようとしてされません一覧されるように、要素のオブジェクトが削除された後にすぐに要素を削除する重要なは。  
  
#### <a name="_core_to_delete_all_elements_in_an_array"></a>  配列内のすべての要素を削除するには  
  
1.  使用して`GetSize`と整数のインデックス値、配列を反復処理します。  
  
2.  使用して、**削除**のイテレーションで検出された各要素を削除する演算子です。  
  
3.  呼び出す、`RemoveAll`関数が削除された後、配列からすべての要素を削除します。  
  
     配列のすべての要素を削除するためのコードは次のとおりです。  
  
     [!code-cpp[NVC_MFCCollections#18](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_2.cpp)]  
  
 一覧上の例と、呼び出すことができます、`RemoveAll`配列内のすべての要素を削除するまたは`RemoveAt`個々 の要素を削除します。  
  
#### <a name="_core_to_delete_all_elements_in_a_map"></a> マップ内のすべての要素を削除するには  
  
1.  使用して`GetStartPosition`と`GetNextAssoc`配列を反復処理します。  
  
2.  使用して、**削除**のイテレーションで検出された、キーまたは各マップ要素の値を削除するオペレーターです。  
  
3.  呼び出す、`RemoveAll`関数が削除された後、マップからすべての要素を削除します。  
  
     すべての要素を削除するため、コード、`CMap`コレクションは、次のようにします。 マップ内の各要素がキーとしての文字列と`CPerson`オブジェクト (から派生した`CObject`) 値として。  
  
     [!code-cpp[NVC_MFCCollections#19](../mfc/codesnippet/cpp/deleting-all-objects-in-a-cobject-collection_3.cpp)]  
  
 呼び出すことができます`RemoveAll`マップ内のすべての要素を削除するまたは`RemoveKey`を指定したキーに個々 の要素を削除します。  
  
## <a name="see-also"></a>関連項目  
 [コレクションの全メンバーへのアクセス](../mfc/accessing-all-members-of-a-collection.md)

