---
title: OLE DB でのトランザクションのサポート
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
ms.openlocfilehash: e7ec4f69b4bba497446c94afb94cb5a1d648f7c7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209550"
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB でのトランザクションのサポート

[トランザクション](../../data/transactions-mfc-data-access.md)は、1つのデータソースに対する一連の更新をグループ化またはバッチ処理する方法であり、すべて成功し、一度にコミットされるか (いずれかが失敗した場合) はコミットされず、トランザクション全体がロールバックされます。 このプロセスにより、データソースの結果の整合性が確保されます。

OLE DB では、次の3つの方法でトランザクションをサポートしています。

- [ITransactionLocal:: StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85))

- [ITransaction:: Commit](/previous-versions/windows/desktop/ms713008(v=vs.85))

- [ITransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85))

## <a name="relationship-of-sessions-and-transactions"></a>セッションとトランザクションの関係

1つのデータソースオブジェクトで1つ以上のセッションオブジェクトを作成できます。各オブジェクトは、特定の時点のトランザクションのスコープの内部または外部に配置できます。

セッションがトランザクションに入力されていない場合、データストア上のそのセッション内で行われたすべての処理は、メソッドの呼び出しごとに直ちにコミットされます。 (これは、自動コミットモードまたは暗黙的モードと呼ばれることもあります)。

セッションがトランザクションに入ると、データストア上のそのセッション内で行われたすべての処理がそのトランザクションの一部になり、1つの単位としてコミットまたは中止されます。 (これは、手動コミットモードと呼ばれることもあります)。

トランザクションのサポートはプロバイダー固有です。 使用しているプロバイダーがトランザクションをサポートしている場合、`ITransaction` と `ITransactionLocal` をサポートするセッションオブジェクトは、(入れ子になっていない) トランザクションに入ることができます。 OLE DB Templates クラス[CSession](../../data/oledb/csession-class.md)はこれらのインターフェイスをサポートしており、ビジュアルC++でトランザクションサポートを実装する場合に推奨される方法です。

## <a name="starting-and-ending-the-transaction"></a>トランザクションの開始と終了

コンシューマーの行セットオブジェクトの `StartTransaction`、`Commit`、および `Abort` メソッドを呼び出します。

`ITransactionLocal::StartTransaction` を呼び出すと、新しいローカルトランザクションが開始されます。 トランザクションを開始すると、トランザクションをコミットするまで、後の操作で必要な変更はデータストアに適用されません。

`ITransaction::Commit` または `ITransaction::Abort` を呼び出すと、トランザクションが終了します。 `Commit` により、トランザクションのスコープ内のすべての変更がデータストアに適用されます。 `Abort` を指定すると、トランザクションのスコープ内のすべての変更が取り消され、データストアはトランザクションが開始される前の状態のままになります。

## <a name="nested-transactions"></a>入れ子になったトランザクション

[入れ子になったトランザクション](/previous-versions/windows/desktop/ms716985(v=vs.85))は、セッションにアクティブなトランザクションが既に存在する場合に、新しいローカルトランザクションを開始すると発生します。 新しいトランザクションは、現在のトランザクションの下に入れ子になったトランザクションとして開始されます。 プロバイダーが入れ子になったトランザクションをサポートしていない場合、セッションでアクティブなトランザクションが既に存在するときに `StartTransaction` を呼び出すと、XACT_E_XTIONEXISTS が返されます。

## <a name="distributed-transactions"></a>分散トランザクション

分散トランザクションは、分散データを更新するトランザクションです。つまり、ネットワークに接続された複数のコンピューターシステム上のデータです。 分散システムでトランザクションをサポートする場合は、OLE DB トランザクションのサポートではなく、.NET Framework を使用する必要があります。

## <a name="see-also"></a>参照

[アクセサーの使用](../../data/oledb/using-accessors.md)
