---
title: OLE DB プログラミング
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB [C++]
- data access [C++], OLE DB programming
- OLE DB [C++], about OLE DB
ms.assetid: 52a80d66-17a9-43a1-9b90-392ae43cea2b
ms.openlocfilehash: 59bee1c204d2f101d8175ff42c78ca4bbdcaeb4c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523144"
---
# <a name="ole-db-programming"></a>OLE DB プログラミング

Microsoft OLE DB は、レガシ テクノロジです。新しいアプリケーションのリンクされた SQL サーバーの必要なデータ アクセス API になります。 その他のすべての新しいアプリケーションでは、ODBC を使用する必要があります。 SQL Server の現在の OLE DB プロバイダーでは、SQLNCLI11 です。DLL です。 プロバイダーは SQL Server 2016 で引き続き出荷されています。 このドキュメントは、OLE DB を既に使用している既存のアプリケーションを保持している開発者を対象としています。

OLE DB テンプレートは、一般的に使用される多数の OLE DB インターフェイスを実装するクラスを提供して、高性能な OLE DB データベース テクノロジを使いやすくする C++ テンプレートです。 このテンプレート ライブラリはコンシューマー テンプレートとプロバイダー テンプレートに分かれています。

Visual C++ には OLE DB のスターター アプリケーションを作成するためのウィザードのサポートもあります。

また、OLE DB コンシューマー テンプレートを実装するのに属性を使用できます。

|詳細情報|参照トピック|
|-------------------------|---------|
|OLE DB コンシューマー テンプレートの使用方法 (概念説明のトピック)|[OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)|
|OLE DB プロバイダー テンプレートの使用方法 (概念説明のトピック)|[OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)|
|OLE DB テンプレート クラスおよびマクロ|[OLE DB テンプレート リファレンス](../../data/oledb/ole-db-templates.md)(Visual C)|
|OLE DB コンシューマー属性|[OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)|
|OLE DB インターフェイス|[OLE DB プログラマーズ リファレンス](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming(v%3dvs.85))(では、Windows SDK)|
|OLE DB テンプレート サンプル|[OLE DB テンプレート サンプル](https://github.com/Microsoft/VCSamples)|
|データ アクセス プログラミングの概要 (Visual C++)|[データ アクセス プログラミング](../../data/data-access-programming-mfc-atl.md)|
|ODBC の概念説明のトピック|[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)|

## <a name="see-also"></a>関連項目

[データ アクセス](../data-access-in-cpp.md)