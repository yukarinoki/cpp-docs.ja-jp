---
title: OLE DB テンプレート、属性、およびその他の実装
ms.date: 10/22/2018
helpviewer_keywords:
- OLE DB, implementations
- OLE DB templates, about OLE DB templates
- OLE DB templates
ms.assetid: 0c780c1b-9bba-4788-8c33-8552d9f120ac
ms.openlocfilehash: 217db304c7d0b5723b7af383e07290f160cc9465
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500915"
---
# <a name="ole-db-templates-attributes-and-other-implementations"></a>OLE DB テンプレート、属性、およびその他の実装

## <a name="atl-ole-db-templates"></a>ATL OLE DB テンプレート

ATL (Active Template Library) の一部である OLE DB テンプレートを使用すると、一般的に使用される OLE DB インターフェイスの多くを実装するクラスを提供することで、高パフォーマンスの OLE DB データベーステクノロジを簡単に使用できるようになります。 このテンプレートライブラリは、OLE DB starter アプリケーションを作成するためのウィザードをサポートしています。

このテンプレートライブラリには、次の2つの部分が含まれます。

- **コンシューマーテンプレートの OLE DB** OLE DB クライアント (コンシューマー) アプリケーションを実装するために使用します。

- **OLE DB プロバイダーテンプレート** OLE DB サーバー (プロバイダー) アプリケーションを実装するために使用します。

OLE DB テンプレートを使用するには、C++ テンプレート、COM、および OLE DB インターフェイスに関する知識が必要です。 OLE DB に慣れていない場合は、「 [プログラマーズリファレンス OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)」を参照してください。

詳細については、次の情報を参照してください。

- [OLE DB コンシューマーテンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)または[OLE DB プロバイダーテンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)に関するトピックを参照してください。

- [OLE DB コンシューマー](../../data/oledb/creating-an-ole-db-consumer.md)または[OLE DB プロバイダー](../../data/oledb/creating-an-ole-db-provider.md)を作成します。

- [OLE DB コンシューマークラス](../../data/oledb/ole-db-consumer-templates-reference.md)または[OLE DB プロバイダークラス](../../data/oledb/ole-db-provider-templates-reference.md)の一覧を参照してください。

- [OLE DB テンプレートのサンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)の一覧を参照してください。

- [OLE DB プログラマーのリファレンス](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)(Windows SDK) を参照してください。

## <a name="ole-db-attributes"></a>OLE DB 属性

[コンシューマー属性 OLE DB](../../windows/attributes/ole-db-consumer-attributes.md)は OLE DB コンシューマーを作成するための便利な方法を提供します。 OLE DB 属性は、 [OLE DB コンシューマーテンプレート](../../data/oledb/ole-db-consumer-templates-reference.md) に基づいてコードを挿入して、コンシューマーとプロバイダーの作業 OLE DB を作成します。 属性でサポートされていない機能を指定する必要がある場合は、コード内の属性と共に OLE DB テンプレートを使用できます。

## <a name="mfc-ole-db-classes"></a>MFC OLE DB クラス

MFC ライブラリには、コントロールにデータベースレコードを表示する、 [Cobf Brecordview](../../mfc/reference/coledbrecordview-class.md)という1つのクラスがあります。 ビューは、オブジェクトに直接接続されたフォームビューで、 `CRowset` `CRowset` ダイアログテンプレートのコントロールにオブジェクトのフィールドを表示します。 また、first、next、previous、last の各レコードに移動するための既定の実装と、現在ビューに表示されているレコードを更新するためのインターフェイスも用意されています。 詳細については、「`COleDBRecordView`」を参照してください。

## <a name="ole-db-sdk-interfaces"></a>OLE DB SDK インターフェイス

OLE DB テンプレートで OLE DB 機能がサポートされていない場合は、OLE DB インターフェイスを使用する必要があります。 詳細については、Windows SDK の「 [プログラマーズリファレンス OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB プログラミング](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)
