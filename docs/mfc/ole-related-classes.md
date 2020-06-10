---
title: OLE 関連クラス
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
ms.openlocfilehash: 6f6db6ce133b440a5ed86e7c1642396888744540
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84621030"
---
# <a name="ole-related-classes"></a>OLE 関連クラス

これらのクラスは、例外からファイルの入力と出力まで、さまざまなサービスを提供します。

[COleObjectFactory](reference/coleobjectfactory-class.md)<br/>
他のコンテナーから要求されたときに項目を作成するために使用されます。 このクラスは、など、より具体的な種類のファクトリの基底クラスとして機能し `COleTemplateServer` ます。

[COleMessageFilter](reference/colemessagefilter-class.md)<br/>
OLE ライトウェイトリモートプロシージャ呼び出し (LRPC) を使用して同時実行を管理するために使用します。

[COleStreamFile](reference/colestreamfile-class.md)<br/>
は、COM インターフェイスを使用して、 `IStream` `CFile` 複合ファイルにアクセスできるようにします。 このクラス (から派生 `CFile` ) を使用すると、MFC のシリアル化で OLE 構造化ストレージを使用できます。

[CRectTracker](reference/crecttracker-class.md)<br/>
インプレース項目の移動、サイズ変更、および再配置を可能にするために使用されます。

## <a name="see-also"></a>関連項目

[クラスの概要](class-library-overview.md)
