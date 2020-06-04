---
title: ATL データベース クラス (OLE DB テンプレート)
ms.date: 05/02/2019
helpviewer_keywords:
- OLE DB templates [C++], ATL database classes
- database classes [C++], OLE DB
- database classes [C++], ATL
ms.assetid: 219766aa-e18a-405f-9e36-d7a0fdb31b2b
ms.openlocfilehash: 76e9f49d4b394d0c807ca1f3d103ff325ded8a09
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213500"
---
# <a name="atl-database-classes-ole-db-templates"></a>ATL データベース クラス (OLE DB テンプレート)

Microsoft では、さまざまな情報ソースと形式のデータへの一様なアクセスを提供する一連の COM インターフェイスである OLE DB の実装をいくつか提供しています。

OLE DB テンプレートは ATL C++のテンプレートであり、一般的に使用される OLE DB インターフェイスの多くを実装するクラスを提供することにより、OLE DB データベーステクノロジを簡単に使用できるようにします。

このテンプレートライブラリには、次の2つの部分が含まれます。

- [コンシューマーテンプレートの OLE DB](../data/oledb/ole-db-consumer-templates-cpp.md)OLE DB クライアント (コンシューマー) アプリケーションを実装するために使用します。

- [OLE DB プロバイダーテンプレート](../data/oledb/ole-db-provider-templates-cpp.md)OLE DB サーバー (プロバイダー) アプリケーションを実装するために使用します。

さらに、 [OLE DB のコンシューマー属性](../windows/ole-db-consumer-attributes.md)は OLE DB コンシューマーを作成するための便利な方法を提供します。 OLE DB の属性は OLE DB コンシューマーテンプレートに基づいてコードを挿入し、作業 OLE DB コンシューマーを作成します。

MFC ライブラリには、コントロールにデータベースレコードを表示する、 [Cobf Brecordview](../mfc/reference/coledbrecordview-class.md)というクラスが1つ含まれていることに注意してください。 ビューは、`CRowset` オブジェクトに直接接続されたフォームビューであり、ダイアログテンプレートのコントロールに `CRowset` オブジェクトのフィールドが表示されます。

詳細については、「プログラミングおよび[OLE DB プログラマーガイド](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)の[OLE DB](../data/oledb/ole-db-programming.md) 」を参照してください。

## <a name="see-also"></a>参照

[OLE DB コンシューマーの作成](../data/oledb/creating-an-ole-db-consumer.md)<br/>
[OLE DB プロバイダーの作成](../data/oledb/creating-an-ole-db-provider.md)<br/>
[OLE DB コンシューマー テンプレート リファレンス](../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[OLE DB プロバイダー テンプレート リファレンス](../data/oledb/ole-db-provider-templates-reference.md)<br/>
[OLE DB テンプレートのサンプルに関するページ](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB)
