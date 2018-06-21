---
title: 'TN055: MFC ODBC データベース クラス アプリケーションの MFC DAO クラスへの移行 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.odbc
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6c346ca05a72917af615ecd6704a96ff9c190350
ms.sourcegitcommit: 05075fce8a0ed7fddb99f50f3931db966a91450d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271423"
---
# <a name="tn055-migrating-mfc-odbc-database-class-applications-to-mfc-dao-classes"></a>テクニカル ノート 55: MFC ODBC データベース クラス アプリケーションの MFC DAO クラスへの移行
> [!NOTE]
>  Visual C 環境とウィザードは、(ただし、DAO クラスが含まれると、引き続き使用することができます) DAO をサポートしています。 使用することをお勧めします。 [OLE DB テンプレート](../data/oledb/ole-db-templates.md)または[ODBC と MFC](../data/odbc/odbc-and-mfc.md)新しいプロジェクトのです。 DAO は、既存のアプリケーションを保守でのみ使用する必要があります。  
  
 **概要**  
  
 多くの状況では、MFC DAO データベース クラスに MFC ODBC データベース クラスを使用するアプリケーションを移行することが望ましい場合があります。 このテクニカル ノートには、MFC ODBC と DAO クラス間の相違点のほとんどは詳しく説明します。 相違点を念頭に使用しないで過度に必要な場合は、MFC クラスに ODBC クラスからアプリケーションを移行するが困難です。  
  
 **DAO に ODBC から移行する理由**  
  
 さまざまな理由、DAO データベース クラスに、ODBC データベース クラスからアプリケーションを移行する場合がありますが、意思決定必ずしも単純または明確な理由があります。 1 つの点に留意には、ODBC ドライバーがある任意の ODBC データ ソースを読み取るは DAO によって使用される Microsoft Jet データベース エンジンができます。 ODBC データベース クラスを使用するか、自分では、Microsoft Jet データベース エンジンは、ODBC データを読み取ることができる直接 ODBC を呼び出すより効率的な場合があります。  
  
 ODBC と DAO 意思決定を容易にする単純なケースです。 インスタンスのみ必要がある場合、Microsoft Jet エンジンが明らかな選択肢は DAO データベース クラスを使用して、(アクセス形式や、Excel 形式で) 直接読み取ることができる形式でデータへのアクセス。  
  
 複雑な場合は、サーバーまたは別のサーバーのさまざまなデータが存在する場合に発生します。 ここでは、ODBC データベース クラスと DAO データベース クラスを使用するかは、難しいものです。 異種結合 (SQL Server、Oracle などの複数の形式でサーバーから結合 data) で行うようなものにする場合は、Microsoft Jet データベース エンジンは、するではなく、ODBC データベースを使用した場合に必要な作業を実行することを強制の結合を実行します。クラスまたはと呼ばれる ODBC 直接します。 ドライバーのカーソルをサポートしている ODBC ドライバーを使用している場合、最適な選択肢に ODBC データベース クラス可能性があります。  
  
 特別なニーズを指定する各種のメソッドのパフォーマンスをテストするサンプル コードを記述することができますので、選択が複雑になることができます。 このテクニカル ノートでは、ODBC データベース クラスから DAO データベース クラスに移行する意思決定が行われたことを前提としています。  
  
 **ODBC データベース クラスと MFC DAO データベース クラスの類似点**  
  
 MFC ODBC クラスの元のデザインは、Microsoft Access や Microsoft Visual Basic で使用されている DAO オブジェクト モデルに基づくされました。 これは、ODBC と DAO MFC クラスのすべてではないリスト表示されるこのセクションの内容の多くの一般的な機能があることを意味します。 一般に、プログラミング モデルは、同じです。  
  
 いくつかの類似点を強調表示します。  
  
-   ODBC と DAO の両方のクラスでは、基になるデータベース管理システム (DBMS) を使用して管理するデータベース オブジェクトがあります。  
  
-   両方には、その DBMS から返される結果のセットを表すレコード セット オブジェクトが含まれています。  
  
-   DAO データベースとレコード セット オブジェクトは、ほぼ同じですが、ODBC クラスにメンバーを持っています。  
  
-   クラスの両方のセットでデータを取得するコードは、いくつかのオブジェクトとメンバーの名前変更を除いて同一です。 変更が必要ですが、されますが、通常、プロセス簡単な名前が変更されたときに、ODBC クラスから DAO クラスへの切り替え。  
  
 たとえば、データを取得する手順は、両方のモデルを作成し、データベース オブジェクトを開く、作成して開き recordset オブジェクトをしてデータ間を移動 (移動) が、いくつかの操作を実行します。  
  
 **ODBC と DAO MFC クラス間の相違点**  
  
 多くのオブジェクトと豊富な一連のメソッド、DAO クラスが含まれますが、このセクションでは同じようなクラスと機能の違いについて詳しく説明のみです。  
  
 可能性があります、最も明白な違いクラスが同様のクラスとグローバル関数の名前が変更できます。 次に、オブジェクト、メソッド、およびデータベース クラスに関連付けられているグローバル関数の名前の変更を示します。  
  
|クラスまたは関数|MFC DAO クラスに該当するショートカット|  
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
|**RFX_Date \\\***|**DFX_Date** (`COleDateTime`-ベース)|  
|`RFX_Text`|`DFX_Text`|  
|`RFX_Binary`|`DFX_Binary`|  
|`RFX_LongBinary`|`DFX_LongBinary`|  
  
 \*    `RFX_Date`関数がに基づいて`CTime`と**TIMESTAMP_STRUCT**です。  
  
 可能性があります、アプリケーションに影響し、複数の単純な名前の変更を必要とする機能に大きな変更は次のとおりです。  
  
-   定数とマクロのレコード セットのような種類を開くし、レコード セットを開くオプションを指定するために使用が変更されました。  
  
     ODBC クラスには、MFC はマクロを使用してこれらのオプションを定義するために必要なまたは列挙型。  
  
     DAO クラスでは、DAO がヘッダー ファイル (DBDAOINT これらのオプションの定義を提供します。H)。 レコード セットの種類の列挙のメンバーは、したがって`CRecordset`、しかし、DAO が定数代わりにします。 たとえばは使用**スナップショット**の種類を指定するときに`CRecordset`odbc が**DB_OPEN_SNAPSHOT**の種類を指定するときに`CDaoRecordset`です。  
  
-   既定のレコード セットの種類`CRecordset`は**スナップショット**の既定のレコード セットの種類を while`CDaoRecordset`は**ダイナセット**(ODBC クラス スナップショットに関するその他の問題の下にあるメモを参照してください)。  
  
-   ODBC`CRecordset`クラス順方向専用レコード セットの種類を作成するオプションがあります。 `CDaoRecordset`クラス、順方向専用、いないレコード セットの種類ではなくプロパティ (またはオプション) 特定の種類のレコード セット。  
  
-   追加専用レコード セットを開くときに、`CRecordset`オブジェクトには、レコード セットのデータの読み取りし、追加できなかったことが意図したものです。 `CDaoRecordset`オブジェクトの追加専用のオプションは、文字通りレコード セットのデータがあることができますのみ追加されます (および読み取ることができません)。  
  
-   ODBC クラスのトランザクションのメンバー関数のメンバーである`CDatabase`し、データベース レベルで機能します。 DAO クラスでより高いレベルのクラスのメンバーである、トランザクションのメンバー関数 (`CDaoWorkspace`) し、したがってが影響を与える複数`CDaoDatabase`同じワークスペース (トランザクション領域) を共有するオブジェクト。  
  
-   例外クラスが変更されました。 **CDBExceptions** ODBC クラス内でスローされると**CDaoExceptions** DAO クラスでします。  
  
-   `RFX_Date` 使用して`CTime`と**TIMESTAMP_STRUCT**オブジェクトを少し**DFX_Date**使用`COleDateTime`です。 `COleDateTime`とほぼ同じ`CTime`、8 バイト OLE に基づきますが、**日付**4 バイトではなく`time_t`データのはるかに大きい範囲を保持できるようにします。  
  
    > [!NOTE]
    >  DAO (`CDaoRecordset`) スナップショットは、ODBC の中に読み取り専用 (`CRecordset`) スナップショットが、ドライバーと ODBC カーソル ライブラリの使用によって更新可能な可能性があります。 カーソル ライブラリを使用している場合`CRecordset`スナップショットは更新可能です。 ODBC カーソル ライブラリが、デスクトップ ドライバー パック 3.0 から Microsoft ドライバーのいずれかを使用している場合、`CRecordset`スナップショットは読み取り専用です。 別のドライバーを使用している場合は、かどうかをドライバーのドキュメントを確認します。 スナップショット (**STATIC_CURSORS**) は読み取り専用です。  
  
## <a name="see-also"></a>関連項目  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)

