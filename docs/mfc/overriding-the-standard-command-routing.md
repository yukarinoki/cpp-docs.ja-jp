---
title: 標準のコマンド ルーティングのオーバーライド
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
ms.openlocfilehash: 680b185f8d68a834862bc0fe14bf6e7984effd65
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617721"
---
# <a name="overriding-the-standard-command-routing"></a>標準のコマンド ルーティングのオーバーライド

まれに、標準フレームワークルーティングの一部のバリエーションを実装する必要がある場合は、それをオーバーライドできます。 概念としては、これらのクラスでをオーバーライドすることによって、1つまたは複数のクラスのルーティングを変更し `OnCmdMsg` ます。 次の手順を実行します。

- クラスで、既定以外のオブジェクトに渡す順序を分割します。

- 新しい既定以外のオブジェクトまたはコマンドターゲットでは、コマンドがに渡される場合があります。

ルーティングに新しいオブジェクトを挿入する場合、そのクラスはコマンドターゲットクラスである必要があります。 のオーバーライドバージョンでは `OnCmdMsg` 、オーバーライドしているバージョンを必ず呼び出してください。 例については、MFC リファレンスのクラスの[OnCmdMsg](reference/ccmdtarget-class.md#oncmdmsg)メンバー関数と、指定され `CCmdTarget` *MFC Reference* `CView` `CDocument` たソースコード内のおよびなどのクラスのバージョンを参照してください。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)
