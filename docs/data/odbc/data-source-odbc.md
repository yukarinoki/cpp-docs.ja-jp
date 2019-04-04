---
title: データ ソース (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: df61ca28a1a5c7fb1f2096f2cc22654794f5dbdc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469798"
---
# <a name="data-source-odbc"></a>データ ソース (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

データベース用語では、データ ソースは、データの集合、そのデータにアクセスするための情報、およびデータ ソースの位置で構成され、データ ソース名で参照できます。 クラスを使用する[CDatabase](../../mfc/reference/cdatabase-class.md)、データ ソースは、Open Database Connectivity (ODBC) の管理者によって設定されているいずれかを指定する必要があります。 データ ソースの例には、ネットワークまたはローカル ディレクトリ内の Microsoft Access ファイルの間で、Microsoft SQL Server で実行されているリモートのデータベースが含まれます。 アプリケーションからは、ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでもアクセスできます。

アプリケーションでは、同時に複数のデータ ソースをアクティブにし、各データ ソースをそれぞれ別の `CDatabase` オブジェクトで表すことができます。 また、どのデータ ソースにも同時に複数の接続を確立できます。 インストールされている ODBC ドライバーの機能によっては、ローカルだけでなくリモートのデータ ソースにも接続できます。 データ ソースと odbc データ ソース アドミニストレーターの詳細については、[ODBC](../../data/odbc/odbc-basics.md)と[ODBC アドミニストレーター](../../data/odbc/odbc-administrator.md)を参照してください。

データ ソースの詳細については、次のトピックを参照してください。

- [データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [データ ソース: データ ソースのスキーマの判定 (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>関連項目

[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)