---
title: データ ソースとセッション |Microsoft Docs
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
ms.openlocfilehash: dfa91db63aaf0266fa6fef7c0b07210575dc70d8
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39339829"
---
# <a name="data-sources-and-sessions"></a>データ ソースとセッション
次の図への接続とデータ ソースへのアクセスをサポートするクラスを示します。 各クラスは、標準の OLE DB コンポーネントの実装に基づいています。  
  
 ![データ ソースとセッション クラス](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
データ ソースとセッション クラス  
  
 クラスは、次のとおりです。  
  
-   [CDataSource](../../data/oledb/cdatasource-class.md)このクラスを作成し、OLE DB プロバイダー経由のデータ ソースへの接続を管理するデータ ソース オブジェクトをインスタンス化します。 データ ソースは、接続文字列の形式でデータ ソースのアドレスや認証情報などの情報です。  
  
     いることに注意もヘルパー クラス[CEnumerator](../../data/oledb/cenumerator-class.md)はシステムに登録されている利用可能なプロバイダーの一覧を取得する任意の接続が確立される前に、よく使用します。 これにより、データ ソースとして、プロバイダーを選択することができます。 たとえば、**データ リンク プロパティ** ダイアログ ボックスでは、このクラスを使用して、プロバイダーの一覧を事前設定、**プロバイダー**タブ。同じになります、`SQLBrowseConnect`または`SQLDriverConnect`関数。  
  
-   [CSession](../../data/oledb/csession-class.md)このクラスは、データ ソースに単一のアクセスのセッションを表すセッション オブジェクトをインスタンス化します。 ただし、データ ソースで複数のセッションを作成できます。 セッションごとに、データ ソースからデータにアクセスするには、行セット、コマンド、およびその他のオブジェクトを作成できます。 セッションでは、トランザクションを処理します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)