---
title: OLE DB コンシューマーとプロバイダー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, OLE DB data architecture
- OLE DB providers
- OLE DB consumers, OLE DB data architecture
- OLE DB consumers
- OLE DB, data model
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b37a06ec89f0e2e21c4332a480e58c605f0d161f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110719"
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB コンシューマーとプロバイダー

OLE DB アーキテクチャでは、コンシューマーとプロバイダーのモデルを使用します。 コンシューマーは、データの要求を行います。 プロバイダーは、表形式でデータを配置して、コンシューマーに返すことによって、これらの要求に応答します。 コンシューマーが行うすべての呼び出しは、プロバイダーで実装する必要があります。  
  
技術的には定義されている、コンシューマーは、システムまたはアプリケーション コード (OLE DB コンポーネント必ずしも) OLE DB インターフェイスを介してデータにアクセスします。 インターフェイスは、プロバイダーで実装されます。 そのため、プロバイダーは、データへのアクセスをカプセル化し、その他のオブジェクト (つまり、消費者) に公開する OLE DB インターフェイスを実装するソフトウェア コンポーネントです。  
  
コンシューマーが OLE DB インターフェイスのメソッドを呼び出しての役割の観点からOLE DB プロバイダーでは、必要な OLE DB インターフェイスを実装します。  
  
OLE DB では、これらのロールは常に意味を成しません、n 層の場合に特にため、用語のクライアントとサーバーを回避できます。 コンシューマーは、別のコンポーネントを処理する層のコンポーネントである可能性があります、ため、クライアントを呼び出すコンポーネントはわかりにくいです。 また、プロバイダーを場合がありますサーバーよりもデータベース ドライバーのようにより動作します。  
  
## <a name="see-also"></a>関連項目  

[OLE DB プログラミング](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)