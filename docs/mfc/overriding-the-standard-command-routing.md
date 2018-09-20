---
title: 標準コマンド ルーティングのオーバーライド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33ee603f680919d69684ab94acfa0515d3ec6292
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439498"
---
# <a name="overriding-the-standard-command-routing"></a>標準のコマンド ルーティングのオーバーライド

まれなケースで標準フレームワークのルーティングのいくつかのバリエーションを実装する必要がありますとオーバーライドできます。 つまり、1 つまたは複数のクラスでオーバーライドすることでルーティングを変更する`OnCmdMsg`それらのクラスでします。 そのための操作を行います。

- クラスには、既定以外のオブジェクトを渡す順序を中断します。

- 新しい既定以外のオブジェクトまたはコマンド ターゲットでさらにコマンドを渡すこと可能性があります。

ルーティングにいくつかの新しいオブジェクトを挿入する場合、クラスは、コマンド ターゲット クラスである必要があります。 オーバーライド元のバージョンで`OnCmdMsg`、オーバーライドしているバージョンを呼び出してください。 参照してください、 [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg)クラスのメンバー関数`CCmdTarget`で、 *MFC リファレンス*のようなクラスのバージョンと`CView`と`CDocument`例については、指定されたソース コードにします。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

