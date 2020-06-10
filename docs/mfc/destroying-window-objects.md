---
title: ウィンドウ オブジェクトの破棄
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], destroying
- window objects [MFC], deleting
- window objects [MFC], destroying
- window objects [MFC], removing
ms.assetid: 3241fea0-c614-4a25-957d-20f21bd5fd0c
ms.openlocfilehash: 22b483c1005931b229453ae229935c0e716ab726
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621863"
---
# <a name="destroying-window-objects"></a>ウィンドウ オブジェクトの破棄

ユーザーがウィンドウで終了したときに C++ ウィンドウオブジェクトを破棄するには、独自の子ウィンドウを使用する必要があります。 これらのオブジェクトが破棄されていない場合、アプリケーションはメモリを回復しません。 さいわい、フレームワークはウィンドウの破棄だけでなく、フレームウィンドウ、ビュー、およびダイアログボックスの作成も管理します。 追加のウィンドウを作成する場合は、そのウィンドウを破棄する必要があります。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [ウィンドウの破棄順序](window-destruction-sequence.md)

- [ウィンドウメモリの割り当てと割り当て解除](allocating-and-deallocating-window-memory.md)

- [CWnd と HWND の分離](detaching-a-cwnd-from-its-hwnd.md)

- [全般ウィンドウ作成順序](general-window-creation-sequence.md)

- [フレーム ウィンドウの破棄](destroying-frame-windows.md)

## <a name="see-also"></a>関連項目

[ウィンドウ オブジェクト](window-objects.md)
