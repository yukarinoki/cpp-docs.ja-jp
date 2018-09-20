---
title: メモリ管理 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e4e83342dde85aae626c9fb83a9493f3e3dd668b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383997"
---
# <a name="memory-management"></a>メモリ管理

この記事のグループには、汎用サービスの Microsoft Foundation Class ライブラリ (MFC) に関連するメモリ管理を活用する方法について説明します。 メモリの割り当ては、2 つの主なカテゴリに分類できます: フレーム割り当ておよびヒープの割り当て。

2 つの割り当て方法の 1 つの主な違いにフレームを割り当てられる実際のメモリを操作する通常ブロック自体には、ヒープ割り当てはするが常に指定のポインターのメモリ ブロックへ。 2 つのスキームのもう 1 つの主な違いは、フレーム オブジェクトが自動的に削除されたこと、中に、ヒープのオブジェクトは、プログラマが明示的に削除する必要があります。

非 MFC プログラムで Windows 用のメモリ管理については、次を参照してください。[メモリ管理](https://msdn.microsoft.com/library/windows/desktop/aa366779)Windows SDK に含まれています。

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

