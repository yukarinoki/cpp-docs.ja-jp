---
title: ヒープ競合の回避 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- heap contention
ms.assetid: 797129d7-5f8c-4b0e-8974-bb93217e9ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a4f01bdbbc14e09fe8f9823eed738556ee876376
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43762252"
---
# <a name="avoidance-of-heap-contention"></a>ヒープ競合の回避

MFC および ATL によって提供される既定の文字列のマネージャーとは、グローバル ヒープ上に単純なラッパーです。 このグローバル ヒープは、スレッド セーフなつまり複数のスレッドが割り当てるし、ヒープを破損することがなく同時にそこからメモリを解放することができます。 スレッド セーフを確保するため、ヒープを自体へのアクセスをシリアル化する必要があります。 通常、クリティカル セクションまたは同様のロック機構を実行します。 2 つのスレッドが、ヒープを同時にアクセスしようとすると、ときに、その他のスレッドの要求が完了するまでに 1 つのスレッドがブロックされます。 多くのアプリケーションでは、このような状況はめったに発生しますおよびヒープのロック機構のパフォーマンスに与える影響はごくわずかです。 ただし、複数のスレッドからのヒープを頻繁にアクセスするアプリケーションでは、ヒープのロックの競合によりアプリケーションを実行 (複数の cpu を搭載したコンピューター) 上でも、シングル スレッドした場合よりも速度が低下することができます。

使用するアプリケーション[CStringT](../atl-mfc-shared/reference/cstringt-class.md)は特に、ヒープの競合が発生しやすいためでの操作`CStringT`オブジェクトは、文字列バッファーの再割り当てを頻繁に必要とします。

スレッド間でヒープ競合を軽減する方法の 1 つでは、各スレッドが、スレッド ローカルのプライベート ヒープから文字列を割り当てます。 文字列が割り当てられている限り、特定のスレッドのアロケーターは、そのスレッドでのみ使用されます、アロケーターでスレッド セーフである必要はありません。

## <a name="example"></a>例

次の例では、スレッド プロシージャにそのスレッドで文字列を使用する独自のプライベート非スレッド セーフなヒープ割り当てを示しています。

[!code-cpp[NVC_ATLMFC_Utilities#182](../atl-mfc-shared/codesnippet/cpp/avoidance-of-heap-contention_1.cpp)]

## <a name="comments"></a>コメント

この同じスレッド プロシージャを使用して複数のスレッドが実行される可能性があるが、スレッド間で競合がないため、各スレッドで独自のヒープ。 さらに、各ヒープはスレッド セーフではないという事実は、スレッドのコピーが 1 つだけが実行されている場合でも、パフォーマンスの測定可能な向上を示します。 これは、同時実行のアクセスを保護する高価なインタロックされた操作を使用していない、ヒープの結果です。

複雑なスレッド プロシージャでは、スレッド ローカル ストレージ (TLS) スロットで、スレッドの文字列のマネージャーへのポインターを格納する便利な場合があります。 これにより、スレッドの文字列のマネージャーにアクセスするスレッドのプロシージャによって呼び出された他の関数です。

## <a name="see-also"></a>関連項目

[CStringT によるメモリ管理](../atl-mfc-shared/memory-management-with-cstringt.md)

