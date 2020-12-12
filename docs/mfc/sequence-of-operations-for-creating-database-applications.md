---
description: '詳細情報: データベースアプリケーションを作成するための一連の操作'
title: データベース アプリケーションの作成手順
ms.date: 11/04/2016
helpviewer_keywords:
- applications [MFC], database
- database applications [MFC]
- database applications [MFC], creating
- MFC, database applications
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
ms.openlocfilehash: 86f06ae5200fc8646ccb80bfec4e2814b94f9225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217589"
---
# <a name="sequence-of-operations-for-creating-database-applications"></a>データベース アプリケーションの作成手順

次の表は、データベースアプリケーションの作成におけるロールとフレームワークの役割を示しています。

> [!NOTE]
> Visual C++ 環境とウィザードでは、DAO はサポートされていません (ただし、DAO クラスは含まれていますが、引き続き使用できます)。 Microsoft では、新しい MFC プロジェクトに ODBC を使用することをお勧めします。 既存のアプリケーションを維持するには、DAO のみを使用する必要があります。

### <a name="creating-database-applications"></a>データベースアプリケーションの作成

|タスク|そうですよね|フレームワークは|
|----------|------------|------------------------|
|MFC ODBC クラスと DAO クラスのどちらを使用するかを決定します。|新しい MFC プロジェクトに ODBC を使用します。 既存のアプリケーションを維持するには、DAO のみを使用します。 一般情報については、「 [データアクセスプログラミング](../data/data-access-programming-mfc-atl.md)」を参照してください。|フレームワークには、データベースアクセスをサポートするクラスが用意されています。|
|データベースオプションを使用してスケルトンアプリケーションを作成します。|MFC アプリケーションウィザードを実行します。 データベースサポートページでオプションを選択します。 レコードビューを作成するオプションを選択した場合は、次の項目も指定します。<br /><br />-データソースとテーブルの名前または名前<br />-クエリ名または名前。|MFC アプリケーションウィザードでは、ファイルを作成し、必要なインクルードを指定します。 指定するオプションによっては、ファイルにレコードセットクラスを含めることができます。|
|データベースフォームまたはフォームをデザインします。|Visual C++ ダイアログエディターを使用して、レコードビュークラスのダイアログテンプレートリソースにコントロールを配置します。|MFC アプリケーションウィザードでは、入力するための空のダイアログテンプレートリソースが作成されます。|
|必要に応じて、追加のレコードビューおよびレコードセットクラスを作成します。|クラスビューを使用して、ビューをデザインするクラスとダイアログエディターを作成します。|クラスビューは、新しいクラス用に追加のファイルを作成します。|
|必要に応じてコードでレコードセットオブジェクトを作成します。 レコードを操作するには、各レコードセットを使用します...|レコードセットは、ウィザードを使用して、 [CRecordset](../mfc/reference/crecordset-class.md) から派生したクラスに基づいています。|ODBC では、レコードフィールドエクスチェンジ (RFX) を使用して、データベースとレコードセットのフィールドデータメンバーの間でデータを交換します。 レコードビューを使用している場合は、ダイアログデータエクスチェンジ (DDX) によって、レコードセットとレコードビューのコントロールとの間でデータが交換されます。|
|...または、開くデータベースごとに、コード内に明示的な [CDatabase](../mfc/reference/cdatabase-class.md) を作成します。|レコードセットオブジェクトをデータベースオブジェクトに基づいて作成します。|データベースオブジェクトは、データソースへのインターフェイスを提供します。|
|データ列をレコードセットに動的にバインドします。|ODBC では、バインドを管理するコードを派生レコードセットクラスに追加します。 「 [レコードセット: データ列を動的にバインドする (ODBC)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)」を参照してください。||

## <a name="see-also"></a>関連項目

[フレームワークでのビルド](../mfc/building-on-the-framework.md)<br/>
[MFC アプリケーションをビルドするための一連の操作](../mfc/sequence-of-operations-for-building-mfc-applications.md)<br/>
[OLE アプリケーションを作成するための一連の操作](../mfc/sequence-of-operations-for-creating-ole-applications.md)<br/>
[ActiveX コントロールを作成するための一連の操作](../mfc/sequence-of-operations-for-creating-activex-controls.md)
