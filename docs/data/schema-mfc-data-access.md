---
title: スキーマ (MFC データ アクセス) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- structures [C++], database
- databases [C++], schema
- database schema [C++], about database schemas
- database schema [C++]
- schemas [C++], database
- structures [C++]
ms.assetid: 7d17e35f-1ccf-4853-b915-5b8c7a45b9ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 597b3870dbfc70b6e1ac392a45491ee0f1804c2f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50055426"
---
# <a name="schema--mfc-data-access"></a>スキーマ (MFC データ アクセス)

データベース スキーマは、データベース内のテーブルとデータベース ビューの現在の構造を記述するものです。 通常、ウィザードで生成されたコードでは、レコードセットからアクセスするテーブルのスキーマは変更されないことを想定しています。ただし、データベース クラスでは、ある程度のスキーマの変更 (バインドされていない列の追加、並べ替え、削除など) に対応できます。 テーブルが変更された場合は、そのテーブルのレコードセットを手動で更新し、アプリケーションを再コンパイルする必要があります。

ウィザードで生成されるコードを補うことで、コンパイル時にスキーマの詳細が不明なデータベースが処理されるようにできます。 詳細については、次を参照してください。[レコード セット: データ列を動的にバインド (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)します。

## <a name="see-also"></a>関連項目

[データ アクセス プログラミング (MFC/ATL)](../data/data-access-programming-mfc-atl.md)<br/>
[SQL](../data/odbc/sql.md)<br/>
[レコードセット (ODBC)](../data/odbc/recordset-odbc.md)