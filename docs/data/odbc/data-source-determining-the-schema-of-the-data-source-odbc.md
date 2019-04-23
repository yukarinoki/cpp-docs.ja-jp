---
title: データ ソース:データ ソース (ODBC) のスキーマを決定します。
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
ms.openlocfilehash: c419a3ac2d870e6a85675492ee6c9b726427a0e9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59040031"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>データ ソース:データ ソース (ODBC) のスキーマを決定します。

このトピックの内容は、MFC ODBC クラスに該当します。

データ メンバーを設定する、`CRecordset`オブジェクトの場合、接続しているデータ ソースのスキーマを把握する必要があります。 データ ソースのスキーマを決定するには、データ ソース内のテーブルの一覧、各テーブルの列で、各列のデータ型の一覧と、インデックスの有無を取得する必要があります。

## <a name="see-also"></a>関連項目

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[データ ソース:接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)