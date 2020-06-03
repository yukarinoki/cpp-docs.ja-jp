---
title: OLE 関連クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: dfcc07b3fbd0c5badce8e397f4d52bc7d8d3028c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447603"
---
# <a name="ole-related-classes"></a>OLE 関連クラス

これらのクラスは、例外からファイルの入力と出力まで、さまざまなサービスを提供します。

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
他のコンテナーから要求されたときに項目を作成するために使用されます。 このクラスは、`COleTemplateServer`を含む、より具体的な種類のファクトリの基底クラスとして機能します。

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
OLE ライトウェイトリモートプロシージャ呼び出し (LRPC) を使用して同時実行を管理するために使用します。

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
は COM `IStream` インターフェイスを使用して、複合ファイルへの `CFile` アクセスを提供します。 このクラス (`CFile`から派生) を使用すると、MFC のシリアル化で OLE 構造化ストレージを使用できます。

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
インプレース項目の移動、サイズ変更、および再配置を可能にするために使用されます。

## <a name="see-also"></a>参照

[クラスの概要](../mfc/class-library-overview.md)
