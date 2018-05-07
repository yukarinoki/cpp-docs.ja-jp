---
title: ATL データベース クラス (OLE DB テンプレート) |Microsoft ドキュメント
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
ms.openlocfilehash: fabced79232d17807d252da9dac5b066ddf69f25
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL データベース クラス (OLE DB テンプレート)
Microsoft では、OLE DB では、さまざまな情報源や形式でのデータへの統一されたアクセスを提供する COM インターフェイスのセットのいくつかの実装を提供します。  OLE DB は正式に廃止されました。このドキュメントは、レガシ コードを保持している開発者です。 新しいアプリケーションは、ODBC を使用して、SQL データ ソースに接続する必要があります。
  
 OLE DB テンプレートは、OLE DB データベース テクノロジを使いやすく、一般的に使用される OLE DB インターフェイスの多くを実装するクラスを提供することにより、ATL の C++ テンプレートです。  
  
 このテンプレート ライブラリには、2 つの部分が含まれています。  
  
-   [OLE DB コンシューマー テンプレート](../data/oledb/ole-db-consumer-templates-cpp.md)OLE DB クライアント (コンシューマー) アプリケーションを実装するために使用します。  
  
-   [OLE DB プロバイダー テンプレート](../data/oledb/ole-db-provider-templates-cpp.md)OLE DB サーバー (プロバイダー) アプリケーションを実装するために使用します。  
  
 さらに、 [OLE DB コンシューマー属性](../windows/ole-db-consumer-attributes.md)OLE DB コンシューマーを作成する便利な手段を提供します。 OLE DB 属性では、作業用の OLE DB コンシューマーを作成する OLE DB コンシューマー テンプレートに基づいたコードを挿入します。  
  
 MFC ライブラリに 1 つのクラスが含まれているメモ[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)コントロールにデータベース レコードを表示します。 ビューに直接接続されているフォーム ビュー、`CRowset`オブジェクト、およびのフィールドを表示、`CRowset`ダイアログ テンプレートのコントロール内のオブジェクト。  
  
 詳細については、次を参照してください。 [OLE DB プログラミング](../data/oledb/ole-db-programming.md)と[OLE DB プログラマ ガイド](http://go.microsoft.com/fwlink/p/?linkid=121548)です。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマーの作成](../data/oledb/creating-an-ole-db-consumer.md)   
 [OLE DB プロバイダーの作成](../data/oledb/creating-an-ole-db-provider.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB プロバイダー テンプレート リファレンス](../data/oledb/ole-db-provider-templates-reference.md)   
 [OLE DB テンプレート サンプル](http://msdn.microsoft.com/en-us/08958863-0b5f-41ad-ae99-fca7440c553c)