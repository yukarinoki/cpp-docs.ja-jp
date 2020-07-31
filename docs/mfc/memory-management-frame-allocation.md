---
title: 'メモリ管理 : フレーム割り当て'
ms.date: 11/04/2016
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
ms.openlocfilehash: cb66a0c0aea16f7e6831b6a1aff1a125df355210
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225047"
---
# <a name="memory-management-frame-allocation"></a>メモリ管理 : フレーム割り当て

フレームの割り当ては、関数が呼び出されるたびに設定される "スタックフレーム" からの名前を受け取ります。 スタックフレームは、関数の引数、および関数に対してローカルに定義されている変数を一時的に保持するメモリ領域です。 フレーム変数は、コンパイラによって領域が自動的に割り当てられるため、"自動" 変数と呼ばれることがよくあります。

フレーム割り当てには、主に2つの特性があります。 まず、ローカル変数を定義すると、大きな配列やデータ構造体であっても、変数全体を保持するのに十分な領域がスタックフレームに割り当てられます。 次に、フレーム変数がスコープ外に出ると自動的に削除されます。

[!code-cpp[NVC_MFC_Utilities#10](codesnippet/cpp/memory-management-frame-allocation_1.cpp)]

ローカル関数変数の場合、このスコープ遷移は関数が終了したときに発生しますが、入れ子になった中かっこが使用されている場合は、フレーム変数のスコープが関数よりも小さくなることがあります。 フレーム変数の自動削除は非常に重要です。 単純なプリミティブ型 ( **`int`** または**byte**など)、配列、またはデータ構造の場合、自動削除では、変数によって使用されるメモリが単に解放されます。 変数はスコープ外になったため、アクセスすることはできません。 ただし、C++ オブジェクトの場合、自動削除のプロセスは少し複雑になります。

オブジェクトがフレーム変数として定義されている場合、そのコンストラクターは定義が検出された時点で自動的に呼び出されます。 オブジェクトがスコープ外に出ると、オブジェクトのメモリが解放される前に、そのデストラクターが自動的に呼び出されます。 この自動構築と破棄は非常に便利ですが、自動呼び出し (特にデストラクター) に注意する必要があります。

フレームにオブジェクトを割り当てることの主な利点は、それらが自動的に削除されることです。 オブジェクトをフレームに割り当てた場合、メモリリークの原因となったオブジェクトを忘れてしまう心配はありません。 (メモリリークの詳細については、「 [MFC でのメモリリークの検出](/previous-versions/visualstudio/visual-studio-2010/c99kz476(v=vs.100))」を参照してください)。フレーム割り当ての欠点は、フレーム変数をそのスコープ外で使用することはできないということです。 フレーム割り当てとヒープ割り当てを選択するもう1つの要因として、大規模な構造体とオブジェクトの場合は、スタック領域が制限されることが多いため、ストレージのスタックではなくヒープを使用することをお勧めします。

## <a name="see-also"></a>関連項目

[メモリ管理](memory-management.md)
