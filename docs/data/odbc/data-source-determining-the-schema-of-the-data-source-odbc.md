---
title: 'データ ソース: データ ソース (ODBC) のスキーマを判定する |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC data sources [C++], schema
- schemas [C++], data sources
- data sources [C++], determining schema
ms.assetid: 17284acb-eb10-4f27-9944-ad1d973c0b05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d9db21b7531f71ba40be64018b71c4e2e3e555e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064972"
---
# <a name="data-source-determining-the-schema-of-the-data-source-odbc"></a>データ ソース : データ ソースのスキーマの判定 (ODBC)

このトピックの内容は、MFC ODBC クラスに該当します。  
  
データ メンバーを設定する、`CRecordset`オブジェクトの場合、接続しているデータ ソースのスキーマを把握する必要があります。 データ ソースのスキーマを決定するには、データ ソース内のテーブルの一覧、各テーブルの列で、各列のデータ型の一覧と、インデックスの有無を取得する必要があります。  
  
## <a name="see-also"></a>関連項目  

[データ ソース (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[データ ソース: 接続 (ODBC)](../../data/odbc/data-source-managing-connections-odbc.md)