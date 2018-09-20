---
title: ウィンドウの破棄順序 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04ef1aa9dadbbe965ab17945da681a0e1189c404
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446648"
---
# <a name="window-destruction-sequence"></a>ウィンドウの破棄順序

ユーザーがウィンドウの既定値であるフレーム ウィンドウを閉じるときに、MFC フレームワーク[OnClose](../mfc/reference/cwnd-class.md#onclose)ハンドラー呼び出し[DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow)します。 Windows のウィンドウが破棄されるときに呼び出されます最後のメンバー関数は[OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy)、呼び出しを行ういくつかのクリーンアップ、[既定](../mfc/reference/cwnd-class.md#default)メンバーが Windows のクリーンアップを実行する関数を呼び出す最後に、仮想メンバー関数[PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy)します。 [CFrameWnd](../mfc/reference/cframewnd-class.md)の実装`PostNcDestroy`C++ ウィンドウ オブジェクトを削除します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [割り当てとウィンドウ メモリの解放](../mfc/allocating-and-deallocating-window-memory.md)

- [Cwnd と HWND の分離](../mfc/detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>関連項目

[ウィンドウ オブジェクトの破棄](../mfc/destroying-window-objects.md)

