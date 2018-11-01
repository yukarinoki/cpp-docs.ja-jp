---
title: 'データ ソース : データ ソースのスキーマの判定 (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
ms.openlocfilehash: ed6500c5718cf90b39600b12659a3090fe9532ce
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580763"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>データ ソース : データ ソースのスキーマの判定 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。

データ メンバーを設定する、`CRecordset`オブジェクトの場合、接続しているデータ ソースのスキーマを把握する必要があります。 データ ソースのスキーマを決定するには、データ ソース内のテーブルの一覧、各テーブルの列で、各列のデータ型の一覧と、インデックスの有無を取得する必要があります。

## <a name="see-also"></a>関連項目

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)