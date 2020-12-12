---
description: '詳細情報: OLE DB プロバイダーテンプレート (C++)'
title: OLE DB プロバイダー テンプレート (C++)
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers [C++], about providers
- databases [C++], OLE DB templates
- OLE DB provider templates [C++], about OLE DB provider templates
- templates [C++], OLE DB
ms.assetid: fccff85f-2af8-4500-82bd-6312d28a74b8
ms.openlocfilehash: 8706fcd9467e6d184633917d7c83ac81ad137b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286918"
---
# <a name="ole-db-provider-templates-c"></a>OLE DB プロバイダー テンプレート (C++)

OLE DB は、Microsoft ユニバーサルデータアクセス戦略の重要な部分です。 OLE DB の設計により、任意のデータソースからの高パフォーマンスなデータアクセスが可能になります。 表形式のデータは、データベースからのものであるかどうかにかかわらず、OLE DB を通じて表示できます。 柔軟性により、非常に多くの電力が得られます。

「OLE DB の [コンシューマーとプロバイダー](../../data/oledb/ole-db-consumers-and-providers.md)」で説明されているように、OLE DB はコンシューマーとプロバイダーの概念を使用します。 コンシューマーはデータの要求を行います。プロバイダーは、データを表形式でコンシューマーに返します。 プログラミングの観点から見ると、このモデルの最も重要な要素は、プロバイダーがコンシューマーが行うことのできる任意の呼び出しを実装する必要があることです。

## <a name="what-is-a-provider"></a>プロバイダーとは

OLE DB プロバイダーは、コンシューマーオブジェクトからのインターフェイス呼び出しを処理する COM オブジェクトのセットであり、テーブル形式のデータを永続ソース (データストアと呼ばれます) からコンシューマーに転送します。

プロバイダーは、単純または複雑にすることができます。 プロバイダーは、さらに多くのインターフェイスを実装することにより、最小限の機能をサポートしたり、本格的な運用品質プロバイダーをサポートしたりすることができます。 プロバイダーはテーブルを返し、クライアントがそのテーブルの形式を決定し、そのデータに対して操作を実行できるようにします。

各プロバイダーは、クライアントからの要求を処理するための標準の COM オブジェクトのセットを実装します。標準では、すべての OLE DB コンシューマーは言語 (C++ や Basic など) に関係なく、任意のプロバイダーからのデータにアクセスできます。

各 COM オブジェクトにはいくつかのインターフェイスが含まれており、その一部は必須であり、一部は省略可能です。 必須のインターフェイスを実装することにより、プロバイダーは、任意のクライアントが使用できる最小限の機能 (コンプライアンスと呼ばれる) を保証します。 プロバイダーは、オプションのインターフェイスを実装して、追加の機能を提供できます。 [OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)では、これらのインターフェイスについて詳しく説明しています。 クライアントは、 `QueryInterface` プロバイダーが特定のインターフェイスをサポートしているかどうかを判断するために、常にを呼び出す必要があります。

## <a name="ole-db-specification-level-support"></a>OLE DB 仕様レベルのサポート

OLE DB プロバイダーテンプレートでは、OLE DB バージョン2.7 仕様がサポートされています。 OLE DB プロバイダーテンプレートを使用して、レベル0に準拠したプロバイダーを実装できます。 たとえば、このサンプルでは、テンプレートを使用して、 `Provider` DOS DIR コマンドを実行してファイルシステムを照会する非 SQL (ms-dos) コマンドサーバーを実装しています。 この `Provider` サンプルでは、テーブルデータを返すための標準 OLE DB メカニズムである、行セットのディレクトリ情報が返されます。

OLE DB テンプレートでサポートされる最も単純な種類のプロバイダーは、コマンドのない読み取り専用プロバイダーです。 ブックマークおよび読み取り/書き込み機能と同様に、コマンドを含むプロバイダーもサポートされます。 追加のコードを記述して、読み取り/書き込みプロバイダーを実装できます。 動的な行セットとトランザクションは、現在のバージョンではサポートされていませんが、必要に応じて追加できます。

## <a name="when-do-you-need-to-create-an-ole-db-provider"></a>OLE DB プロバイダーを作成する必要がある場合は、

常に独自のプロバイダーを作成する必要はありません。Microsoft では、Visual C++ の [ **データリンクプロパティ** ] ダイアログボックスに、いくつかのパッケージ化された標準プロバイダーを提供しています。 OLE DB プロバイダーを作成する主な理由は、ユニバーサルデータアクセス戦略を利用することです。 これには、次のような利点があります。

- C++、Basic、Visual Basic Scripting Edition などの任意の言語を使用したデータへのアクセス。 これにより、組織内のさまざまなプログラマが、使用する言語に関係なく同じ方法で同じデータにアクセスできるようになります。

- SQL Server、Excel、Access などの他のデータソースに対してデータを開きます。 これは、異なる形式でデータを転送する場合に便利です。

- クロスデータソース (異種) 操作への参加。 これは、データウェアハウスの効果的な方法です。 OLE DB プロバイダーを使用すると、データをネイティブ形式で保持しながら、単純な操作でデータにアクセスできます。

- クエリ処理など、データに機能を追加します。

- データへのアクセスのパフォーマンスを向上させるために、操作方法を制御します。

- 堅牢性の向上。 プログラマが1人しかアクセスできない独自のデータ形式を使用している場合は、危険にさらされています。 OLE DB プロバイダーを使用すると、その独自の形式をすべてのプログラマに対して開くことができます。

## <a name="read-only-and-updatable-providers"></a>Read-Only および更新可能なプロバイダー

プロバイダーは、複雑さと機能に大きく左右されます。 プロバイダーを読み取り専用のプロバイダーと更新可能なプロバイダーに分類すると便利です。

- Visual C++ 6.0 では、読み取り専用プロバイダーのみがサポートされています。 [OLE DB プロバイダーを作成](../../data/oledb/creating-an-ole-db-provider.md) する方法については、「読み取り専用プロバイダーを作成する」を参照してください。
- Visual C++ では、データストアを更新 (書き込み) できる更新可能なプロバイダーがサポートされています。 更新可能なプロバイダーの詳細については、「 [更新可能なプロバイダーの作成](../../data/oledb/creating-an-updatable-provider.md)」を参照してください。 [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) サンプルは、更新可能なプロバイダーの例です。

詳細については、次を参照してください。

- [OLE DB プロバイダーテンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)

- [OLE DB プロバイダーの作成](../../data/oledb/creating-an-ole-db-provider.md)

- [OLE DB プログラミング](../../data/oledb/ole-db-programming.md)

## <a name="see-also"></a>関連項目

[データ アクセス](../data-access-in-cpp.md)<br/>
[OLE DB SDK のドキュメント](/previous-versions/windows/desktop/ms722784(v=vs.85))<br/>
[OLE DB プログラマーズ リファレンス](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming)<br/>
