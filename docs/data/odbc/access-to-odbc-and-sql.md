---
title: ODBC や SQL へのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4635d482a08c486c1cf3259ae642fd82eb4bae82
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055945"
---
# <a name="access-to-odbc-and-sql"></a>ODBC や SQL へのアクセス

Microsoft Foundation Class ライブラリでは、Windows API 呼び出しの多くをカプセル化し、まだする任意の Windows API 関数を直接呼び出すことができます。 データベース クラスでは、ODBC API に関して同様の柔軟性を提供します。 データベース クラスをシールドすると、ODBC の複雑さの多くが、中には、任意の場所から直接 ODBC API 関数を呼び出すことができます、プログラムでします。

同様に、データベース クラスからも保護では多くの作業をしなくて[SQL](../../data/odbc/sql.md)、する場合は SQL を直接使用することができます。 レコード セット オブジェクトをカスタマイズするには、カスタムの SQL ステートメント (または既定のステートメントの一部を設定) を渡すことによって、レコード セットを開くとします。 使用して直接 SQL 呼び出しを行うことができます、 [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)クラスのメンバー関数[CDatabase](../../mfc/reference/cdatabase-class.md)します。

詳細については、次を参照してください。 [ODBC: を呼び出す ODBC API 関数直接](../../data/odbc/odbc-calling-odbc-api-functions-directly.md)と[SQL: を行う直接 SQL 呼び出し (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)します。

## <a name="see-also"></a>関連項目

[ODBC と MFC](../../data/odbc/odbc-and-mfc.md)