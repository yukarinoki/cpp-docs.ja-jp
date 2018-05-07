---
title: OLE DB プロバイダー テンプレート リファレンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- vc.templates.ole
dev_langs:
- C++
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 040e8a5e244b7978a2b9ead394e243207939655c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB プロバイダー テンプレート リファレンス
クラスと OLE DB プロバイダー テンプレート用のインターフェイスは、次のカテゴリにグループ化できます。 参考資料に関する情報も含まれます、 [OLE DB プロバイダー テンプレート用マクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)です。  
  
 クラスは、次の名前付け規則を使用: とパターンをという名前のクラス**IWidgetImpl**インターフェイスの実装が提供**IWidget**です。  
  
## <a name="session-classes"></a>セッション クラス  
 [IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)  
 データ ソース オブジェクトから、新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。 データ ソース オブジェクトに対する必須のインターフェイスです。  
  
 [ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)  
 プロパティ セットのマップによって定義された静的関数を呼び出すことによって、セッションのプロパティを実装します。 セッション クラスでは、プロパティ セットのマップを指定してください。 セッションの必須インターフェイス。  
  
## <a name="rowset-classes"></a>行セット クラス  
 [CRowsetImpl](../../data/oledb/crowsetimpl-class.md)  
  
 多くの実装インターフェイスの多重継承を必要とせず、標準の OLE DB 行セットの実装を提供します。 唯一の方法を実装を提供する必要があります**Execute**です。  
  
 [CSimpleRow](../../data/oledb/csimplerow-class.md)  
 使用されている行ハンドルの既定の実装を提供、`IRowsetImpl`クラスです。 行ハンドルは、結果の行の一意のタグで、論理的にします。 `IRowsetImpl` 新たに作成`CSimpleRow`で要求されているすべての行の`IRowsetImpl::GetNextRows`します。  
  
 [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)  
 OLE DB プロバイダーを実装するを必要とする**HACCESSOR**、タグの配列には**DBBINDING**構造体。 提供**HACCESSOR**のアドレスは、s、 **BindType**構造体。 行セットおよびコマンドには必須です。  
  
 [IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)  
 プロバイダーの列マップによって定義された静的関数にデリゲートします。 行セットとコマンドの必須のインターフェイスです。  
  
 [IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)  
 コマンドまたは行セットでは、型変換の可用性の情報を提供します。 コマンド、行セット、およびインデックス行セットでは必須です。 実装して、 **IConvertType** OLE DB で指定されている変換オブジェクトへの委任でのインターフェイスです。  
  
 [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)  
 実装して、 **IDBSchemaRowset**インターフェイスと、テンプレート化された作成関数`CreateSchemaRowset`です。  
  
 [IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)  
 開き、単一のベース テーブルまたはインデックスからすべての行を含む行セットを返します。 セッション オブジェクトの必須のインターフェイスです。  
  
 [IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)  
 OLE DB を実装する[IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)インターフェイスは、これにより、行を削除して、新しい行を挿入する既存の行の列の値を更新します。  
  
 [IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)  
 このクラスから継承[IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765)と上書き[IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869)です。 `IRowsetCreatorImpl` 同じ機能を実行`IObjectWithSite`OLE DB プロパティこともできますが、 **DBPROPCANSCROLLBACKWARDS**と**DBPROPCANFETCHBACKWARDS**です。  
  
 [IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)  
 実装して、 **IRowsetIdentity**インターフェイスで、2 つの行のデータが同一かどうかを比較することができます。  
  
 [IRowsetImpl](../../data/oledb/irowsetimpl-class.md)  
 実装を提供、`IRowset`インターフェイスで、行セットの基本インターフェイスです。  
  
 [IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)  
 実装してプロパティを使用して行セット プロパティは、コマンド クラスで定義されているマップを設定します。 行セットの必須インターフェイス。  
  
 [IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)  
 OLE DB を実装する[IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx)インターフェイスで、行セットから任意の行をフェッチします。 OLE DB のブックマークを行セットをサポートするには、このクラスから継承行セットを確認します。  
  
 [IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)  
 実装は、接続ポイントに対するリスナーに通知する関数をブロードキャスト**IID_IRowsetNotify**行セットの内容を変更します。 通知を処理するコンシューマーを実装[IRowsetNotify](https://msdn.microsoft.com/en-us/library/ms712959.aspx)し、その接続ポイントに登録します。  
  
 [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)  
 OLE DB を実装する[IRowsetUpdate](https://msdn.microsoft.com/en-us/library/ms714401.aspx)インターフェイスで行われた変更の送信を遅延するコンシューマー [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)をデータ ソースし、データ伝送する前に変更を元に戻します。  
  
## <a name="command-classes"></a>コマンド クラス  
 [ICommandImpl](../../data/oledb/icommandimpl-class.md)  
 `ICommand` インターフェイスの実装を提供します。 このインターフェイスは表示されませんが、によって処理される**ICommandTextImpl**です。 Command オブジェクトに必須のインターフェイスです。  
  
 [ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)  
 この実装、 **ICommandProperties**インターフェイスが定義されている静的関数によって提供される、`BEGIN_PROPSET_MAP`マクロです。 コマンドでは必須です。  
  
 [ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)  
 設定、格納、およびコマンド テキストを返します。 コマンドでは必須です。  
  
 [IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)  
 セッション オブジェクトから、新しいコマンドを作成し、新しく作成されたコマンドに対して要求されたインターフェイスを返します。 セッション オブジェクトの省略可能なインターフェイスです。  
  
 その他のコマンド クラスは、`IColumnsInfoImpl`と`IAccessorImpl`前の行セット クラスのセクションで説明します。  
  
## <a name="data-source-classes"></a>データ ソース クラス  
 [IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)  
 作成し、コンシューマーとの接続を削除します。 データ ソース オブジェクトと列挙子の省略可能なインターフェイスの必須のインターフェイスです。  
  
 [IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)  
 `IDBProperties` データ ソース オブジェクトに必要なインターフェイスと列挙子のオプションのインターフェイスです。 ただし、列挙子を公開する場合**IDBInitialize**、公開している`IDBProperties`(データ ソースのプロパティ)。  
  
 [IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)  
 データ ソース オブジェクトへのインターフェイス ポインターを取得します。 このセッションで必須のインターフェイスです。  
  
## <a name="other-classes"></a>その他のクラス  
 [CUtlProps](../../data/oledb/cutlprops-class.md)  
 プロパティの OLE DB インターフェイスのさまざまなプロパティを実装する (たとえば、 `IDBProperties`、 **ISessionProperties**、および`IRowsetInfo`)。  
  
 [IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)  
  
 OLE DB を実装する[IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx)インターフェイスにレコードを追加して、データ メンバーからレコードを取得します。  
  
## <a name="see-also"></a>関連項目  
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [OLE DB テンプレート](../../data/oledb/ole-db-templates.md)