---
description: 詳細については、「ATL データベースクラス (OLE DB テンプレート)」を参照してください。
title: ATL データベース クラス (OLE DB テンプレート)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: a9cc532a0b49f591cd08c70c398f8a37c08071ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213222"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL データベース クラス (OLE DB テンプレート)

Microsoft では、さまざまな情報ソースと形式のデータへの一様なアクセスを提供する一連の COM インターフェイスである OLE DB の実装をいくつか提供しています。

OLE DB テンプレートは ATL の C++ テンプレートであり、一般的に使用される OLE DB インターフェイスの多くを実装するクラスを提供することにより、OLE DB データベーステクノロジを簡単に使用できるようにします。

このテンプレートライブラリには、次の2つの部分が含まれます。

- [コンシューマーテンプレートの OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md) OLE DB クライアント (コンシューマー) アプリケーションを実装するために使用します。

- [OLE DB プロバイダーテンプレート](../data/oledb/ole-db-provider-templates-cpp.md) OLE DB サーバー (プロバイダー) アプリケーションを実装するために使用します。

さらに、 [OLE DB のコンシューマー属性](../windows/attributes/ole-db-consumer-attributes.md) は OLE DB コンシューマーを作成するための便利な方法を提供します。 OLE DB の属性は OLE DB コンシューマーテンプレートに基づいてコードを挿入し、作業 OLE DB コンシューマーを作成します。

MFC ライブラリには、コントロールにデータベースレコードを表示する、 [Cobf Brecordview](../mfc/reference/coledbrecordview-class.md)というクラスが1つ含まれていることに注意してください。 ビューは、オブジェクトに直接接続されたフォームビューで、 `CRowset` `CRowset` ダイアログテンプレートのコントロールにオブジェクトのフィールドを表示します。

詳細については、「プログラミングおよび[OLE DB プログラマーガイド](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)の[OLE DB](../data/oledb/ole-db-programming.md) 」を参照してください。

## <a name="see-also"></a>関連項目

[OLE DB コンシューマーの作成](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB プロバイダーの作成](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB コンシューマーテンプレートリファレンス](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB プロバイダーテンプレートのリファレンス](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB テンプレートのサンプル](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)
