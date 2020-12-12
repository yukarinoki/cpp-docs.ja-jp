---
description: '詳細情報: データソース (ODBC)'
title: データ ソース (ODBC)
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources, configuring
- CDatabase class, data source connections
- ODBC data sources
- configuring ODBC data sources
- ODBC data sources, represented by CDatabase
ms.assetid: b246721f-b9e1-49bd-a6c7-f348b8c3d537
ms.openlocfilehash: 655ba48414a733c6f2704d51c0e2bf1d4edf3ff4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255679"
---
# <a name="data-source-odbc"></a>データ ソース (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

データベース用語では、データ ソースは、データの集合、そのデータにアクセスするための情報、およびデータ ソースの位置で構成され、データ ソース名で参照できます。 [CDatabase](../../mfc/reference/cdatabase-class.md)クラスを使用するには、データソースが OPEN DATABASE CONNECTIVITY (ODBC) 管理者を使用して構成したものである必要があります。 データ ソースの例としては、ネットワーク上の Microsoft SQL Server で実行中のリモート データベースや、ローカル ディレクトリにある Microsoft Access のファイルなどがあります。 アプリケーションからは、ODBC ドライバーがあるデータ ソースならば、どのデータ ソースにでもアクセスできます。

アプリケーションでは、同時に複数のデータ ソースをアクティブにし、各データ ソースをそれぞれ別の `CDatabase` オブジェクトで表すことができます。 また、どのデータ ソースにも同時に複数の接続を確立できます。 インストールされている ODBC ドライバーの機能によっては、ローカルだけでなくリモートのデータ ソースにも接続できます。 データソースと ODBC 管理者の詳細については、「 [odbc](../../data/odbc/odbc-basics.md) および [odbc アドミニストレーター](../../data/odbc/odbc-administrator.md)」を参照してください。

データ ソースの詳細については、次のトピックを参照してください。

- [データソース: 接続の管理 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)

- [データソース: データソースのスキーマの決定 (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)

## <a name="see-also"></a>関連項目

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
