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
ms.openlocfilehash: 399230446977636cc8769efe32b8f86fad466b83
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616118"
---
# <a name="deriving-a-document-class-from-cdocument"></a>CDocument からのドキュメント クラスの派生

ドキュメントには、アプリケーションのデータが格納され、管理されます。 MFC アプリケーションウィザードで提供されるドキュメントクラスを使用するには、次の操作を行う必要があります。

- ドキュメントの種類ごとにからクラスを派生させ `CDocument` ます。

- 各ドキュメントのデータを格納するためのメンバー変数を追加します。

- `CDocument` `Serialize` ドキュメントクラスのメンバー関数をオーバーライドします。 `Serialize`ディスクとの間でドキュメントのデータを読み書きします。

## <a name="other-document-functions-often-overridden"></a>多くの場合、オーバーライドされるその他のドキュメント関数

他のメンバー関数をオーバーライドすることもでき `CDocument` ます。 特に、多くの場合、 [OnNewDocument](reference/cdocument-class.md#onnewdocument)と[onopendocument](reference/cdocument-class.md#onopendocument)をオーバーライドしてドキュメントのデータメンバーを初期化し、 [DeleteContents](reference/cdocument-class.md#deletecontents)を使用して動的に割り当てられたデータを破棄する必要があります。 オーバーライド可能なメンバーの詳細については、 *MFC リファレンス*の「 [CDocument](reference/cdocument-class.md)クラス」を参照してください。

## <a name="see-also"></a>関連項目

[ドキュメントの使い方](using-documents.md)
