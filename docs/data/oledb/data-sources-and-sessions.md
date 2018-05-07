---
title: データ ソースとセッション |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d93f6aba8e9fad27054c731d37e6df28b54eacda
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="data-sources-and-sessions"></a>データ ソースとセッション
次の図に接続して、データ ソースへのアクセスをサポートするクラスを示します。 各クラスは、標準の OLE DB コンポーネントの実装に基づいています。  
  
 ![データ ソースとセッション クラス](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
データ ソースとセッション クラス  
  
 クラスは、次のとおりです。  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md)このクラスのインスタンスを作成して、OLE DB プロバイダー経由のデータ ソースへの接続を管理するデータ ソース オブジェクトを作成します。 データ ソースは、接続文字列の形式でデータ ソースのアドレスや認証情報などの情報を取得します。  
  
     注目に値すヘルパー クラス[CEnumerator](../../data/oledb/cenumerator-class.md)はシステムに登録されている使用可能なプロバイダーの一覧を取得する任意の接続が確立される前に、よく使用します。 これにより、データ ソースとして、プロバイダーを選択できます。 たとえば、**データ リンク プロパティ** ダイアログ ボックスでは、このクラスを使用して、プロバイダーの一覧を事前設定、**プロバイダー**タブです。等価である、 **SQLBrowseConnect**または**SQLDriverConnect**関数。  
  
-   [CSession](../../data/oledb/csession-class.md)このクラスのインスタンスを作成、セッション オブジェクト、データ ソースに単一のアクセスのセッションを表します。 ただし、データ ソース内の複数のセッションを作成できます。 セッションごとに、データ ソースからデータにアクセスするには、行セット、コマンド、およびその他のオブジェクトを作成できます。 セッションは、トランザクションを処理します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)