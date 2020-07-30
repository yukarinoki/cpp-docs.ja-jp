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
ms.openlocfilehash: 33d471b41c8f1fd670e25626049ecd9b06b034e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195201"
---
# <a name="allocating-and-deallocating-window-memory"></a>ウィンドウ メモリの割り当てと解放

**`delete`** フレームウィンドウまたはビューを破棄する場合は、C++ 演算子を使用しないでください。 代わりに、 `CWnd` メンバー関数を呼び出し `DestroyWindow` ます。 そのため、フレームウィンドウは、演算子を使用してヒープに割り当てる必要があり **`new`** ます。 スタックフレームまたはグローバルにフレームウィンドウを割り当てるときは注意してください。 可能な場合は、他のウィンドウをスタックフレームに割り当てる必要があります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ウィンドウの作成](creating-windows.md)

- [ウィンドウの破棄順序](window-destruction-sequence.md)

- [CWnd と HWND の分離](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>関連項目

[破棄 (ウィンドウオブジェクトを)](destroying-window-objects.md)
