---
title: データベース アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: c393269d6af108ee82786e9d59f81aad11428157
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372771"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>データベース アプリケーションの作成手順

次の表は、データベース アプリケーションを作成する際の役割とフレームワークの役割を示しています。

> [!NOTE]
> Visual C++ 環境およびウィザードは DAO をサポートしていません (ただし、DAO クラスは含まれていますが、使用することはできます)。 マイクロソフトでは、新しい MFC プロジェクトに ODBC を使用することをお勧めします。 DAO は、既存のアプリケーションの保守にのみ使用してください。

### <a name="creating-database-applications"></a>データベース アプリケーションの作成

|タスク|そうですよね|フレームワークは、|
|----------|------------|------------------------|
|MFC ODBC クラスと DAO クラスのどちらを使用するかを決定します。|新しい MFC プロジェクトには ODBC を使用します。 DAO は、既存のアプリケーションを保守する場合にのみ使用します。 一般的な情報については、[データ アクセス プログラミングに関する記事を参照](../data/data-access-programming-mfc-atl.md)してください。|フレームワークは、データベース アクセスをサポートするクラスを提供します。|
|データベース オプションを使用してスケルトン アプリケーションを作成します。|MFC アプリケーション ウィザードを実行します。 [データベース サポート] ページでオプションを選択します。 レコードビューを作成するオプションを選択した場合は、次の項目も指定します。<br /><br />- データ ソースとテーブル名または名前<br />- クエリ名または名前。|MFC アプリケーション ウィザードは、ファイルを作成し、必要なインクルードを指定します。 指定するオプションに応じて、ファイルにレコードセット クラスを含めることができます。|
|データベース フォームをデザインします。|Visual C++ ダイアログ エディターを使用して、レコード ビュー クラスのダイアログ テンプレート リソースにコントロールを配置します。|MFC アプリケーション ウィザードは、入力する空のダイアログ テンプレート リソースを作成します。|
|必要に応じて、追加のレコード ビュークラスとレコードセット クラスを作成します。|クラス ビューを使用してクラスを作成し、ダイアログ エディターを使用してビューをデザインします。|クラス ビューでは、新しいクラス用に追加のファイルが作成されます。|
|必要に応じて、コード内にレコードセット オブジェクトを作成します。 各レコードセットを使用してレコードを操作します。|レコードセットは、ウィザードを使用して[CRecordset](../mfc/reference/crecordset-class.md)から派生したクラスに基づいています。|ODBC は、レコード フィールド エクスチェンジ (RFX) を使用して、データベースとレコードセットのフィールド データ メンバ間でデータを交換します。 レコード ビューを使用している場合、レコードセットとレコード ビューのコントロールとの間で、ダイアログ データ エクスチェンジ (DDX) がデータを交換します。|
|...または、開くデータベースごとに明示的な[CDatabase](../mfc/reference/cdatabase-class.md)をコードに作成します。|レコードセット オブジェクトの基にデータベース オブジェクトを作成します。|データベース オブジェクトは、データ ソースへのインターフェイスを提供します。|
|データ列をレコードセットに動的にバインドします。|ODBC で、バインディングを管理するコードを派生レコードセット クラスに追加します。 「[レコードセット: データ列の動的連結 (ODBC)」を](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)参照してください。||

## <a name="see-also"></a>関連項目

[フレームワーク上の構築](../mfc/building-on-the-framework.md)<br/>
[MFC アプリケーションの作成手順](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE アプリケーションの作成手順](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX コントロールの作成手順](../mfc/sequence-of-operations-for-creating-activex-controls.md)
