---
description: 詳細については、「Windows メッセージをクラスにマップする」を参照してください。
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
ms.openlocfilehash: cca13c4b262c6373fa3d968438331d5e0ce5f7d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280782"
---
# <a name="mapping-windows-messages-to-your-class"></a>ダイアログ クラスと Windows メッセージの対応

Windows メッセージを処理するためのダイアログボックスが必要な場合は、適切なハンドラー関数をオーバーライドします。 これを行うには、**ソリューションエクスプローラー** の [**クラスビュー** ] タブをクリックし、ダイアログボックスを表すクラスを右クリックして、[[クラスウィザード](reference/mfc-class-wizard.md)] を選択します。 ウィザードを使用して、メッセージをダイアログクラスに [マップ](reference/mapping-messages-to-functions.md) します。 これにより、各メッセージのメッセージマップエントリが書き込まれ、メッセージハンドラーのメンバー関数がクラスに追加されます。 コードエディターを使用して、メッセージハンドラーにコードを記述します。

また、 [CDialog](reference/cdialog-class.md) のメンバー関数とその基本クラス (特に [CWnd](reference/cwnd-class.md)) をオーバーライドすることもできます。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [メッセージの処理とマップ](message-handling-and-mapping.md)

- [通常オーバーライドされるメンバー関数](commonly-overridden-member-functions.md)

- [通常追加されるメンバー関数](commonly-added-member-functions.md)

## <a name="see-also"></a>関連項目

[ダイアログボックス](dialog-boxes.md)<br/>
[MFC でのダイアログ ボックスの操作](life-cycle-of-a-dialog-box.md)
