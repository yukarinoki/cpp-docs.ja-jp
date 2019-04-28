---
title: メモリ管理
ms.date: 11/04/2016
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
ms.openlocfilehash: 1c7f901009d5e1e7f0af20d493bb748b46b18480
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62219132"
---
# <a name="memory-management"></a>メモリ管理

この記事のグループには、汎用サービスの Microsoft Foundation Class ライブラリ (MFC) に関連するメモリ管理を活用する方法について説明します。 メモリの割り当ては、2 つの主なカテゴリに分類できます: フレーム割り当ておよびヒープの割り当て。

2 つの割り当て方法の 1 つの主な違いにフレームを割り当てられる実際のメモリを操作する通常ブロック自体には、ヒープ割り当てはするが常に指定のポインターのメモリ ブロックへ。 2 つのスキームのもう 1 つの主な違いは、フレーム オブジェクトが自動的に削除されたこと、中に、ヒープのオブジェクトは、プログラマが明示的に削除する必要があります。

非 MFC プログラムで Windows 用のメモリ管理については、次を参照してください。[メモリ管理](/windows/desktop/memory/memory-management)Windows SDK に含まれています。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [フレーム割り当て](../mfc/memory-management-frame-allocation.md)

- [ヒープの割り当て](../mfc/memory-management-heap-allocation.md)

- [配列のメモリの割り当てください。](../mfc/memory-management-examples.md)

- [配列のメモリのヒープから割り当て解除](../mfc/memory-management-examples.md)

- [データ構造のメモリの割り当てください。](../mfc/memory-management-examples.md)

- [オブジェクトのメモリの割り当てください。](../mfc/memory-management-examples.md)

- [サイズ変更可能なメモリ ブロック](../mfc/memory-management-resizable-memory-blocks.md)

## <a name="see-also"></a>関連項目

[概念](../mfc/mfc-concepts.md)<br/>
[MFC の一般的なトピック](../mfc/general-mfc-topics.md)
