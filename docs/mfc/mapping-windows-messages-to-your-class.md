---
title: ダイアログ クラスと Windows メッセージの対応
ms.date: 11/04/2016
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 37c0f61f4d38e3e152d9dd508c9487782ebdf81a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630461"
---
# <a name="mapping-windows-messages-to-your-class"></a>ダイアログ クラスと Windows メッセージの対応

Windows メッセージを処理するために、ダイアログ ボックスが必要な場合は、適切なハンドラー関数をオーバーライドします。 これを行うには、プロパティ ウィンドウを使用して、[メッセージ](../mfc/reference/mapping-messages-to-functions.md)ダイアログ クラスにします。 これにより、各メッセージのメッセージ マップ エントリを書き込み、メッセージ ハンドラー メンバー関数をクラスに追加します。 Visual C ソース コード エディターを使用して、メッセージ ハンドラーでコードを記述します。

メンバー関数をオーバーライドすることもできます。 [CDialog](../mfc/reference/cdialog-class.md)とその基本クラスでは、特に[CWnd](../mfc/reference/cwnd-class.md)します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [メッセージの処理とのマッピング](../mfc/message-handling-and-mapping.md)

- [通常オーバーライドされるメンバー関数](../mfc/commonly-overridden-member-functions.md)

- [通常追加されるメンバー関数](../mfc/commonly-added-member-functions.md)

## <a name="see-also"></a>関連項目

[ダイアログ ボックス](../mfc/dialog-boxes.md)<br/>
[ダイアログ ボックスの有効期間](../mfc/life-cycle-of-a-dialog-box.md)

