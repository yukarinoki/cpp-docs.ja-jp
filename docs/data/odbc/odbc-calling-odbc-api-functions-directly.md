---
title: 'ODBC: ODBC API 関数の直接呼び出し'
ms.date: 11/04/2016
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
ms.openlocfilehash: 208749438f40eef746a638dd12373397c426d454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368663"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 関数の直接呼び出し

データベース クラスは、ODBC よりもデータ[ソース](../../data/odbc/data-source-odbc.md)へのインターフェイスを簡単に提供します。 その結果、クラスはすべての ODBC API をカプセル化しません。 クラスの機能の範囲外の機能については、ODBC API 関数を直接呼び出す必要があります。 たとえば、ODBC カタログ関数 (`::SQLColumns`、 、、`::SQLTables``::SQLProcedures`その他 ) を直接呼び出す必要があります。

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

ODBC API 関数を直接呼び出す場合は、フレームワークなしで呼び出しを行う場合と同じ手順を実行する必要があります。 彼らは次の手順を実行します。

- 呼び出しが返す結果に対してストレージを割り当てます。

- 関数のパラメーター `HDBC` `HSTMT`シグネチャに応じて、ODBC またはハンドルを渡します。 [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv)マクロを使用して、ODBC ハンドルを取得します。

   メンバー変数`CDatabase::m_hdbc`を`CRecordset::m_hstmt`使用して、これらを自分で割り当てて初期化する必要がないようにすることができます。

- おそらく、メインコールの準備またはフォローアップのために追加のODBC関数を呼び出します。

- 完了したら、記憶域の割り当てを解除します。

これらの手順の詳細については、MSDN ドキュメントの[オープン データベース接続 (ODBC)](/sql/odbc/microsoft-open-database-connectivity-odbc) SDK を参照してください。

これらの手順に加えて、関数の戻り値をチェックする追加の手順を実行し、非同期呼び出しの完了をプログラムが待機していないことを確認する必要があります。 AFX_SQL_ASYNCとAFX_SQL_SYNCマクロを使用すると、これらの最後の手順を簡略化できます。 詳細については *、「MFC リファレンス*」の[「マクロとグローバル」](../../mfc/reference/mfc-macros-and-globals.md)を参照してください。

## <a name="see-also"></a>関連項目

[ODBC の基本](../../data/odbc/odbc-basics.md)
