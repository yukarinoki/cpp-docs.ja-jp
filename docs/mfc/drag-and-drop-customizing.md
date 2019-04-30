---
title: ドラッグ アンド ドロップします。カスタマイズ
ms.date: 11/04/2016
helpviewer_keywords:
- drag and drop [MFC], implementing in non-OLE applications
- drag and drop [MFC], customizing behavior
- drag and  [MFC], COleDataSource object
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], customizing behavior
ms.assetid: 03369d3e-46bf-4140-b58c-d0c9657cf38a
ms.openlocfilehash: b4749f8d45c962f8b9217e4c6367538d3e6a3608
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405951"
---
# <a name="drag-and-drop-customizing"></a>ドラッグ アンド ドロップします。カスタマイズ

ドラッグ アンド ドロップ機能の既定の実装では、ほとんどのアプリケーションにとって十分です。 ただし、一部のアプリケーションでは、この標準の動作を変更する必要があります。 この記事では、これらの既定値を変更するために必要な手順について説明します。 さらに、ドロップ ソースとしての複合ドキュメント サポートしていないアプリケーションを確立するために、この手法を使用することができます。

標準の OLE ドラッグ アンド ドロップ動作をカスタマイズするまたは非 OLE アプリケーションを作成する必要が、`COleDataSource`データを格納するオブジェクト。 ユーザーは、ドラッグ アンド ドロップ操作を起動するときに、コードを呼び出す必要があります、`DoDragDrop`ドラッグ アンド ドロップ操作をサポートする他のクラスの代わりにこのオブジェクトからの関数。

必要に応じて、作成、`COleDropSource`ドロップを制御し、変更する動作の種類に応じて、機能の一部をオーバーライドするオブジェクト。 このドロップ ソース オブジェクトに渡されます`COleDataSource::DoDragDrop`をこれらの関数の既定の動作を変更します。 これらのさまざまなオプションは、多くのアプリケーションでドラッグ アンド ドロップ操作をサポートする方法の柔軟性を許可します。 データ ソースの詳細については、記事を参照してください。[データ オブジェクトとデータ ソース (OLE)](../mfc/data-objects-and-data-sources-ole.md)します。

ドラッグ アンド ドロップ操作をカスタマイズするには、次の関数をオーバーライドすることができます。

|オーバーライド|カスタマイズするには|
|--------------|------------------|
|`OnBeginDrag`|どのドラッグの開始を呼び出した後`DoDragDrop`します。|
|`GiveFeedback`|ドロップの結果に、カーソルの外観などの視覚的フィードバック。|
|`QueryContinueDrag`|ドラッグ アンド ドロップ操作の終了。 この関数では、ドラッグ操作中に修飾子キーの状態を確認することができます。|

## <a name="see-also"></a>関連項目

[ドラッグ アンド ドロップ (OLE)](../mfc/drag-and-drop-ole.md)<br/>
[COleDropSource クラス](../mfc/reference/coledropsource-class.md)<br/>
[COleDataSource クラス](../mfc/reference/coledatasource-class.md)
