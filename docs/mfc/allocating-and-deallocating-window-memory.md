---
description: '詳細情報: ウィンドウメモリの割り当てと割り当て解除'
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
ms.openlocfilehash: 7648914289babffdfb5195f1ec53cd736e26892c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343719"
---
# <a name="allocating-and-deallocating-window-memory"></a>ウィンドウ メモリの割り当てと解放

**`delete`** フレームウィンドウまたはビューを破棄する場合は、C++ 演算子を使用しないでください。 代わりに、 `CWnd` メンバー関数を呼び出し `DestroyWindow` ます。 そのため、フレームウィンドウは、演算子を使用してヒープに割り当てる必要があり **`new`** ます。 スタックフレームまたはグローバルにフレームウィンドウを割り当てるときは注意してください。 可能な場合は、他のウィンドウをスタックフレームに割り当てる必要があります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ウィンドウの作成](creating-windows.md)

- [ウィンドウの破棄順序](window-destruction-sequence.md)

- [CWnd と HWND の分離](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>関連項目

[破棄 (ウィンドウオブジェクトを)](destroying-window-objects.md)
