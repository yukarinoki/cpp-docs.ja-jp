---
title: OLE DB プログラミングの概要
ms.date: 10/22/2018
helpviewer_keywords:
- Universal Data Access
- OLE DB, about OLE DB
ms.assetid: a5a69730-2793-4277-a67d-6f3c8edab6df
ms.openlocfilehash: 2b855e0917ba9cdbdaa38a92473d7bddb4279101
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210071"
---
# <a name="ole-db-programming-overview"></a>OLE DB プログラミングの概要

OLE DB は、COM ベースの高パフォーマンスのデータベーステクノロジです。 格納されているフォームとは無関係に、データにアクセスする一般的な方法を提供します。 一般的なビジネス上の状況では、膨大な量の情報が企業データベースに格納されていません。 このような情報は、ファイル システム (FAT や NTFS など)、インデックス付きのシーケンシャル ファイル、パーソナル データベース (Access など)、スプレッドシート (Excel など)、プロジェクト プランニング アプリケーション (Project など)、および電子メール (Outlook など) に含まれています。 OLE DB を使用すると、データストアに OLE DB プロバイダーがある限り、任意の種類のデータストアに同じ方法でアクセスできます。

OLE DB を使用すると、DBMS であるかどうかにかかわらず、さまざまなデータソースにアクセスするアプリケーションを開発できます。 OLE DB では、特定のデータ ソースに適した DBMS 機能をサポートする COM インターフェイスを使用することにより、汎用アクセスが可能になります。 COM では、データ ソース間だけでなく、ほかのアプリケーションとの間でも、サービスおよび最大化された相互運用性の不要な二重化が削減されます。

## <a name="benefits-of-com"></a>COM の利点

このような場合に COM が役に立ちます。 OLE DB は、COM インターフェイスのセットです。 インターフェイスの統一されたセットを通じてデータにアクセスすることにより、相互に協調するコンポーネントのマトリックスとしてデータベースを編成できます。

COM の仕様に基づき、OLE DB は、DBMS 機能の一貫性があり再利用できる部分を分解してカプセル化する、拡張可能で保守性の高いインターフェイスの集合を定義します。 これらのインターフェイスは、行コンテナー、クエリ プロセッサ、トランザクション コーディネーターなどの DBMS コンポーネントの境界を定義し、多様な情報源への統一されたトランザクション アクセスを可能にします。

## <a name="see-also"></a>参照

[OLE DB プログラミング](../../data/oledb/ole-db-programming.md)<br/>
[OLE DB コンシューマー テンプレートに関するページ](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB プロバイダー テンプレートに関するページ](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB テンプレート](../../data/oledb/ole-db-templates.md)
