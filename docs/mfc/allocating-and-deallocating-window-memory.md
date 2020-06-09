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
ms.openlocfilehash: 02546559183d0e14973bc2e5ccb26a4570a39b1e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623261"
---
# <a name="allocating-and-deallocating-window-memory"></a>ウィンドウ メモリの割り当てと解放

フレームウィンドウまたはビューを破棄する場合は、C++ **delete**演算子を使用しないでください。 代わりに、 `CWnd` メンバー関数を呼び出し `DestroyWindow` ます。 そのため、フレームウィンドウは、 **new**演算子を使用してヒープに割り当てる必要があります。 スタックフレームまたはグローバルにフレームウィンドウを割り当てるときは注意してください。 可能な場合は、他のウィンドウをスタックフレームに割り当てる必要があります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [作成 (ウィンドウを)](creating-windows.md)

- [ウィンドウの破棄順序](window-destruction-sequence.md)

- [CWnd と HWND の分離](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>関連項目

[破棄 (ウィンドウオブジェクトを)](destroying-window-objects.md)
