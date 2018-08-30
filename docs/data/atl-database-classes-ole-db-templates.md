---
title: ATL データベース クラス (OLE DB テンプレート) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 91cd06ea1d8ff697da6c4959fff34fdc3798dcfd
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218989"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL データベース クラス (OLE DB テンプレート)
Microsoft では、OLE DB では、一連のさまざまな情報源や形式のデータに同じ方法でアクセスを提供する COM インターフェイスの実装がいくつか提供します。  OLE DB は正式に非推奨とされます。このドキュメントでは、レガシ コードを保持している開発者のためです。 新しいアプリケーションは、ODBC を使用して、SQL データ ソースに接続する必要があります。
  
 OLE DB テンプレートは、OLE DB データベース テクノロジを使いやすく、一般的に使用される OLE DB インターフェイスの多くを実装するクラスを提供することで、ATL の C++ テンプレートです。  
  
 このテンプレート ライブラリには、2 つの部分が含まれています。  
  
-   [OLE DB コンシューマー テンプレート](../data/oledb/ole-db-consumer-templates-cpp.md)OLE DB (コンシューマー) のクライアント アプリケーションを実装するために使用します。  
  
-   [OLE DB プロバイダー テンプレート](../data/oledb/ole-db-provider-templates-cpp.md)OLE DB サーバー (プロバイダー) アプリケーションを実装するために使用します。  
  
 さらに、 [OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)OLE DB コンシューマーを作成する便利な手段を提供します。 OLE DB 属性では、作業用の OLE DB コンシューマーを作成する OLE DB コンシューマー テンプレートに基づくコードを挿入します。  
  
 MFC ライブラリに 1 つのクラスが含まれているメモ[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)コントロールでのデータベース レコードを表示します。 ビューが、フォーム ビューに直接接続されている、`CRowset`オブジェクトし、のフィールドが表示されます、`CRowset`ダイアログ テンプレートのコントロール内のオブジェクト。  
  
 詳細については、次を参照してください。 [OLE DB プログラミング](../data/oledb/ole-db-programming.md)と[OLE DB プログラマ ガイド](http://go.microsoft.com/fwlink/p/?linkid=121548)します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマーの作成](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB プロバイダーの作成](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB プロバイダー テンプレート リファレンス](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB テンプレート サンプル](https://msdn.microsoft.com/08958863-0b5f-41ad-ae99-fca7440c553c)