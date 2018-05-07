---
title: OLE DB プログラミングの概要 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fdeca20ad97a09f9d5862fa43be680a2f907405f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-programming-overview"></a>OLE DB プログラミングの概要
OLE DB は、高パフォーマンス、COM ベース データベース テクノロジです。 格納されている形式に関係なくデータにアクセスする一般的な方法を提供します。 一般的に、ビジネスの現場では、大量の情報が企業データベースの外部に格納されています。 このような情報は、ファイル システム (FAT や NTFS など)、インデックス付きのシーケンシャル ファイル、パーソナル データベース (Access など)、スプレッドシート (Excel など)、プロジェクト プランニング アプリケーション (Project など)、および電子メール (Outlook など) に含まれています。 OLE DB をデータ ストアがある OLE DB プロバイダーにある限り、同じ方法であらゆる種類のデータ ストアにアクセスできます。
  
 OLE DB を使用すると、DBMS かどうかにかかわらず、多様なデータ ソースにアクセスするアプリケーションを開発できます。 OLE DB では、特定のデータ ソースに適した DBMS 機能をサポートする COM インターフェイスを使用することにより、汎用アクセスが可能になります。 COM では、データ ソース間だけでなく、ほかのアプリケーションとの間でも、サービスおよび最大化された相互運用性の不要な二重化が削減されます。  
  
## <a name="benefits-of-com"></a>COM の利点  
 このような場合に COM が役に立ちます。 OLE DB は、COM インターフェイスのセットです。 インターフェイスの統一されたセットを通じてデータにアクセスすることにより、相互に協調するコンポーネントのマトリックスとしてデータベースを編成できます。  
  
 COM の仕様に基づき、OLE DB は、DBMS 機能の一貫性があり再利用できる部分を分解してカプセル化する、拡張可能で保守性の高いインターフェイスの集合を定義します。 これらのインターフェイスは、行コンテナー、クエリ プロセッサ、トランザクション コーディネーターなどの DBMS コンポーネントの境界を定義し、多様な情報源への統一されたトランザクション アクセスを可能にします。  
 
  
## <a name="see-also"></a>関連項目  
 [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)   
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB テンプレート](../../data/oledb/ole-db-templates.md)