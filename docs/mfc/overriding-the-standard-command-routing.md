---
title: 標準コマンド ルーティングのオーバーライド |Microsoft ドキュメント
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
ms.openlocfilehash: 58156f6d1c361c24dc6cf04a9208157d614f91a8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929011"
---
# <a name="overriding-the-standard-command-routing"></a>標準のコマンド ルーティングのオーバーライド
まれなケースで、標準的なフレームワークのルーティングのいくつかのバリエーションを実装する必要がありますとオーバーライドできます。 つまり、オーバーライドすることで、1 つまたは複数のクラスでルーティングを変更する`OnCmdMsg`それらのクラスです。 そのための操作を行います。  
  
-   クラスには、既定以外のオブジェクトに渡す順序を中断します。  
  
-   またはコマンド ターゲットで新しい既定以外のオブジェクトでさらにコマンドを渡すこと可能性があります。  
  
 ルーティングにいくつかの新しいオブジェクトを挿入する場合、そのクラスは、コマンド ターゲット クラスをする必要があります。 オーバーライド元のバージョンの`OnCmdMsg`、オーバーライドしているバージョンを呼び出してください。 参照してください、 [OnCmdMsg](../mfc/reference/ccmdtarget-class.md#oncmdmsg)クラスのメンバー関数`CCmdTarget`で、 *『 MFC リファレンス*とバージョンのようなクラスを`CView`と`CDocument`例については、指定されたソース コードにします。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)

