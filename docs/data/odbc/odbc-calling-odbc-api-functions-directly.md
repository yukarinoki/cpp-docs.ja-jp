---
title: 'ODBC: ODBC API を呼び出す関数を直接 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC API functions [C++], calling
- ODBC [C++], catalog functions
- ODBC API functions [C++]
- APIs [C++], calling
- ODBC classes [C++], vs. ODBC API
- direct ODBC API calls
- catalog functions (ODBC)
- catalog functions (ODBC), calling
- ODBC [C++], API functions
ms.assetid: 4295f1d9-4528-4d2e-bd6a-c7569953c7fa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 918ae8dd0249479cf8a99b1476e0beda5efc72f2
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059806"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 関数の直接呼び出し

データベース クラスに単純なインターフェイスを提供する、[データソース](../../data/odbc/data-source-odbc.md)ODBC よりもします。 その結果、クラスには、すべての ODBC API はカプセル化しません。 クラスの機能が含まれていない機能、ODBC API 関数を直接呼び出す必要があります。 たとえば、ODBC カタログ関数を呼び出す必要があります (`::SQLColumns`、 `::SQLProcedures`、 `::SQLTables`、およびその他) 直接します。

> [!NOTE]
>  ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

直接、ODBC API 関数を呼び出すには、framework なしの呼び出しを作成する場合は場合と同じ手順を実行する必要があります。 これらの手順します。

- 記憶域の割り当て用の呼び出しが返されます。

- ODBC を渡す`HDBC`または`HSTMT`関数のパラメーター シグネチャによって、処理します。 使用して、 [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv)マクロを ODBC ハンドルを取得します。

   メンバー変数`CDatabase::m_hdbc`と`CRecordset::m_hstmt`を利用できるよう、割り当ておよび自身を初期化する必要はありません。

- おそらく、フォロー アップの main 呼び出しを準備またはその他の ODBC 関数を呼び出します。

- 完了したときにストレージの割り当てを解除します。

次の手順の詳細については、次を参照してください。、[オープン データベース コネクティビティ (ODBC)](/previous-versions/windows/desktop/ms710252) MSDN ドキュメント内の SDK です。

この手順に加えて、関数の戻り値のチェック、プログラムが完了する非同期呼び出しを待機していないことを確認する追加の手順を実行する必要があります。 手順についてを使用して、これらの最後の手順を簡略化できます。 詳細については、次を参照してください。[マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)で、 *MFC リファレンス*します。

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)
