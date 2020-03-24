---
title: ODBC と MFC
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC [C++], MFC
- connections [C++], databases
- connections [C++], data source
- databases [C++], connecting to
- data sources [C++], connecting to
- MFC [C++], ODBC and
- database connections [C++], MFC ODBC classes
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
ms.openlocfilehash: 94a3455324a52b789bcfcf192b698a3c42b37c00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213183"
---
# <a name="odbc-and-mfc"></a>ODBC と MFC

> [!NOTE]
>  MFC データベースクラスを使用するには、データソースに適した ODBC ドライバーが必要です。 最新 Microsoft ODBC driver for SQL Server は、 [MICROSOFT Odbc driver 13 for SQL Server](https://www.microsoft.com/download/details.aspx?id=50420)です。 ほとんどのデータベースベンダーは、Windows 用 ODBC ドライバーを提供しています。

このトピックでは、Microsoft Foundation Classes (MFC) ライブラリの ODBC ベースのデータベースクラスの主要な概念について説明し、クラスを連携させる方法の概要を示します。 ODBC と MFC の詳細については、次のトピックを参照してください。

- [データ ソースへの接続](connecting-to-a-data-source.md)

- [レコードの選択と操作](selecting-and-manipulating-records.md)

- [フォームでのデータの表示と操作](displaying-and-manipulating-data-in-a-form.md)

- [ドキュメントとビューの操作](working-with-documents-and-views.md)

- [ODBC や SQL へのアクセス](access-to-odbc-and-sql.md)

- [MFC ODBC クラスに関する詳細情報](further-reading-about-the-mfc-odbc-classes.md)

ODBC に基づく MFC データベースクラスは、ODBC ドライバーを使用できるすべてのデータベースへのアクセスを提供するように設計されています。 クラスでは ODBC が使用されるため、アプリケーションはさまざまなデータ形式とさまざまなローカル/リモート構成のデータにアクセスできます。 異なるデータベース管理システム (Dbms) を処理するために、特殊なケースコードを記述する必要はありません。 ユーザーは、アクセスするデータに適した ODBC ドライバーを持っている限り、プログラムを使用して、そこに格納されているテーブルのデータを操作できます。

## <a name="see-also"></a>参照

[ODBC (Open Database Connectivity)](open-database-connectivity-odbc.md)
