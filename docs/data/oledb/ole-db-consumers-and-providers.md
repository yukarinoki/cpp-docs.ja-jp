---
title: OLE DB コンシューマーとプロバイダー |Microsoft ドキュメント
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
ms.openlocfilehash: 170f45a3581846dc588abf06aec170d66aa0d545
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-consumers-and-providers"></a>OLE DB コンシューマーとプロバイダー
OLE DB アーキテクチャでは、コンシューマーとプロバイダーのモデルを使用します。 コンシューマーは、データの要求を行います。 プロバイダーは、表形式でデータを配置して、コンシューマーに返すによってこれらの要求に応答します。 コンシューマーが行う任意の呼び出しは、プロバイダーに実装する必要があります。  
  
 技術的な定義で、コンシューマーは、システムまたはアプリケーション コード (OLE DB コンポーネント必ずしも) OLE DB インターフェイスを介してデータにアクセスします。 プロバイダーでは、インターフェイスを実装します。 したがって、プロバイダーは、データへのアクセスをカプセル化し、その他のオブジェクト (つまり、消費者) に公開する OLE DB インターフェイスを実装する任意のソフトウェア コンポーネントです。  
  
 コンシューマーが OLE DB インターフェイスのメソッドを呼び出しての役割の観点からOLE DB プロバイダーでは、必要な OLE DB インターフェイスを実装します。  
  
 OLE DB では、これらのロールはないため常に意味では、n 層の場合に特に条項クライアントとサーバーを回避できます。 コンシューマーは、別のコンポーネントを処理する層のコンポーネントであることが、それを呼び出すクライアント コンポーネントことは複雑になる場合。 また、プロバイダーもサーバーよりもデータベース ドライバーなどよりは機能します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)