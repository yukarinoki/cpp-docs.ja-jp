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
ms.openlocfilehash: 2e0484698654cd14f22a92be76a80f71c0f9adf5
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621842"
---
# <a name="detaching-a-cwnd-from-its-hwnd"></a>CWnd と HWND の分離

オブジェクトの関係を回避する必要がある場合は、 `HWND` MFC によって別のメンバー関数 Detach が提供され、 `CWnd` Windows ウィンドウから C++ ウィンドウオブジェクトが切断されます。 [Detach](reference/cwnd-class.md#detach) これにより、オブジェクトが破棄されたときに、デストラクターが Windows ウィンドウを破棄するのを防ぎます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [作成 (ウィンドウを)](creating-windows.md)

- [ウィンドウの破棄順序](window-destruction-sequence.md)

- [ウィンドウメモリの割り当てと割り当て解除](allocating-and-deallocating-window-memory.md)

## <a name="see-also"></a>関連項目

[ウィンドウ オブジェクト](window-objects.md)
