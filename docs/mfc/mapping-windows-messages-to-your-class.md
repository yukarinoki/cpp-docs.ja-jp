---
title: ダイアログ クラスと Windows メッセージの対応
ms.date: 09/06/2019
helpviewer_keywords:
- MFC dialog boxes [MFC], Windows messages
- message maps [MFC], in dialog class
- Windows messages [MFC], mapping in dialog classes
- messages to dialog class [MFC]
- mappings [MFC], messages to dialog class [MFC]
- message maps [MFC], mapping Windows messages to classes
- messages to dialog class [MFC], mapping
- Class Wizard [MFC]
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
ms.openlocfilehash: 6b1155945c4248c5ac2755d60d8887f890e6d324
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618294"
---
# <a name="mapping-windows-messages-to-your-class"></a>ダイアログ クラスと Windows メッセージの対応

Windows メッセージを処理するためのダイアログボックスが必要な場合は、適切なハンドラー関数をオーバーライドします。 これを行うには、**ソリューションエクスプローラー**の [**クラスビュー** ] タブをクリックし、ダイアログボックスを表すクラスを右クリックして、[[クラスウィザード](reference/mfc-class-wizard.md)] を選択します。 ウィザードを使用して、メッセージをダイアログクラスに[マップ](reference/mapping-messages-to-functions.md)します。 これにより、各メッセージのメッセージマップエントリが書き込まれ、メッセージハンドラーのメンバー関数がクラスに追加されます。 コードエディターを使用して、メッセージハンドラーにコードを記述します。

また、 [CDialog](reference/cdialog-class.md)のメンバー関数とその基本クラス (特に[CWnd](reference/cwnd-class.md)) をオーバーライドすることもできます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [メッセージの処理とマッピング](message-handling-and-mapping.md)

- [通常オーバーライドされるメンバー関数](commonly-overridden-member-functions.md)

- [一般的に追加されるメンバー関数](commonly-added-member-functions.md)

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
