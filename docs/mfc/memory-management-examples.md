---
title: 'メモリ管理 : 例'
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], memory allocation
- data structures [MFC]
- arrays [MFC], allocating resources
- objects [MFC], allocating memory
- data structures [MFC], allocating memory
- examples [MFC], memory allocation
- heap allocation [MFC], examples
- memory allocation [MFC], arrays
- MFC, memory management
- struct memory allocation [MFC]
- types [MFC], memory allocation
- memory allocation [MFC], objects
- memory allocation [MFC], examples
- arrays [MFC], memory management
- frame allocation [MFC]
- memory allocation [MFC], data structures
ms.assetid: f10240f8-b698-4c83-9288-97a54318930b
ms.openlocfilehash: 3a1e647175b7b5294e672efbf234e3ae2853e411
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367846"
---
# <a name="memory-management-examples"></a>メモリ管理 : 例

この資料では、MFC が次の 3 種類のメモリ割り当てについて、フレーム割り当てとヒープ割り当てを実行する方法について説明します。

- [バイトの配列](#_core_allocation_of_an_array_of_bytes)

- [データ構造](#_core_allocation_of_a_data_structure)

- [1 つのオブジェクト](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a>バイト配列の割り当て

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>フレームにバイト配列を割り当てるには

1. 次のコードに示すように、配列を定義します。 配列変数がスコープを終了すると、配列は自動的に削除され、そのメモリは解放されます。

   [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>ヒープにバイト配列 (または任意のプリミティブ データ型) を割り当てるには

1. **new**演算子は、次の例に示す配列構文と共に使用します。

   [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>ヒープから配列の割り当てを解除するには

1. **delete**演算子は次のように使用します。

   [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a>データ構造の割り当て

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>フレームにデータ構造を割り当てるには

1. 構造体変数を次のように定義します。

   [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]

   構造体が占有するメモリは、スコープを終了すると再利用されます。

#### <a name="to-allocate-data-structures-on-the-heap"></a>ヒープにデータ構造を割り当てるには

1. 次の例に示すように **、new**を使用してヒープにデータ構造を割り当て、**削除**して割り当てを解除します。

   [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a>オブジェクトの割り当て

#### <a name="to-allocate-an-object-on-the-frame"></a>フレームにオブジェクトを割り当てるには

1. オブジェクトを次のように宣言します。

   [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]

   オブジェクトのデストラクターは、オブジェクトがそのスコープを終了すると自動的に呼び出されます。

#### <a name="to-allocate-an-object-on-the-heap"></a>ヒープにオブジェクトを割り当てるには

1. オブジェクトへのポインターを返す**new**演算子を使用して、ヒープにオブジェクトを割り当てます。 **削除**演算子を使用して削除します。

   次のヒープとフレームの例では、`CPerson`コンストラクターが引数を受け取らないものとします。

   [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]

   `CPerson`コンストラクタの引数が**char**へのポインタである場合、フレーム割り当てのステートメントは次のようになります。

   [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]

   ヒープ割り当てのステートメントは次のとおりです。

   [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>関連項目

[メモリ管理 : ヒープ割り当て](../mfc/memory-management-heap-allocation.md)
