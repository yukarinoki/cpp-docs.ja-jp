---
title: OLE DB アーキテクチャのデザインの問題 |Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, application design considerations
ms.assetid: 8caa7d99-d2bb-42c9-8884-74f228bb6ecc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a79cc4dfa36170293a8832571ba3348d6e2c8865
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990024"
---
# <a name="ole-db-architectural-design-issues"></a>OLE DB アーキテクチャのデザインの問題

OLE DB アプリケーションを開始する前に、次の問題を考慮してください。  
  
## <a name="what-programming-implementation-will-you-use-to-write-your-ole-db-application"></a>OLE DB アプリケーションを記述するプログラミング実装を使用するか。

Microsoft には、このタスクを実行するいくつかのライブラリが用意されています。 OLE DB テンプレート ライブラリを、OLE DB 属性、および OLE DB SDK では、生の OLE DB インターフェイス。 または、ウィザード、プログラムを記述するのに役立ちます。 これらの実装については、後述[OLE DB テンプレート、属性、およびその他の実装](../../data/oledb/ole-db-templates-attributes-and-other-implementations.md)します。

## <a name="do-you-need-to-write-your-own-provider"></a>独自のプロバイダーを記述する必要がありますか。

ほとんどの開発者は、独自のプロバイダーを作成する必要はありません。 Microsoft では、いくつかのプロバイダーを提供します。 データ接続を作成するたびに (たとえば、使用してプロジェクトにコンシューマーを追加すると、 **ATL OLE DB コンシューマー ウィザード**)、**データ リンク プロパティ** ダイアログ ボックスには、使用可能なすべてのプロバイダーが一覧表示されますシステムに登録します。 独自のデータ ストアとデータ アクセス アプリケーションの適切なプロバイダーのいずれかの場合を行う最も簡単な方法は次のいずれかを使用します。 ただし場合は、データ ストアは、これらのカテゴリのいずれかに一致しない、独自のプロバイダーを作成する必要あります。 プロバイダーを作成する方法の詳細については、次を参照してください。 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)します。

## <a name="what-level-of-support-do-you-need-for-your-consumer"></a>コンシューマーに必要なレベルのサポート

一部のコンシューマーは、ベーシック; であることができます。他のユーザーは、複雑になることができます。 OLE DB オブジェクトの機能は、プロパティによって指定されます。 使用すると、 **ATL OLE DB コンシューマー ウィザード**コンシューマーを作成する、または**データベース プロバイダー ウィザード**の標準セットを提供する適切なオブジェクトのプロパティを設定するプロバイダーを作成するには機能。 ただし、これらの処理に必要なすべてのウィザードで生成されたコンシューマーまたはプロバイダーのクラスをサポートしていない場合、必要がありますでこれらのクラス インターフェイスを指すため、 [OLE DB テンプレート ライブラリ](../../data/oledb/ole-db-templates.md)します。 これらのインターフェイスは、使いやすくために余分な実装を提供する、生の OLE DB インターフェイスをラップします。

など、行セット内のデータを更新するウィザードを使用して、コンシューマーの作成時に指定されていない場合は、する機能、ファクトの後に設定して指定できます、`DBPROP_IRowsetChange`と`DBPROP_UPDATABILITY`コマンド オブジェクトのプロパティ。 次に、行セットが作成されたときに、`IRowsetChange`インターフェイス。

## <a name="do-you-have-older-code-using-another-data-access-technology-ado-odbc-or-dao"></a>別のデータ アクセス テクノロジ (ADO、ODBC、または DAO) を使用して以前のコードを使用していますか。

(コンポーネントの OLE DB と ADO のコンポーネントを使用して、OLE DB の ODBC コードを移行する) などのテクノロジの組み合わせについて、すべての状況を説明することは、Visual C ドキュメントの範囲外です。 ただし、さまざまなシナリオをカバーする多くの記事では、次の Microsoft web サイトで使用できます。

- [Microsoft ヘルプおよびサポート](https://support.microsoft.com/)

- [Microsoft データ アクセス技術記事の概要](https://msdn.microsoft.com/library/ms810811.aspx)

## <a name="see-also"></a>関連項目

[OLE DB プログラミング](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB プログラミングの概要](../../data/oledb/ole-db-programming-overview.md)
