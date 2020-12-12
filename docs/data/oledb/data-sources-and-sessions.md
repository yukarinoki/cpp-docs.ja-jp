---
description: 詳細については、「データソースとセッション」を参照してください。
title: データ ソースとセッション
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 352bce1140ef8aebdc198ad237f4a427d5f9c440
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287659"
---
# <a name="data-sources-and-sessions"></a>データ ソースとセッション

次の図は、データソースへの接続とデータソースへのアクセスをサポートするクラスを示しています。 各クラスは、標準の OLE DB コンポーネントの実装に基づいています。

![データソースとセッションクラス](../../data/oledb/media/vcdatasourcesessionclasses.gif "データ ソースとセッション クラス") <br/>
データ ソースとセッション クラス

クラスは次のとおりです。

- [CDataSource](../../data/oledb/cdatasource-class.md) このクラスは、データソースオブジェクトをインスタンス化します。このオブジェクトは、OLE DB プロバイダーを介してデータソースへの接続を作成し、管理します。 データソースは、データソースのアドレスや認証情報などの情報を接続文字列の形式で取得します。

   また、ヘルパークラス [CEnumerator](../../data/oledb/cenumerator-class.md) は、システムに登録されている使用可能なプロバイダーの一覧を取得するために接続が確立される前に頻繁に使用されることに注意してください。 これにより、プロバイダーをデータソースとして選択できます。 たとえば、[ **データリンクプロパティ** ] ダイアログボックスでは、このクラスを使用して [ **プロバイダー** ] タブでプロバイダーの一覧を設定します。 `SQLBrowseConnect` または関数に相当 `SQLDriverConnect` します。

- [CSession](../../data/oledb/csession-class.md) このクラスは、データソースへの単一のアクセスセッションを表すセッションオブジェクトをインスタンス化します。 ただし、データソースに対して複数のセッションを作成することができます。 各セッションに対して、データソースからデータにアクセスするための行セット、コマンド、およびその他のオブジェクトを作成できます。 セッションはトランザクションを処理します。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)
