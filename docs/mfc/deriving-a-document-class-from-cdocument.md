---
title: CDocument からのドキュメント クラスの派生
ms.date: 11/04/2016
helpviewer_keywords:
- CDocument class [MFC], deriving from
- classes [MFC], deriving from CDocument
- document objects [MFC], derived
- derived classes [MFC], functions often overridden
- document classes [MFC], functions often overridden
ms.assetid: e6a198e0-9799-43c0-83c5-04174d8b532c
ms.openlocfilehash: 042ba7adc8d36e57a714e03ec67c1c0f22b4da78
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496123"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument からのドキュメント クラスの派生

ドキュメントでは、含めることがおよびアプリケーションのデータを管理します。 MFC アプリケーション ウィザードで提供されるドキュメント クラスを使用するには、次の操作を行う必要があります。

- クラスを派生`CDocument`ドキュメントの種類ごとにします。

- 各ドキュメントのデータを格納するメンバー変数を追加します。

- オーバーライド`CDocument`の`Serialize`ドキュメント クラスのメンバー関数。 `Serialize` ディスクと、ドキュメントのデータを読み書きします。

## <a name="other-document-functions-often-overridden"></a>オーバーライドされた多くの場合、その他のドキュメント関数

その他をオーバーライドすることも`CDocument`メンバー関数。 具体的には、オーバーライドする必要があります[でも実質的](../mfc/reference/cdocument-class.md#onnewdocument)と[かまいません](../mfc/reference/cdocument-class.md#onopendocument)ドキュメントのデータ メンバーを初期化するために、 [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents)を破棄するにはデータを動的に割り当てられます。 オーバーライド可能なメンバーについては、クラスを参照してください。 [CDocument](../mfc/reference/cdocument-class.md)で、 *MFC リファレンス*します。

## <a name="see-also"></a>関連項目

[ドキュメントの使い方](../mfc/using-documents.md)

