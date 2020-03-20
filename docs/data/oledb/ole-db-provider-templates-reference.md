---
title: OLE DB プロバイダー テンプレート リファレンス
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB provider templates
ms.assetid: 518358f0-bab1-4de9-bce9-4062cc87c11f
ms.openlocfilehash: f0200f0cff5292a75ec853496a644c148c8356a3
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79545793"
---
# <a name="ole-db-provider-templates-reference"></a>OLE DB プロバイダー テンプレート リファレンス

OLE DB プロバイダーテンプレートのクラスとインターフェイスは、次のカテゴリに分類できます。 参照資料には、 [OLE DB プロバイダーテンプレートのマクロ](../../data/oledb/macros-for-ole-db-provider-templates.md)に関する情報も含まれています。

クラスは、次の名前付け規則を使用します。という名前のクラスは、`IWidgetImpl` パターンを使用して、インターフェイス `IWidget`の実装を提供します。

## <a name="session-classes"></a>セッションクラス

[IDBCreateSessionImpl](../../data/oledb/idbcreatesessionimpl-class.md)<br/>
データソースオブジェクトから新しいセッションを作成し、新しく作成されたセッションで要求されたインターフェイスを返します。 データソースオブジェクトの必須インターフェイスです。

[ISessionPropertiesImpl](../../data/oledb/isessionpropertiesimpl-class.md)<br/>
プロパティセットマップによって定義された静的関数を呼び出すことによって、セッションのプロパティを実装します。 プロパティセットマップは、セッションクラスで指定する必要があります。 セッションの必須インターフェイス。

## <a name="rowset-classes"></a>行セットクラス

[CRowsetImpl](../../data/oledb/crowsetimpl-class.md)

多くの実装インターフェイスを多重継承せずに、標準の OLE DB 行セットの実装を提供します。 実装を提供する必要があるメソッドは `Execute`だけです。

[CSimpleRow](../../data/oledb/csimplerow-class.md)<br/>
`IRowsetImpl` クラスで使用される行ハンドルの既定の実装を提供します。 行ハンドルは、論理的には結果行の一意のタグです。 `IRowsetImpl` は、`IRowsetImpl::GetNextRows`で要求されたすべての行に対して新しい `CSimpleRow` を作成します。

[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)<br/>
OLE DB には、`DBBINDING` 構造体の配列へのタグである `HACCESSOR`を実装するプロバイダーが必要です。 `BindType` 構造体のアドレスである `HACCESSOR`を提供します。 行セットとコマンドでは必須です。

[IColumnsInfoImpl](../../data/oledb/icolumnsinfoimpl-class.md)<br/>
プロバイダー列マップによって定義された静的関数にデリゲートします。 行セットとコマンドの必須インターフェイスです。

[IConvertTypeImpl](../../data/oledb/iconverttypeimpl-class.md)<br/>
コマンドまたは行セットでの型変換の可用性に関する情報を提供します。 コマンド、行セット、およびインデックス行セットでは必須です。 OLE DB によって提供される変換オブジェクトにデリゲートすることによって、`IConvertType` インターフェイスを実装します。

[IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md)<br/>
`IDBSchemaRowset` インターフェイスと、テンプレート化 creator 関数 `CreateSchemaRowset`を実装します。

[IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)<br/>
を開き、1つのベーステーブルまたはインデックスのすべての行を含む行セットを返します。 セッションオブジェクトの必須インターフェイスです。

[IRowsetChangeImpl](../../data/oledb/irowsetchangeimpl-class.md)<br/>
OLE DB [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))インターフェイスを実装します。これにより、既存の行の列の値を更新したり、行を削除したり、新しい行を挿入したりできます。

[IRowsetCreatorImpl](../../data/oledb/irowsetcreatorimpl-class.md)<br/>
このクラスは、 [IObjectWithSite](/windows/win32/api/ocidl/nn-ocidl-iobjectwithsite)から継承し、 [IObjectWithSite:: SetSite](/windows/win32/api/ocidl/nf-ocidl-iobjectwithsite-setsite)をオーバーライドします。 `IRowsetCreatorImpl` は `IObjectWithSite` と同じ機能を実行しますが、`DBPROPCANSCROLLBACKWARDS` および `DBPROPCANFETCHBACKWARDS`の OLE DB プロパティも有効にします。

[IRowsetIdentityImpl](../../data/oledb/irowsetidentityimpl-class.md)<br/>
`IRowsetIdentity` インターフェイスを実装します。これにより、2つのデータ行が同一かどうかを比較できます。

[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)<br/>
基本行セットインターフェイスである `IRowset` インターフェイスの実装を提供します。

[IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)<br/>
コマンドクラスで定義されたプロパティセットマップを使用して、行セットプロパティを実装します。 行セットの必須のインターフェイスです。

[IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)<br/>
行セットから任意の行をフェッチする OLE DB [IRowsetLocate](/previous-versions/windows/desktop/ms721190(v=vs.85))インターフェイスを実装します。 行セット内の OLE DB ブックマークをサポートするには、行セットがこのクラスから継承されるようにします。

[IRowsetNotifyCP](../../data/oledb/irowsetnotifycp-class.md)<br/>
は、ブロードキャスト関数を実装して、行セットの内容に対する変更の `IID_IRowsetNotify` コネクションポイントでリスナーをアドバイズします。 通知を処理するコンシューマーは、 [IRowsetNotify](/previous-versions/windows/desktop/ms712959(v=vs.85))を実装し、その接続ポイントに登録します。

[IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)<br/>
OLE DB [IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85))インターフェイスを実装します。これにより、 [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))で行われた変更がデータソースに送信されるのをコンシューマーが遅らせ、転送前に変更を元に戻すことができます。

## <a name="command-classes"></a>コマンドクラス

[ICommandImpl](../../data/oledb/icommandimpl-class.md)<br/>
`ICommand` インターフェイスの実装を提供します。 このインターフェイスは表示されませんが、`ICommandTextImpl`によって処理されます。 Command オブジェクトの必須のインターフェイスです。

[ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)<br/>
この `ICommandProperties` インターフェイスの実装は、`BEGIN_PROPSET_MAP` マクロによって定義された静的関数によって提供されます。 コマンドでは必須。

[ICommandTextImpl](../../data/oledb/icommandtextimpl-class.md)<br/>
コマンドテキストを設定して格納し、返します。 コマンドでは必須。

[IDBCreateCommandImpl](../../data/oledb/idbcreatecommandimpl-class.md)<br/>
セッションオブジェクトから新しいコマンドを作成し、新しく作成されたコマンドで要求されたインターフェイスを返します。 セッションオブジェクトの省略可能なインターフェイスです。

その他のコマンドクラスは、上記の「行セットクラス」セクションで説明されている `IColumnsInfoImpl` および `IAccessorImpl`です。

## <a name="data-source-classes"></a>データソースクラス

[IDBInitializeImpl](../../data/oledb/idbinitializeimpl-class.md)<br/>
コンシューマーとの接続を作成および削除します。 列挙子のデータソースオブジェクトおよびオプションのインターフェイスの必須インターフェイス。

[IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)<br/>
`IDBProperties` は、データソースオブジェクトの必須のインターフェイスであり、列挙子のオプションのインターフェイスです。 ただし、列挙子が `IDBInitialize`を公開する場合は、`IDBProperties` (データソースのプロパティ) を公開する必要があります。

[IGetDataSourceImpl](../../data/oledb/igetdatasourceimpl-class.md)<br/>
データソースオブジェクトへのインターフェイスポインターを取得します。 セッションの必須インターフェイス。

## <a name="other-classes"></a>その他のクラス

[CUtlProps](../../data/oledb/cutlprops-class.md)<br/>
さまざまな OLE DB プロパティインターフェイス (`IDBProperties`、`ISessionProperties`、`IRowsetInfo`など) のプロパティを実装します。

[IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)

OLE DB [Ierrorrecords](/previous-versions/windows/desktop/ms718112(v=vs.85))インターフェイスを実装し、データメンバーにレコードを追加してレコードを取得します。

## <a name="see-also"></a>参照

[OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB テンプレート](../../data/oledb/ole-db-templates.md)