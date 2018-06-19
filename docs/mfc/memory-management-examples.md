---
title: 'メモリ管理: 例 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 84bc2ce7c084f2951d63eee546df3bf70a2ba1fe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347192"
---
# <a name="memory-management-examples"></a>メモリ管理 : 例
この記事では、メモリ割り当ての 3 つの一般的な種類の各、MFC がフレーム割り当てとヒープの割り当てを実行する方法について説明します。  
  
-   [バイト配列](#_core_allocation_of_an_array_of_bytes)  
  
-   [データ構造体](#_core_allocation_of_a_data_structure)  
  
-   [オブジェクト](#_core_allocation_of_an_object)  
  
##  <a name="_core_allocation_of_an_array_of_bytes"></a> バイト配列の割り当て  
  
#### <a name="to-allocate-an-array-of-bytes-on-the-frame"></a>フレームにバイトの配列を割り当てる  
  
1.  次のコードに示すように、配列を定義します。 配列が自動的に削除され、配列変数には、そのスコープが終了するときにそのメモリが再利用します。  
  
     [!code-cpp[NVC_MFC_Utilities#1](../mfc/codesnippet/cpp/memory-management-examples_1.cpp)]  
  
#### <a name="to-allocate-an-array-of-bytes-or-any-primitive-data-type-on-the-heap"></a>ヒープのバイト (または任意のプリミティブ データ型) の配列を割り当てる  
  
1.  使用して、**新しい**この例に示すように配列の構文を持つ演算子。  
  
     [!code-cpp[NVC_MFC_Utilities#2](../mfc/codesnippet/cpp/memory-management-examples_2.cpp)]  
  
#### <a name="to-deallocate-the-arrays-from-the-heap"></a>ヒープからの配列の割り当てを解除するには  
  
1.  使用して、**削除**よう演算子。  
  
     [!code-cpp[NVC_MFC_Utilities#3](../mfc/codesnippet/cpp/memory-management-examples_3.cpp)]  
  
##  <a name="_core_allocation_of_a_data_structure"></a> データ構造の割り当て  
  
#### <a name="to-allocate-a-data-structure-on-the-frame"></a>フレーム上のデータ構造を割り当てる  
  
1.  構造体変数を次のように定義します。  
  
     [!code-cpp[NVC_MFC_Utilities#4](../mfc/codesnippet/cpp/memory-management-examples_4.cpp)]  
  
     構造体が占有するメモリが回収されるは、そのスコープを終了する場合。  
  
#### <a name="to-allocate-data-structures-on-the-heap"></a>ヒープ上のデータ構造を割り当てる  
  
1.  使用して**新しい**をヒープ上のデータ構造を割り当てると**削除**次の例で示すように、それらの割り当てを解除します。  
  
     [!code-cpp[NVC_MFC_Utilities#5](../mfc/codesnippet/cpp/memory-management-examples_5.cpp)]  
  
##  <a name="_core_allocation_of_an_object"></a> オブジェクトの割り当て  
  
#### <a name="to-allocate-an-object-on-the-frame"></a>フレーム上のオブジェクトを割り当てる  
  
1.  次のように、オブジェクトを宣言します。  
  
     [!code-cpp[NVC_MFC_Utilities#6](../mfc/codesnippet/cpp/memory-management-examples_6.cpp)]  
  
     オブジェクトのデストラクターが呼び出されるは、そのスコープ外に出るときに自動的にします。  
  
#### <a name="to-allocate-an-object-on-the-heap"></a>ヒープ上のオブジェクトを割り当てる  
  
1.  使用して、**新しい**この演算子は、オブジェクトへのポインターを返します、ヒープにオブジェクトを割り当てます。 使用して、**削除**それらを削除する演算子です。  
  
     次のヒープとフレームの例では、あると想定、`CPerson`コンス トラクターは引数を受け取りません。  
  
     [!code-cpp[NVC_MFC_Utilities#7](../mfc/codesnippet/cpp/memory-management-examples_7.cpp)]  
  
     場合の引数、`CPerson`コンス トラクターへのポインターは、 `char`、フレーム割り当て用のステートメントは。  
  
     [!code-cpp[NVC_MFC_Utilities#8](../mfc/codesnippet/cpp/memory-management-examples_8.cpp)]  
  
     ヒープ割り当て用のステートメントは次のとおりです。  
  
     [!code-cpp[NVC_MFC_Utilities#9](../mfc/codesnippet/cpp/memory-management-examples_9.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [メモリ管理: ヒープ割り当て](../mfc/memory-management-heap-allocation.md)

