---
title: ODBC の基礎 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4ff225cb9095f78e7e7bd79c02eef1b67b7eb18
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069634"
---
# <a name="odbc-basics"></a>ODBC の基礎

このトピックでは、ODBC (Open Database Connectivity) の基礎について説明します。

- [ODBC のしくみとデータベース クラス](../../data/odbc/odbc-and-the-database-classes.md)

- [ダイナセットを使う場合の ODBC ドライバーのしくみ](../../data/odbc/odbc-driver-requirements-for-dynasets.md)

- [どのような ODBC コンポーネントをアプリケーションで再配布する必要があります。](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

関連トピックを参照することも[ODBC: ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)します。

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

> [!NOTE]
> MFC ODBC クラスは、Unicode とマルチスレッドをサポートしています。 マルチ スレッドのサポートの詳細については、次を参照してください[ODBC クラスおよびスレッド。](../../data/odbc/odbc-classes-and-threads.md)

ODBC は、データベース内のデータにアクセスするための呼び出しレベルのインターフェイスであり、ODBC ドライバーがあるデータベースならば、どのデータベースにでもアクセスできます。 ODBC を使って作成したアプリケーションからはどのデータベースにでもアクセスできますが、アプリケーションのユーザーがそのデータベースに対応した ODBC ドライバーを持っている必要があります。 ODBC が提供する API を使うと、アプリケーションをデータベース管理システム (DBMS) から独立できます。

ODBC は、WOSA (Microsoft Windows Open Services Architecture) のデータベース関連部分です。WOSA は、Windows ベースのデスクトップ アプリケーションから複数のコンピューティング環境に接続できるようにするためのインターフェイスであり、プラットフォームごとにアプリケーションを書き換える必要がありません。

ODBC の構成要素は、次のとおりです。

- ODBC API

   関数のライブラリを呼び出すと、一連の標準的なエラー コード、 [SQL](../../data/odbc/sql.md) Dbms のデータにアクセスするための構文。

- ODBC ドライバー マネージャー

   アプリケーションの代わりに、ODBC データベース ドライバーを読み込むダイナミック リンク ライブラリ (Odbc32.dll) です。 この DLL は、アプリケーションに対して透過的です。

- ODBC データベース ドライバー

   ODBC の関数の呼び出しを処理する DLL です。DBMS ごとにあります。 指定されたドライバーの一覧は、次を参照してください。 [ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)します。

- [ODBC カーソル ライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)

   ODBC ドライバー マネージャーとドライバーの間でデータのスクロールを処理するダイナミック リンク ライブラリ (Odbccr32.dll) です。

- [ODBC データ ソース アドミニストレーター](../../data/odbc/odbc-administrator.md)

   アプリケーションからデータ ソースとして認識できるように DBMS を設定するツールです。

DBMS に直接アクセスせずに、各 DBMS 用の ODBC ドライバーを通じてアクセスすると、アプリケーションを DBMS から独立させることができます。 関数呼び出しは、ドライバーによって DBMS のコマンドに変換されるため、開発者の手間が省けるだけでなく、多くのデータ ソースに対応したアプリケーションを作成できます。

データベース クラスは、ODBC ドライバーを持つデータ ソースをサポートします。 たとえば、リレーショナル データベース、ISAM (Indexed Sequential Access Method) データベース、Excel のスプレッドシート、テキスト ファイルなどを扱えます。 データ ソースへの接続は ODBC ドライバーが行い、SQL を使ってデータベースからレコードを選択します。

このバージョンの Visual C に含まれる ODBC ドライバーの一覧については、および追加のドライバーの入手方法については、「 [ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)します。

## <a name="see-also"></a>関連項目

[ODBC (Open Database Connectivity)](../../data/odbc/open-database-connectivity-odbc.md)