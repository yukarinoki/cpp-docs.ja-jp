---
description: 詳細については、「ODBC および SQL へのアクセス」を参照してください。
title: ODBC や SQL へのアクセス
ms.date: 11/04/2016
helpviewer_keywords:
- API calls [C++], calling DAO or ODBC directly
- Windows API [C++], calling from MFC
- ODBC API functions [C++]
- ODBC API functions [C++], calling from MFC
- SQL [C++], calling ODBC API functions
- ODBC [C++], API functions
ms.assetid: 5613d7dc-00b7-4646-99ae-1116c05c52b4
ms.openlocfilehash: 507e3a8e2d88c253f193de41be1a28ae0c5cba87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295147"
---
# <a name="access-to-odbc-and-sql"></a>ODBC や SQL へのアクセス

Microsoft Foundation Class ライブラリは多くの Windows API 呼び出しをカプセル化しますが、Windows API 関数を直接呼び出すこともできます。 データベースクラスを使用すると、ODBC API に関しても同じ柔軟性が得られます。 データベースクラスを使用すると、ODBC の複雑さの多くを防ぐことができますが、ODBC API 関数をプログラム内の任意の場所から直接呼び出すことができます。

同様に、データベースクラスを使用することによって [sql](../../data/odbc/sql.md)でも多くの作業を行う必要がありますが、必要に応じて sql を直接使用することもできます。 レコードセットを開くときに、レコードセットオブジェクトをカスタマイズするには、カスタム SQL ステートメント (または既定のステートメントの一部を設定する) を渡します。 また、 [CDatabase](../../mfc/reference/cdatabase-class.md)クラスの[ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)メンバー関数を使用して、SQL 呼び出しを直接行うこともできます。

詳細については、「 [odbc: ODBC API 関数の直接呼び出し](../../data/odbc/odbc-calling-odbc-api-functions-directly.md) 」および「 [SQL: Direct Sql 呼び出しの作成 (odbc)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ODBC と MFC](../../data/odbc/odbc-and-mfc.md)
