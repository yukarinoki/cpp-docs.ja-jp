---
title: 'レコード セット: テーブル (ODBC) クラスの宣言 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, declaring class for tables
- recordsets, declaring classes for tables
ms.assetid: 3fe286c2-3f3d-493d-9d8c-762310939d08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 423ed9b97900777160818b7699f8dac7b81e38a8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057532"
---
# <a name="recordset-declaring-a-class-for-a-table-odbc"></a>レコードセット: テーブルにアクセスするレコードセット クラスの宣言 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

最も一般的なレコード セット クラスでは、1 つのテーブルを開きます。 1 つのテーブルのレコード セット クラスを宣言するには、使用、 [MFC ODBC コンシューマー ウィザード](../../mfc/reference/adding-an-mfc-odbc-consumer.md)から**クラスの追加**対応するレコード セット フィールド データ メンバーの名前を付け、各列を選択します。

レコード セットの他の用途は次のとおりです。

- 2 つ以上のテーブルを結合します。

- 定義済みのクエリの結果を格納しています。

## <a name="see-also"></a>関連項目

[レコードセット (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[レコードセット: レコードセットの生成と破棄 (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)<br/>
[レコードセット: 定義済みクエリを利用したクラスの宣言 (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-predefined-query-odbc.md)<br/>
[レコードセット: 結合 (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)