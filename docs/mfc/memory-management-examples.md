---
description: '詳細については、「メモリ管理: 例」を参照してください。'
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
ms.openlocfilehash: dcd7ba9ce5fee0af932766494f0a7afd64684e77
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222295"
---
# <a name="memory-management-examples"></a>メモリ管理 : 例

この記事では、次の3つの一般的なメモリ割り当てのそれぞれに対して、MFC がフレーム割り当てとヒープ割り当てを実行する方法について説明します。

- [バイトの配列](#_core_allocation_of_an_array_of_bytes)

- [データ構造](#_core_allocation_of_a_data_structure)

- [1 つのオブジェクト](#_core_allocation_of_an_object)

## <a name="allocation-of-an-array-of-bytes"></a><a name="_core_allocation_of_an_array_of_bytes"></a> バイト配列の割り当て

#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>フレームにバイト配列を割り当てるには

1. 次のコードに示すように、配列を定義します。 配列変数がスコープを終了すると、配列が自動的に削除され、メモリが解放されます。

   [!code-cpp[NVC_MFC_Utilities#1](codesnippet/cpp/memory-management-examples_1.cpp)]

#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>ヒープにバイト (または任意のプリミティブデータ型) の配列を割り当てるには

1. 次の **`new`** 例に示すように、演算子に配列構文を使用します。

   [!code-cpp[NVC_MFC_Utilities#2](codesnippet/cpp/memory-management-examples_2.cpp)]

#### <a name="to-deallocate-the-arrays-from-the-heap"></a>ヒープから配列の割り当てを解除するには

1. 次のように演算子を使用し **`delete`** ます。

   [!code-cpp[NVC_MFC_Utilities#3](codesnippet/cpp/memory-management-examples_3.cpp)]

## <a name="allocation-of-a-data-structure"></a><a name="_core_allocation_of_a_data_structure"></a> データ構造の割り当て

#### <a name="to-allocate-a-data-structure-on-the-frame"></a>フレームにデータ構造を割り当てるには

1. 構造体変数を次のように定義します。

   [!code-cpp[NVC_MFC_Utilities#4](codesnippet/cpp/memory-management-examples_4.cpp)]

   構造体によって占有されているメモリは、そのスコープを終了すると解放されます。

#### <a name="to-allocate-data-structures-on-the-heap"></a>ヒープにデータ構造を割り当てるには

1. **`new`** 次の例に示すように、を使用してヒープにデータ構造体を割り当て、割り当てを **`delete`** 解除します。

   [!code-cpp[NVC_MFC_Utilities#5](codesnippet/cpp/memory-management-examples_5.cpp)]

## <a name="allocation-of-an-object"></a><a name="_core_allocation_of_an_object"></a> オブジェクトの割り当て

#### <a name="to-allocate-an-object-on-the-frame"></a>フレームにオブジェクトを割り当てるには

1. オブジェクトを次のように宣言します。

   [!code-cpp[NVC_MFC_Utilities#6](codesnippet/cpp/memory-management-examples_6.cpp)]

   オブジェクトのデストラクターは、オブジェクトがスコープを終了したときに自動的に呼び出されます。

#### <a name="to-allocate-an-object-on-the-heap"></a>ヒープにオブジェクトを割り当てるには

1. オブジェクトへのポインターを返す演算子を使用して、 **`new`** ヒープ上にオブジェクトを割り当てます。 演算子を使用して **`delete`** 削除します。

   次のヒープとフレームの例では、コンストラクターが引数を取らないと想定して `CPerson` います。

   [!code-cpp[NVC_MFC_Utilities#7](codesnippet/cpp/memory-management-examples_7.cpp)]

   コンストラクターの引数がへのポインターである場合 `CPerson` **`char`** 、フレーム割り当てのステートメントは次のようになります。

   [!code-cpp[NVC_MFC_Utilities#8](codesnippet/cpp/memory-management-examples_8.cpp)]

   ヒープ割り当てのステートメントは次のとおりです。

   [!code-cpp[NVC_MFC_Utilities#9](codesnippet/cpp/memory-management-examples_9.cpp)]

## <a name="see-also"></a>関連項目

[メモリ管理: ヒープ割り当て](memory-management-heap-allocation.md)
