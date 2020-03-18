---
title: CWnd と HWND の分離
ms.date: 11/04/2016
helpviewer_keywords:
- HWND, detaching CWnd from
- removing HWNDs from CWnds
- CWnd objects [MFC], detaching from HWND
- detaching CWnds from HWNDs
- Detach method (CWnd class)
ms.assetid: 6efadf84-0517-4a3f-acfd-216e088f19c6
ms.openlocfilehash: f7a6f97ba9f1dd3a928a5450c1a899ce09a4ac5f
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446962"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd と HWND の分離

オブジェクト`HWND` の関係を回避する必要がある場合は、MFC によって別[Detach](../mfc/reference/cwnd-class.md#detach)の `CWnd` メンバー関数でC++ある Detach が提供され、Windows ウィンドウからウィンドウオブジェクトが切断されます。 これにより、オブジェクトが破棄されたときに、デストラクターが Windows ウィンドウを破棄するのを防ぎます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [作成 (ウィンドウを)](../mfc/creating-windows.md)

- [ウィンドウの破棄順序](../mfc/window-destruction-sequence.md)

- [ウィンドウメモリの割り当てと割り当て解除](../mfc/allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>参照

[Window オブジェクト](../mfc/window-objects.md)
