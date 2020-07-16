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
ms.openlocfilehash: e1cb5df4a93fc642ccf4d500a5eb93690b0b3d75
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2020
ms.locfileid: "86403824"
---
# <a name="odbc-calling-odbc-api-functions-directly"></a>ODBC: ODBC API 関数の直接呼び出し

データベースクラスは、ODBC よりも[データソース](../../data/odbc/data-source-odbc.md)に対してより単純なインターフェイスを提供します。 このため、クラスは、すべての ODBC API をカプセル化するわけではありません。 クラスの機能の外部にある機能については、ODBC API 関数を直接呼び出す必要があります。 たとえば、ODBC カタログ関数 (、、など) を直接呼び出す必要があり `::SQLColumns` `::SQLProcedures` `::SQLTables` ます。

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

ODBC API 関数を直接呼び出すには、フレームワークを使用せずに呼び出しを行う場合と同じ手順を実行する必要があります。 これらの手順は次のとおりです。

- 呼び出しが返すすべての結果に対してストレージを割り当てます。

- `HDBC` `HSTMT` 関数のパラメーターシグネチャに応じて、ODBC またはハンドルを渡します。 [AFXGetHENV](../../mfc/reference/database-macros-and-globals.md#afxgethenv)マクロを使用して、ODBC ハンドルを取得します。

   メンバー変数 `CDatabase::m_hdbc` と `CRecordset::m_hstmt` は使用可能であるため、自分で割り当てたり初期化したりする必要はありません。

- 場合によっては、メイン呼び出しの準備またはフォローアップのために、追加の ODBC 関数を呼び出すことができます。

- 完了したら、ストレージの割り当てを解除します。

これらの手順の詳細については、 [ODBC プログラマーズリファレンス](/sql/odbc/reference/odbc-programmer-s-reference)を参照してください。

これらの手順に加えて、関数の戻り値をチェックするための追加の手順を実行し、プログラムが非同期呼び出しの完了を待機していないことを確認する必要があります。 これらの最後の手順は、AFX_SQL_ASYNC と AFX_SQL_SYNC マクロを使用して簡単に行うことができます。 詳細については、「 [MFC マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)」を参照してください。

## <a name="see-also"></a>関連項目

[ODBC の基礎](../../data/odbc/odbc-basics.md)
