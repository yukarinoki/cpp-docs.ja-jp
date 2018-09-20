---
title: OLE 関連クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE classes [MFC]
- OLE [MFC], classes
ms.assetid: 2135cf54-1d9d-4e0e-91b4-943b3440effa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f43dadaa4aaefa677106710d1adbcdf0e60be59d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411314"
---
# <a name="ole-related-classes"></a>OLE 関連クラス

これらのクラスは、さまざまな例外からの入力と出力をファイルに至るまで、さまざまなサービスを提供します。

[COleObjectFactory](../mfc/reference/coleobjectfactory-class.md)<br/>
他のコンテナーから要求されたときに項目を作成するために使用します。 このクラスはファクトリなどの特定の種類の基本クラスとして機能`COleTemplateServer`します。

[COleMessageFilter](../mfc/reference/colemessagefilter-class.md)<br/>
同時実行と OLE ライトウェイト リモート プロシージャ コール (LRPC) を管理するために使用します。

[COleStreamFile](../mfc/reference/colestreamfile-class.md)<br/>
COM を使用して`IStream`インターフェイスを提供する`CFile`複合ファイルにアクセスします。 このクラス (から派生した`CFile`) OLE 構造化ストレージを使用する MFC のシリアル化を有効します。

[CRectTracker](../mfc/reference/crecttracker-class.md)<br/>
移動、サイズ変更、およびインプレース項目の方向を許可するために使用します。

## <a name="see-also"></a>関連項目

[クラスの概要](../mfc/class-library-overview.md)

