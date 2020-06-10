---
title: ドキュメントでのコマンドの処理
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], in document class
- command handling [MFC]
- documents [MFC], message maps
- message handling [MFC], WM_COMMAND messages
- command handling [MFC], commands in documents
- documents [MFC], handling messages in
ms.assetid: c7375584-27af-4275-b2fd-afea476785d0
ms.openlocfilehash: ed2ef635437408cacfd600d6cdba4b3731d575b4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625740"
---
# <a name="handling-commands-in-the-document"></a>ドキュメントでのコマンドの処理

ドキュメントクラスでは、メニュー項目、ツールバーボタン、またはアクセラレータキーによって生成される特定のコマンドを処理することもできます。 既定では、 `CDocument` シリアル化を使用して、[ファイル] メニューの [保存] と [名前を付けて保存] コマンドを処理します。 データに影響を与える他のコマンドは、ドキュメントのメンバー関数によって処理されることもあります。 たとえば、Scribble プログラムでは、クラスは `CScribDoc` [すべてクリア] を編集するためのハンドラーを提供します。これにより、ドキュメントに現在格納されているすべてのデータが削除されます。 ドキュメントにはメッセージマップを含めることができますが、ビューとは異なり、ドキュメントでは標準の Windows メッセージだけを処理することはできません ( **WM_COMMAND**メッセージのみ、または "コマンド")。

## <a name="see-also"></a>関連項目

[ドキュメントの使い方](using-documents.md)
