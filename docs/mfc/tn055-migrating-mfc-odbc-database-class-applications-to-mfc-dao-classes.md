---
title: TN055:MFC DAO クラスへ MFC ODBC データベース クラス アプリケーションの移行
ms.date: 06/20/2018
helpviewer_keywords:
- DAO [MFC], migration
- TN055
- migration [MFC], ODBC database applications
- ODBC classes [MFC], DAO classes
- migrating ODBC database applications [MFC]
- porting database applications to DAO
- ODBC [MFC], DAO
- porting ODBC database applications to DAO
- migrating database applications [MFC]
ms.assetid: 0f858bd1-e168-4e2e-bcd1-8debd82856e4
ms.openlocfilehash: 7a1d3436a9b19c40df2a08576d797de49833f14f
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611238"
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>TN055:MFC DAO クラスへ MFC ODBC データベース クラス アプリケーションの移行

> [!NOTE]
> Visual C 環境とウィザードは、(DAO クラスが含まれていますし、それらを使用することもできます) が DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)の新しいプロジェクト。 DAO は、既存のアプリケーションを維持するためにのみ使用する必要があります。

## <a name="overview"></a>概要

多くの状況では、MFC DAO データベース クラスに MFC ODBC データベース クラスを使用するアプリケーションを移行することが望ましい場合があります。 このテクニカル ノートは、MFC ODBC と DAO クラス間の相違点のほとんどについて詳しく説明します。 相違点に使用する必要な場合に、ODBC クラスからアプリケーションを MFC クラスに移行する非常に困難です。

## <a name="why-migrate-from-odbc-to-dao"></a>DAO に ODBC から移行する理由

さまざまな理由、DAO データベース クラスに、ODBC データベース クラスからアプリケーションを移行する場合がありますが、決定するは必ずしも単純型または明確な理由があります。 留意すべき 1 つには、ODBC ドライバーがある任意の ODBC データ ソースを読み取るは DAO によって使用される Microsoft Jet データベース エンジンができます。 ODBC データベース クラスを使用して、または ODBC のデータを読み取ることができますが、Microsoft Jet データベース エンジンを使用して、自分で直接、ODBC の呼び出しより効率的な場合があります。

ODBC と DAO 意思決定を容易にする単純なケースです。 たとえば、のみ必要がある場合、Microsoft Jet エンジンは、直接 DAO データベース クラスを使用する最適なことです (形式のアクセスや、Excel 形式) を読み取ることができる形式でデータにアクセスします。

複雑な場合は、サーバーまたは別のサーバーのさまざまなデータが存在する場合に発生します。 この場合は、ODBC データベース クラスまたは DAO データベース クラスを使用するかは、困難です。 異種結合 (SQL Server や Oracle などの複数の形式でサーバーからの結合データ) をなどの操作を行いますし、Microsoft Jet データベース エンジンはなくする ODBC データベースを使用している場合に必要な作業を実行するのに結合を実行する場合クラスまたはと呼ばれる ODBC 直接します。 ドライバーのカーソルをサポートする ODBC ドライバーを使用している場合、最適な選択肢には、ODBC データベース クラス可能性があります。

選択は、複雑なので、特別なニーズを指定されたさまざまなメソッドのパフォーマンスをテストするサンプル コードを記述することもできますです。 このテクニカル ノートでは、ODBC データベース クラスから DAO データベース クラスに移行する意思決定を行ったことを前提としています。

## <a name="similarities-between-odbc-database-classes-and-mfc-dao-database-classes"></a>ODBC データベース クラスと MFC DAO データベース クラスの類似点

MFC ODBC クラスの元のデザインが Microsoft Access および Microsoft Visual Basic で使用されている、DAO オブジェクト モデルに基づいています。 これはすべてここで示したする、ODBC と DAO の MFC クラスの多くの一般的な機能があることを意味します。 一般に、プログラミング モデルは、同じです。

いくつかの類似点を強調表示します。

- ODBC と DAO の両方のクラスでは、基になるデータベース管理システム (DBMS) を使用して管理するデータベース オブジェクトがあります。

- 両方が、その DBMS から返される結果のセットを表すレコード セット オブジェクトがあります。

- DAO データベースとレコード セット オブジェクトがあるメンバーは、ODBC クラスとほとんど同じです。

- クラスの両方のセットでは、データを取得するコードは、いくつかのオブジェクトとメンバーの名前変更と同じです。 変更が必要になりますが、通常、プロセス簡単な名前が変更されたときに、ODBC クラスから DAO クラスへの切り替え。

たとえば、両方のモデル データを取得するプロシージャは作成しデータベース オブジェクトを開いて、作成しレコード セット オブジェクトを開くおよび移動 (移動) は、いくつかの操作を実行するデータには。

## <a name="differences-between-odbc-and-dao-mfc-classes"></a>ODBC と DAO の MFC クラスの違い

複数のオブジェクトと豊富な一連のメソッド、DAO クラスが含まれますが、このセクションでは同じようなクラスと機能の違いについて詳しく説明のみ。

おそらく、クラスの最も明白な違いは同様のクラスおよびグローバル関数名の変更です。 次に、オブジェクト、メソッド、およびデータベース クラスに関連付けられているグローバル関数の名前の変更を示します。

|クラスまたは関数|同等の MFC DAO クラス|
|-----------------------|-----------------------------------|
|`CDatabase`|`CDaoDatabase`|
|`CDatabase::ExecuteSQL`|`CDaoDatabase::Execute`|
|`CRecordset`|`CDaoRecordset`|
|`CRecordset::GetDefaultConnect`|`CDaoRecordset::GetDefaultDBName`|
|`CFieldExchange`|`CDaoFieldExchange`|
|`RFX_Bool`|`DFX_Bool`|
|`RFX_Byte`|`DFX_Byte`|
|`RFX_Int`|`DFX_Short`|
|`RFX_Long`|`DFX_Long`|
||`DFX_Currency`|
|`RFX_Single`|`DFX_Single`|
|`RFX_Double`|`DFX_Double`|
|`RFX_Date`<sup>1</sup>|`DFX_Date` (`COleDateTime`-ベース)|
|`RFX_Text`|`DFX_Text`|
|`RFX_Binary`|`DFX_Binary`|
|`RFX_LongBinary`|`DFX_LongBinary`|

<sup>1</sup> 、`RFX_Date`に基づいて関数`CTime`と`TIMESTAMP_STRUCT`します。

可能性があります、アプリケーションに影響し、複数の単純な名前の変更を必要と機能の主な変更は、以下に示します。

- 定数とマクロを使用して、レコード セットなどのオープン型とオープン オプションが変更されました。

   ODBC クラスでは、MFC はマクロを使用してこれらのオプションを定義するために必要なまたは列挙型。

   DAO クラスでは、DAO はヘッダー ファイル (DBDAOINT でこれらのオプションの定義を提供します。H)。 レコード セットの種類の列挙のメンバーは、したがって`CRecordset`が、dao 定数代わりにします。 たとえばは使用**スナップショット**の種類を指定するときに`CRecordset`odbc が**DB_OPEN_SNAPSHOT**の種類を指定するときに`CDaoRecordset`します。

- 既定のレコード セットの種類`CRecordset`は**スナップショット**の既定のレコード セットの種類を while`CDaoRecordset`は**ダイナセット**(ODBC クラス スナップショットに関するその他の問題は、下記の注を参照してください)。

- ODBC`CRecordset`クラス順方向専用レコード セットの種類を作成するオプションがあります。 `CDaoRecordset`順方向専用のクラスまたはではないレコード セットの種類ではなくプロパティ (オプション) 特定の種類のレコード セット。

- 追加専用レコード セットを開くときに、`CRecordset`レコード セットのデータを読み取りおよび追加できますされるオブジェクトのものです。 `CDaoRecordset`追加専用のオプションの意味を文字どおり、レコード セットのデータができるオブジェクトの追加 (および、読み取ることができません)。

- ODBC クラスのトランザクションのメンバー関数のメンバーである`CDatabase`し、データベース レベルで動作します。 トランザクションのメンバー関数は、DAO クラスでより高いレベルのクラスのメンバーである (`CDaoWorkspace`) ため、複数を影響する可能性があると`CDaoDatabase`同じワークスペース (トランザクション領域) を共有するオブジェクト。

- 例外クラスが変更されました。 `CDBExceptions` ODBC クラス内でスローされると`CDaoExceptions`DAO クラスにします。

- `RFX_Date` 使用して`CTime`と`TIMESTAMP_STRUCT`オブジェクト`DFX_Date`使用`COleDateTime`します。 `COleDateTime`とほぼ同じです`CTime`、8 バイトの OLE に基づきますが、**日付**4 バイトではなく**time_t**データの大きな範囲を保持できるようにします。

   > [!NOTE]
   > DAO (`CDaoRecordset`) スナップショットは、ODBC の中に読み取り専用 (`CRecordset`) スナップショットが、ドライバーと ODBC カーソル ライブラリの使用によって更新可能な可能性があります。 カーソル ライブラリを使用している場合`CRecordset`スナップショットは更新可能です。 ODBC カーソル ライブラリが、デスクトップ Driver パック 3.0 から Microsoft ドライバーのいずれかを使用している場合、`CRecordset`スナップショットは読み取り専用です。 別のドライバーを使用している場合は、かどうかをドライバーのドキュメントを確認してください。 スナップショット (`STATIC_CURSORS`) は読み取り専用です。

## <a name="see-also"></a>関連項目

[番号順テクニカル ノート](../mfc/technical-notes-by-number.md)<br/>
[カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)
