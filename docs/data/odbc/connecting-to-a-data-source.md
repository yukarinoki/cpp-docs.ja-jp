---
description: 詳細については、「データソースへの接続」を参照してください。
title: データ ソースへの接続
ms.date: 11/04/2016
helpviewer_keywords:
- database connections [C++], ODBC
- ODBC connections [C++], using
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
ms.openlocfilehash: 3bc5436a678d39682b89d82dd7f3ab90eb6f5bb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295121"
---
# <a name="connecting-to-a-data-source"></a>データ ソースへの接続

ODBC データソースは、データの特定のセット、そのデータにアクセスするために必要な情報、およびデータソースの場所であり、データソース名を使用して記述できます。 プログラムの観点から見ると、データソースには、データ、DBMS、ネットワーク (存在する場合)、および ODBC が含まれています。

データソースによって提供されるデータにアクセスするには、まず、プログラムがデータソースへの接続を確立する必要があります。 すべてのデータアクセスは、その接続を介して管理されます。

データソース接続は、 [CDatabase](../../mfc/reference/cdatabase-class.md)クラスによってカプセル化されます。 `CDatabase`オブジェクトがデータソースに接続されている場合、次のことができます。

- テーブルまたはクエリからレコードを選択するレコード [セット](../../mfc/reference/crecordset-class.md)を構築します。

- データソースが必要なレベルのトランザクションをサポートしている場合は、 [トランザクション](../../data/odbc/transaction-odbc.md)を管理して、すべての更新を一度にデータソースにコミットする (または、データソースが変更されないようにトランザクション全体をロールバックする) ことができます。

- [SQL](../../data/odbc/sql.md)ステートメントを直接実行します。

データソース接続の操作が完了したら、オブジェクトを閉じて、そのオブジェクトを破棄するか、 `CDatabase` 新しい接続に再利用します。 データソース接続の詳細については、「 [データソース (ODBC)](../../data/odbc/data-source-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ODBC と MFC](../../data/odbc/odbc-and-mfc.md)
