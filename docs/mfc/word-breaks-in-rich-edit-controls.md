---
title: リッチ エディット コントロールでのワード区切り |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f012897d968d108cb366126fc38992ff1dd11d0a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424613"
---
# <a name="word-breaks-in-rich-edit-controls"></a>リッチ エディット コントロールでのワード区切り

リッチ エディット コントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md))「という単語区切りプロシージャ」という名前の関数を呼び出して単語の区切り記号を検索し、行を壊すことを決定します。 コントロールは、ctrl キーを押しながら左と CTRL + → キーの組み合わせを処理するときに、ワード ラップ操作の実行時にこの情報を使用します。 アプリケーションは、単語区切りの情報を取得し、特定の文字がある行を決定する既定単語区切りプロシージャを置換するリッチ エディット コントロールにメッセージが送信できます。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

