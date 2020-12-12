---
description: '詳細情報: リッチエディットコントロールでのワード区切り'
title: リッチ エディット コントロールでのワード区切り
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], word breaks in
- word breaks
- breaking words in CRichEditCtrl
- rich edit controls [MFC], word breaks in
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
ms.openlocfilehash: 662a6b8441c4a9041a539acdabcab74f12d52782
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172714"
---
# <a name="word-breaks-in-rich-edit-controls"></a>リッチ エディット コントロールでのワード区切り

リッチエディットコントロール ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)) は、"単語区切りプロシージャ" と呼ばれる関数を呼び出して、単語間の区切り記号を検索し、行を改行できる場所を特定します。 コントロールは、ワードラップ操作を実行するときと、CTRL + LEFT キーと CTRL + RIGHT キーの組み合わせを処理するときに、この情報を使用します。 アプリケーションは、リッチエディットコントロールにメッセージを送信して、既定の単語区切りプロシージャを置き換えたり、単語区切りの情報を取得したり、特定の文字がどの行に含まれているかを判断したりすることができます。

## <a name="see-also"></a>関連項目

[CRichEditCtrl の使い方](../mfc/using-cricheditctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
