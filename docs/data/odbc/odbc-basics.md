---
description: '詳細情報: ODBC の基礎'
title: ODBC の基礎
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC cursor library [ODBC], ODBC components
- ODBC components
- ODBC components, required components
- ODBC, about ODBC
- ODBC, components
ms.assetid: ec529702-0fb2-4754-b8de-d1efa8eca18f
ms.openlocfilehash: 94482abd046645e445ffae7f85f192514f4fff78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161183"
---
# <a name="odbc-basics"></a>ODBC の基礎

このトピックでは、ODBC (Open Database Connectivity) の基礎について説明します。

- [ODBC とデータベース クラス](../../data/odbc/odbc-and-the-database-classes.md)

- [ダイナセットを使う場合の ODBC ドライバーの必要条件](../../data/odbc/odbc-driver-requirements-for-dynasets.md)

- [ODBC の構成要素の配布](../../data/odbc/redistributing-odbc-components-to-your-customers.md)

また、関連トピック「 [odbc: Odbc Cursor Library](../../data/odbc/odbc-the-odbc-cursor-library.md)」も参照してください。

> [!NOTE]
> ODBC データ ソースには、ここで説明するように、MFC ODBC クラス経由でアクセスできます。また、MFC DAO (Data Access Object) クラス経由でもアクセスできます。

> [!NOTE]
> MFC ODBC クラスは、Unicode とマルチスレッドをサポートしています。 マルチスレッドのサポートの詳細については、「 [ODBC のクラスとスレッド](../../data/odbc/odbc-classes-and-threads.md)」を参照してください。

ODBC は、データベース内のデータにアクセスするための呼び出しレベルのインターフェイスであり、ODBC ドライバーがあるデータベースならば、どのデータベースにでもアクセスできます。 ODBC を使って作成したアプリケーションからはどのデータベースにでもアクセスできますが、アプリケーションのユーザーがそのデータベースに対応した ODBC ドライバーを持っている必要があります。 ODBC が提供する API を使うと、アプリケーションをデータベース管理システム (DBMS) から独立できます。

ODBC は、WOSA (Microsoft Windows Open Services Architecture) のデータベース関連部分です。WOSA は、Windows ベースのデスクトップ アプリケーションから複数のコンピューティング環境に接続できるようにするためのインターフェイスであり、プラットフォームごとにアプリケーションを書き換える必要がありません。

ODBC の構成要素は、次のとおりです。

- ODBC API

   関数呼び出しのライブラリ、一連のエラーコード、および Dbms のデータにアクセスするための標準的な [SQL](../../data/odbc/sql.md) 構文。

- ODBC ドライバー マネージャー

   アプリケーションの代わりに、ODBC データベース ドライバーを読み込むダイナミック リンク ライブラリ (Odbc32.dll) です。 この DLL は、アプリケーションに対して透過的です。

- ODBC データベース ドライバー

   ODBC の関数の呼び出しを処理する DLL です。DBMS ごとにあります。 提供されているドライバーの一覧については、「 [ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)」を参照してください。

- [ODBC カーソルライブラリ](../../data/odbc/odbc-the-odbc-cursor-library.md)

   ODBC ドライバー マネージャーとドライバーの間でデータのスクロールを処理するダイナミック リンク ライブラリ (Odbccr32.dll) です。

- [ODBC 管理者](../../data/odbc/odbc-administrator.md)

   アプリケーションからデータ ソースとして認識できるように DBMS を設定するツールです。

DBMS に直接アクセスせずに、各 DBMS 用の ODBC ドライバーを通じてアクセスすると、アプリケーションを DBMS から独立させることができます。 関数呼び出しは、ドライバーによって DBMS のコマンドに変換されるため、開発者の手間が省けるだけでなく、多くのデータ ソースに対応したアプリケーションを作成できます。

データベース クラスは、ODBC ドライバーを持つデータ ソースをサポートします。 たとえば、リレーショナル データベース、ISAM (Indexed Sequential Access Method) データベース、Excel のスプレッドシート、テキスト ファイルなどを扱えます。 データ ソースへの接続は ODBC ドライバーが行い、SQL を使ってデータベースからレコードを選択します。

Visual C++ のこのバージョンに含まれている ODBC ドライバー一覧、および他のドライバーを取得する方法については、「[ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)」を参照してください。

## <a name="see-also"></a>関連項目

[Open Database Connectivity (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)
