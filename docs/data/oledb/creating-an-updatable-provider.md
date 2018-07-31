---
title: 更新可能なプロバイダーの作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, updatable
- notifications, support in providers
- OLE DB providers, creating
ms.assetid: bdfd5c9f-1c6f-4098-822c-dd650e70ab82
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e9ee36d2300ed1e86c1f867012ed54c85692f5bd
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340639"
---
# <a name="creating-an-updatable-provider"></a>更新可能なプロバイダーの作成

更新可能なプロバイダーまたはプロバイダーを更新できる visual C をサポートしています (書き込む) データ ストア。 このトピックでは、OLE DB テンプレートを使用して、更新可能なプロバイダーを作成する方法について説明します。  
  
 このトピックでは、実行可能なプロバイダーを起動することを前提としています。 更新可能なプロバイダーを作成する 2 つの手順があります。 プロバイダーが、データ ストアに変更を加える方法をまず決定する必要があります。具体的には、変更するかどうかをすぐに実行する、更新コマンドが実行されるまで延期されます。 セクション"[プロバイダーを更新可能にする](#vchowmakingprovidersupdatable)"の変更と、プロバイダー コードで行う必要がある設定について説明します。  
  
 次に、ご利用のプロバイダーには、コンシューマーの要求をサポートするためのすべての機能が含まれています。 確認する必要があります。 コンシューマーは、データ ストアを更新する場合、プロバイダーをデータ ストアにデータを保存するコードが含まれる必要があります。 たとえば、C ランタイム ライブラリまたは MFC を使用、データ ソースには、このような操作を実行するのに可能性があります。 セクション"[データ ソースへの書き込み](#vchowwritingtothedatasource)"データ ソースへの書き込み、NULL、既定値の処理、および列のフラグを設定する方法について説明します。  
  
> [!NOTE]
>  UpdatePV では、更新可能なプロバイダーの例を示します。 UpdatePV インストールされている MyProv として更新をサポートしています。  
  
##  <a name="vchowmakingprovidersupdatable"></a> 更新可能なプロバイダーを作成  

 更新可能なプロバイダーを行うには、データ ストアと、プロバイダーのこれらの操作を実行する方法で実行するプロバイダーを作成操作を理解することです。 具体的には、大きな問題は、データ ストアに更新プログラムが即座に実行または遅延がかどうか (バッチ)、update コマンドが発行されるまでです。  
  
 継承するかどうかを決定する必要がありますまず`IRowsetChangeImpl`または`IRowsetUpdateImpl`行セット クラス。 3 つのメソッドの機能の影響を実装するために選択次のうち、に応じて: `SetData`、 `InsertRows`、および`DeleteRows`します。  
  
- 継承する場合[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)、すぐにこれら 3 つのメソッドを呼び出すデータ ストアを変更します。  
  
- 継承する場合[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)を呼び出すまで、メソッドは、データ ストアへの変更を遅延`Update`、 `GetOriginalData`、または`Undo`します。 更新プログラムには、いくつかの変更が含まれている場合は、バッチ モード (変更のバッチ処理で大量のメモリ オーバーヘッドを追加できることに注意してください) で実行されます。  
  
 なお`IRowsetUpdateImpl`から派生した`IRowsetChangeImpl`します。 したがって、`IRowsetUpdateImpl`機能とバッチ機能を変更できます。  
  
#### <a name="to-support-updatability-in-your-provider"></a>プロバイダーで更新をサポートするには  
  
1. 行セット クラスから継承`IRowsetChangeImpl`または`IRowsetUpdateImpl`します。 これらのクラスは、データ ストアを変更するための適切なインターフェイスを提供します。  
  
     **IRowsetChange を追加します。**  
  
     追加`IRowsetChangeImpl`継承チェーンをこの形式を使用します。  
  
    ```cpp  
    IRowsetChangeImpl< rowset-name, storage-name >  
    ```  
  
     追加も`COM_INTERFACE_ENTRY(IRowsetChange)`を`BEGIN_COM_MAP`行セット クラスでセクション。  
  
     **IRowsetUpdate を追加します。**  
  
     追加`IRowsetUpdate`継承チェーンをこの形式を使用します。  
  
    ```cpp  
    IRowsetUpdateImpl< rowset-name, storage>  
    ```  
  
    > [!NOTE]
    >  削除する必要があります、`IRowsetChangeImpl`継承チェーンからの行。 ディレクティブの前に説明したこの例外が 1 つのコードを含める必要があります`IRowsetChangeImpl`します。  
  
2.  次の COM マップに追加 (`BEGIN_COM_MAP ... END_COM_MAP`)。  
  
    |実装する場合|COM マップに追加します。|  
    |----------------------|--------------------|  
    |`IRowsetChangeImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)`|  
    |`IRowsetUpdateImpl`|`COM_INTERFACE_ENTRY(IRowsetChange)COM_INTERFACE_ENTRY(IRowsetUpdate)`|  
  
3.  コマンドで、次のプロパティ セット マップに追加 (`BEGIN_PROPSET_MAP ... END_PROPSET_MAP`)。  
  
    |実装する場合|プロパティ セットのマップに追加します。|  
    |----------------------|-----------------------------|  
    |`IRowsetChangeImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)`|  
    |`IRowsetUpdateImpl`|`PROPERTY_INFO_ENTRY_VALUE(IRowsetChange, VARIANT_FALSE)PROPERTY_INFO_ENTRY_VALUE(IRowsetUpdate, VARIANT_FALSE)`|  
  
4.  プロパティ セット マップにも含めますすべて、次の設定の下に表示されます。  
  
    ```cpp  
    PROPERTY_INFO_ENTRY_VALUE(UPDATABILITY, DBPROPVAL_UP_CHANGE |   
      DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
    PROPERTY_INFO_ENTRY_VALUE(CHANGEINSERTEDROWS, VARIANT_TRUE)  
    PROPERTY_INFO_ENTRY_VALUE(IMMOBILEROWS, VARIANT_TRUE)  
  
    PROPERTY_INFO_ENTRY_EX(OWNINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OWNUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERINSERT, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(OTHERUPDATEDELETE, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_TRUE, 0)  
    PROPERTY_INFO_ENTRY_EX(REMOVEDELETED, VT_BOOL, DBPROPFLAGS_ROWSET |   
      DBPROPFLAGS_READ, VARIANT_FALSE, 0)  
    ```  
  
     プロパティの Id と値を Atldb.h で探すことによってこれらのマクロの呼び出しで使用する値を見つけることができます (Atldb.h と異なる場合、オンライン ドキュメント、Atldb.h よりも優先されますマニュアルを参照)。  
  
    > [!NOTE]
    >  多くは、`VARIANT_FALSE`と`VARIANT_TRUE`設定は、OLE DB テンプレートに必要な; OLE DB 仕様によれば、読み取り/書き込みができるが、OLE DB テンプレートは 1 つの値のみをサポートします。  
  
     **IRowsetChangeImpl を実装する場合**  
  
     実装する場合`IRowsetChangeImpl`プロバイダーに、次のプロパティを設定する必要があります。 これらのプロパティは、主にを介してインターフェイスを要求する使用`ICommandProperties::SetProperties`します。  
  
    - `DBPROP_IRowsetChange`: 設定セットでは自動的にこの`DBPROP_IRowsetChange`します。  
  
    - `DBPROP_UPDATABILITY`: でサポートされているメソッドを指定するビットマスク`IRowsetChange`: `SetData`、 `DeleteRows`、または`InsertRow`します。  
  
    - `DBPROP_CHANGEINSERTEDROWS`。 呼び出すことができますコンシューマー`IRowsetChange::DeleteRows`または`SetData`新しく挿入された行の。  
  
    - `DBPROP_IMMOBILEROWS`: 行セットは、挿入または更新された行を並べ替えられません。  
  
     **IRowsetUpdateImpl を実装する場合**  
  
     実装する場合`IRowsetUpdateImpl`、する必要があります、次プロパティを設定して、プロバイダー、さらにすべてのプロパティを設定する`IRowsetChangeImpl`上記に示した。  
  
    - `DBPROP_IRowsetUpdate`。  
  
    - `DBPROP_OWNINSERT`: READ_ONLY と VARIANT_TRUE をする必要があります。  
  
    - `DBPROP_OWNUPDATEDELETE`: READ_ONLY と VARIANT_TRUE をする必要があります。  
  
    - `DBPROP_OTHERINSERT`: READ_ONLY と VARIANT_TRUE をする必要があります。  
  
    - `DBPROP_OTHERUPDATEDELETE`: READ_ONLY と VARIANT_TRUE をする必要があります。  
  
    - `DBPROP_REMOVEDELETED`: READ_ONLY と VARIANT_TRUE をする必要があります。  
  
    - `DBPROP_MAXPENDINGROWS`。  
  
        > [!NOTE]
        >  通知をサポートする場合は、その他のプロパティも; をもがあります。参照してください`IRowsetNotifyCP`このリスト。  
  
##  <a name="vchowwritingtothedatasource"></a> データ ソースへの書き込み  
 データ ソースからの読み取り、呼び出し、`Execute`関数。 データ ソースへの書き込みを呼び出して、`FlushData`関数。 (一般的な意味では、テーブルまたはインデックスをディスクに加えた変更を保存するための手段をフラッシュします)。  

