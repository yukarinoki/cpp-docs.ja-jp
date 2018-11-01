---
title: ドキュメントとビューの後処理
ms.date: 11/04/2016
helpviewer_keywords:
- views [MFC], cleaning up
- documents [MFC], cleaning up
- documents [MFC], closing
ms.assetid: 0c454db2-3644-434d-9e53-8108a7aedfe1
ms.openlocfilehash: 1357a02379a848af23a6f78dee29e5b6adc1efcc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653896"
---
# <a name="cleaning-up-documents-and-views"></a>ドキュメントとビューの後処理

フレームワークが呼び出す最初、ドキュメントが閉じている間、その[DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)メンバー関数。 ドキュメントの操作の実行中にヒープにメモリを割り当てた場合`DeleteContents`割り当てを解除することをお勧めします。

> [!NOTE]
>  ドキュメント データをドキュメントのデストラクターで割り当ては解除する必要があります。 SDI アプリケーションの場合は、ドキュメント オブジェクトを再利用する可能性があります。

ヒープに割り当てられたメモリを解放するビューのデストラクターをオーバーライドできます。

## <a name="see-also"></a>関連項目

[ドキュメントとビューの初期化と後処理](../mfc/initializing-and-cleaning-up-documents-and-views.md)

