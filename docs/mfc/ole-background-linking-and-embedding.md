---
description: '詳細については、「OLE の背景: リンクと埋め込み」を参照してください。'
title: 'OLE 概要 : リンクと埋め込み'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE embedded items [MFC]
- item types [MFC], defined
- item types [MFC]
- OLE [MFC], linked items
- linked items (OLE) [MFC]
- embedded objects [MFC]
- OLE items [MFC], types
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
ms.openlocfilehash: 05bd51c11cadfc3220f23db9098db9f07703a814
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97112220"
---
# <a name="ole-background-linking-and-embedding"></a>OLE 概要 : リンクと埋め込み

コンテナーアプリケーションで [貼り付け] コマンドを使用すると、埋め込みコンポーネントまたは埋め込みアイテムを作成できます。 埋め込みアイテムのソースデータは、それを含む OLE ドキュメントの一部として格納されます。 このように、ワードプロセッサドキュメントのドキュメントファイルにはテキストを含めることができ、ビットマップ、グラフ、式、またはその他の種類のデータを含めることもできます。

OLE では、別のアプリケーションのデータを組み込む別の方法として、リンクコンポーネント、リンクされたアイテム、またはリンクを作成できます。 リンク項目を作成する手順は、埋め込み項目を作成する手順と似ていますが、[貼り付け] コマンドの代わりに [リンクの貼り付け] コマンドを使用する点が異なります。 埋め込みコンポーネントとは異なり、リンクコンポーネントは元のデータへのパスを格納します。これは多くの場合、別のファイルに格納されます。

たとえば、ワードプロセッサのドキュメントで作業しているときに、スプレッドシートのセルにリンクアイテムを作成すると、リンクアイテムのデータが元のスプレッドシートドキュメントに格納されます。 ワードプロセッサドキュメントには、アイテムを検索できる場所を指定する情報、つまり元のスプレッドシートドキュメントへのリンクが含まれています。 セルをダブルクリックすると、スプレッドシートアプリケーションが起動され、元のスプレッドシートドキュメントが格納されている場所から読み込まれます。

埋め込みまたはリンクされているすべての OLE 項目には、それを作成したアプリケーションに基づいて、型が関連付けられています。 たとえば、Microsoft ペイントブラシ項目は1種類の項目であり、Microsoft Excel 項目は別の種類です。 ただし、アプリケーションによっては、複数の項目の種類を作成できます。 たとえば、Microsoft Excel では、ワークシートアイテム、グラフアイテム、および macrosheet アイテムを作成できます。 これらの各項目は、クラス識別子または **CLSID** を使用してシステムによって一意に識別されます。

## <a name="see-also"></a>関連項目

[OLE の背景](ole-background.md)<br/>
[OLE の背景: コンテナーとサーバー](ole-background-containers-and-servers.md)<br/>
[コンテナー: クライアントアイテム](containers-client-items.md)<br/>
[サーバー: サーバー項目](servers-server-items.md)
