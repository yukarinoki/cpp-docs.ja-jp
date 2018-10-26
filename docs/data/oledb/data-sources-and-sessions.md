---
title: データ ソースとセッション |Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
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
ms.openlocfilehash: 0a6cb4e27f8a248b0b90454acb782b3b8994abc4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056036"
---
# <a name="data-sources-and-sessions"></a>データ ソースとセッション

次の図への接続とデータ ソースへのアクセスをサポートするクラスを示します。 各クラスは、標準の OLE DB コンポーネントの実装に基づいています。

![データ ソースとセッション クラス](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")データ ソースとセッション クラス

クラスは、次のとおりです。

- [CDataSource](../../data/oledb/cdatasource-class.md)このクラスを作成し、OLE DB プロバイダー経由のデータ ソースへの接続を管理するデータ ソース オブジェクトをインスタンス化します。 データ ソースは、接続文字列の形式でデータ ソースのアドレスや認証情報などの情報です。

   いることに注意もヘルパー クラス[CEnumerator](../../data/oledb/cenumerator-class.md)はシステムに登録されている利用可能なプロバイダーの一覧を取得する任意の接続が確立される前に、よく使用します。 これにより、データ ソースとして、プロバイダーを選択することができます。 たとえば、**データ リンク プロパティ** ダイアログ ボックスでは、このクラスを使用して、プロバイダーの一覧を事前設定、**プロバイダー**タブ。同じですが、`SQLBrowseConnect`または`SQLDriverConnect`関数。

- [CSession](../../data/oledb/csession-class.md)このクラスは、データ ソースに単一のアクセスのセッションを表すセッション オブジェクトをインスタンス化します。 ただし、データ ソースで複数のセッションを作成できます。 セッションごとに、データ ソースからデータにアクセスするには、行セット、コマンド、およびその他のオブジェクトを作成できます。 セッションでは、トランザクションを処理します。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)