---
title: OLE DB コンシューマーとプロバイダー
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
ms.openlocfilehash: 65e4cf9dcade897a346e8f9bbc1985f9edede78e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443395"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB コンシューマーとプロバイダー

OLE DB アーキテクチャでは、コンシューマーとプロバイダーのモデルを使用します。 コンシューマーは、データの要求を行います。 プロバイダーは、表形式でデータを配置して、コンシューマーに返すことによって、これらの要求に応答します。 コンシューマーが行うすべての呼び出しは、プロバイダーで実装する必要があります。

技術的には定義されている、コンシューマーは、システムまたはアプリケーション コード (OLE DB コンポーネント必ずしも) OLE DB インターフェイスを介してデータにアクセスします。 インターフェイスは、プロバイダーで実装されます。 したがってプロバイダーは、データへのアクセスをカプセル化し、その他のオブジェクト (つまり、消費者) に公開する OLE DB インターフェイスを実装するソフトウェア コンポーネントです。

コンシューマーが OLE DB インターフェイスのメソッドを呼び出してロールについては、OLE DB プロバイダーでは、必要な OLE DB インターフェイスを実装します。

OLE DB では、これらのロールはありません、n 層の場合に特に意味を必ずため、用語のクライアントとサーバーを回避できます。 コンシューマーは、別のコンポーネントを処理する層のコンポーネントである可能性があります、ため、クライアントを呼び出すコンポーネントはわかりにくいです。 また、プロバイダーを場合がありますサーバーよりもデータベース ドライバーのようにより動作します。

## <a name="see-also"></a>関連項目

[OLE DB プログラミング](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)