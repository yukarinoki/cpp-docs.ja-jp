---
description: '詳細情報: ウィンドウの破棄順序'
title: ウィンドウの破棄順序
ms.date: 11/04/2016
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
ms.openlocfilehash: 2ba60f1dcd3668a754bbe4384a6c8cf6b4d541d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207684"
---
# <a name="window-destruction-sequence"></a>ウィンドウの破棄順序

MFC フレームワークでは、ユーザーがフレームウィンドウを閉じると、ウィンドウの既定の [OnClose](../mfc/reference/cwnd-class.md#onclose) ハンドラーは [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)を呼び出します。 Windows ウィンドウが破棄されるときに呼び出される最後のメンバー関数は [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)であり、一部のクリーンアップでは、windows クリーンアップを実行する [既定](../mfc/reference/cwnd-class.md#default) のメンバー関数を呼び出し、最後に仮想メンバー関数 [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)を呼び出します。 の [CFrameWnd](../mfc/reference/cframewnd-class.md) 実装は、 `PostNcDestroy` C++ ウィンドウオブジェクトを削除します。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ウィンドウ メモリの割り当てと解放](../mfc/allocating-and-deallocating-window-memory.md)

- [CWnd と HWND の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>関連項目

[破棄 (ウィンドウオブジェクトを)](../mfc/destroying-window-objects.md)
