---
title: ウィンドウ メモリの割り当てと解放
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: a9bbf92a586a910dfa4e81774ce4817c9cf458e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582495"
---
# <a name="allocating-and-deallocating-window-memory"></a>ウィンドウ メモリの割り当てと解放

C++ を使用しないでください**削除**フレーム ウィンドウまたはビューを破棄する演算子。 代わりに、`CWnd`メンバー関数は`DestroyWindow`します。 フレーム ウィンドウ、そのため、割り当てる必要がある演算子でヒープに**新しい**します。 フレーム ウィンドウのスタック フレームにまたはグローバルに割り当てるときは注意します。 他のウィンドウは、可能な限りのスタック フレームに割り当てる必要があります。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [ウィンドウの作成](../mfc/creating-windows.md)

- [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)

- [Cwnd と HWND の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>関連項目

[ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

