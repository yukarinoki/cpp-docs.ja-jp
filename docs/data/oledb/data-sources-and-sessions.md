---
title: データ ソースとセッション
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 0514f6a9285936c85608f08774c1d377fd72d6ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211056"
---
# <a name="data-sources-and-sessions"></a>データ ソースとセッション

次の図は、データソースへの接続とデータソースへのアクセスをサポートするクラスを示しています。 各クラスは、標準の OLE DB コンポーネントの実装に基づいています。

![データソースとセッションクラス](../../data/oledb/media/vcdatasourcesessionclasses.gif "データ ソースとセッション クラス") <br/>
データ ソースとセッション クラス

クラスは次のとおりです。

- [CDataSource](../../data/oledb/cdatasource-class.md)このクラスは、データソースオブジェクトをインスタンス化します。このオブジェクトは、OLE DB プロバイダーを介してデータソースへの接続を作成し、管理します。 データソースは、データソースのアドレスや認証情報などの情報を接続文字列の形式で取得します。

   また、ヘルパークラス[CEnumerator](../../data/oledb/cenumerator-class.md)は、システムに登録されている使用可能なプロバイダーの一覧を取得するために接続が確立される前に頻繁に使用されることに注意してください。 これにより、プロバイダーをデータソースとして選択できます。 たとえば、 **[データリンクプロパティ]** ダイアログボックスでは、このクラスを使用して **[プロバイダー]** タブでプロバイダーの一覧を設定します。これは、`SQLBrowseConnect` または `SQLDriverConnect` 関数に相当します。

- [CSession](../../data/oledb/csession-class.md)このクラスは、データソースへの単一のアクセスセッションを表すセッションオブジェクトをインスタンス化します。 ただし、データソースに対して複数のセッションを作成することができます。 各セッションに対して、データソースからデータにアクセスするための行セット、コマンド、およびその他のオブジェクトを作成できます。 セッションはトランザクションを処理します。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)
