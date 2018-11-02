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
ms.openlocfilehash: d2f0a7271452ace9b9e06ff995af61881db4403c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50548955"
---
# <a name="handling-commands-in-the-document"></a>ドキュメントでのコマンドの処理

ドキュメント クラスには、メニュー項目、ツール バー ボタン、またはアクセラレータ キーによって生成される特定のコマンドも処理します。 既定では、`CDocument`保存を処理し、シリアル化を使用して [ファイル] メニュー コマンドの名前を付けて保存します。 その他のデータに影響を与えるコマンドは、ドキュメントのメンバー関数によっても処理があります。 たとえば、Scribble プログラムで、クラス`CScribDoc`編集のすべてのクリア コマンドは、ドキュメントに格納されているデータをすべて削除するハンドラーを提供します。 ドキュメントは、メッセージ マップを持つことができますが、ビューとは異なり、ドキュメントが標準の Windows メッセージを処理できません-のみ**WM_COMMAND**メッセージ、または「コマンド」。

## <a name="see-also"></a>関連項目

[ドキュメントの使い方](../mfc/using-documents.md)

