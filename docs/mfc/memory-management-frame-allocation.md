---
title: 'メモリ管理: フレーム割り当て |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory leaks [MFC], frame allocation
- memory [MFC], detecting leaks
- memory [MFC], reclaiming
- memory allocation [MFC], frames
- frame variables [MFC], automatic deletion of
- scope [MFC], frame variables
- heap allocation [MFC], vs. frame allocation
- variables [MFC], frame variables
- memory leaks [MFC], detecting
- memory, releasing [MFC]
- stack frames [MFC]
- memory leaks [MFC], allocating objects on the frame
- detecting memory leaks [MFC]
- frame allocation [MFC]
- frame variables [MFC]
ms.assetid: 945a211a-6f4f-4679-bb6a-b0f2a0d4a6c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f67149e5835ee6f2b8922b29ee92872b24d0ec4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349312"
---
# <a name="memory-management-frame-allocation"></a>メモリ管理 : フレーム割り当て
フレーム割り当てが設定されている「スタック フレーム」から名前を取得する関数が呼び出されるときに、必ずです。 スタック フレームは、一時的を保持する引数に定義されている任意の変数だけでなく、関数、関数に対してローカルなメモリの領域です。 フレーム変数は、コンパイラは自動的にそれらの領域を割り当てるために、多くの場合、「自動」の変数と呼ばれます。  
  
 フレーム割り当ての 2 つの特徴があります。 最初に、ローカル変数を定義するときに十分な領域は割り当て全体の変数を保持するために、スタック フレーム上、大きな配列またはデータ構造体である場合でも。 次に、フレーム変数はスコープ外に出ると自動的に削除します。  
  
 [!code-cpp[NVC_MFC_Utilities#10](../mfc/codesnippet/cpp/memory-management-frame-allocation_1.cpp)]  
  
 関数のローカル変数の場合は、このスコープの移行は、入れ子になった中かっこを使用する場合は、フレーム変数のスコープが、関数が終了を関数よりも小さくすることができるは発生します。 フレーム変数の自動削除は非常に重要です。 単純なプリミティブ型の場合 (など`int`または**バイト**)、配列、またはデータ構造、自動削除が単に、変数で使用されるメモリを解放します。 変数がスコープ外になった、ために、アクセスできません。 C++ オブジェクトの場合、自動削除のプロセスがもう少し複雑なです。  
  
 オブジェクトが、フレーム変数として定義されている場合、コンス トラクターは定義が発生した時点で自動的に呼び出されます。 オブジェクトがスコープ外に出るときに、デストラクターは自動的に呼び出されるオブジェクトのメモリが回収される前にします。 この自動構築と破棄が非常に便利なできますが、自動への呼び出し、特にデストラクターに注意してください。  
  
 フレーム上のオブジェクトの割り当ての主な利点は、それらが自動的に削除されたことです。 フレームに、オブジェクトを割り当てるときは忘れられたオブジェクトがメモリ リークの原因について心配する必要はありません。 (メモリ リークの詳細については、「アーティクル[MFC でのメモリ リークの検出します](http://msdn.microsoft.com/en-us/29ee8909-96e9-4246-9332-d3a8aa8d4658))。フレーム割り当ての欠点は、そのスコープ外にフレーム変数を使用できないことです。 もう 1 つの要因とヒープ割り当てフレーム割り当てを選択する際に、大きな構造体とオブジェクトは、ある多くの場合、スタック領域は限られた多くの場合は、記憶域のスタックの代わりに、ヒープを使用する方が適切です。  
  
## <a name="see-also"></a>関連項目  
 [メモリ管理](../mfc/memory-management.md)

