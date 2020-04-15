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
ms.openlocfilehash: 38a625c73a17ecae4d8adc61e8c56bc4bdda67f6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320080"
---
# <a name="odbc-and-mfc"></a>ODBC と MFC

> [!NOTE]
> MFC データベース クラスを使用するには、データ ソースに適した ODBC ドライバが必要です。 SQL サーバーの最後の ODBC[ドライバーは、SQL Server 用の ODBC ドライバー 13 です](https://www.microsoft.com/download/details.aspx?id=50420)。 ほとんどのデータベース ベンダーは、Windows 用の ODBC ドライバーを提供します。

ここでは、MFC (MFC) ライブラリの ODBC ベースのデータベース クラスの主要な概念を紹介し、クラスの連携の概要を説明します。 ODBC および MFC の詳細については、次のトピックを参照してください。

- [データ ソースへの接続](connecting-to-a-data-source.md)

- [レコードの選択と操作](selecting-and-manipulating-records.md)

- [フォームでのデータの表示と操作](displaying-and-manipulating-data-in-a-form.md)

- [ドキュメントとビューの操作](working-with-documents-and-views.md)

- [ODBC や SQL へのアクセス](access-to-odbc-and-sql.md)

- [MFC ODBC クラスに関する詳細情報](further-reading-about-the-mfc-odbc-classes.md)

ODBC に基づく MFC データベース クラスは、ODBC ドライバが使用できる任意のデータベースにアクセスできるように設計されています。 クラスは ODBC を使用するため、アプリケーションはさまざまなデータ形式と異なるローカル/リモート構成のデータにアクセスできます。 異なるデータベース管理システム (DBMS) を処理するために、特殊なコードを記述する必要はありません。 ユーザーがアクセスするデータに適した ODBC ドライバーを使用している限り、ユーザーはプログラムを使用して、そこに格納されているテーブルのデータを操作できます。

## <a name="see-also"></a>関連項目

[データベース接続を開く (ODBC)](open-database-connectivity-odbc.md)
