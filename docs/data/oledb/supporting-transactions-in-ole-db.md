---
title: OLE DB でのトランザクションのサポート |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ecd5b7274e62508289a83d6c0420d5f76e239e4d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33110342"
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB でのトランザクションのサポート
A[トランザクション](../../data/transactions-mfc-data-access.md)グループ、またはバッチの場合は、すべて成功が 1 回にコミットされるか (存在する任意の 1 つには失敗) は一切コミットされませんように一連のデータ ソースを更新する方法は、トランザクション全体がロールバックされます。 このプロセスは、データ ソースの結果の整合性を確保します。  
  
 OLE DB では、次の 3 つの方法でトランザクションをサポートしています。  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>セッションとトランザクションの関係  
 1 つのデータ ソース オブジェクトには、内部、または特定の時点でトランザクションのスコープ外のできる 1 つ以上のセッション オブジェクトを作成できます。  
  
 セッションに、トランザクションが入力していない場合、そのセッションで、データ ストアに対して行われたすべての作業はメソッド呼び出しごとにすぐにコミットされます。 (この場合もあります呼びます自動コミット モードまたは暗黙的なモードです。)  
  
 入力すると、セッション、トランザクション、そのセッションで、データ ストアに対して行われたすべての作業がトランザクションの一部とはコミットまたはアボート単一ユニットとして。 (この場合もあります呼びます手動コミット モードです。)  
  
 トランザクションのサポートは、プロバイダー固有です。 使用しているプロバイダーは、トランザクションをサポートするセッション オブジェクトをサポートしている場合**ITransaction**と**ITransactionLocal**単純なを入力できます (つまり、入れ子になっていない) トランザクション。 OLE DB テンプレート クラス[CSession](../../data/oledb/csession-class.md)をこれらのインターフェイスをサポートします。 Visual c でのトランザクションのサポートを実装することをお勧めします。  
  
## <a name="starting-and-ending-the-transaction"></a>最初と最後のトランザクション  
 呼び出す、 `StartTransaction`、**コミット**、および**中止**がコンシューマーの行セット オブジェクトのメソッドです。  
  
 呼び出す**itransactionlocal::starttransaction**新しいローカル トランザクションを開始します。 トランザクションを開始するときにすべての変更が後続の操作で必須では実際には適用されませんデータ ストアに、トランザクションがコミットされるまで。  
  
 呼び出す**itransaction::commit**または**itransaction::abort**トランザクションを終了します。 **コミット**データ ストアに適用するトランザクションのスコープ内のすべての変更が発生します。 **中止**キャンセルされるトランザクションとデータ ストアのスコープ内のすべての変更は状態のままに、その原因が、トランザクションの開始前にします。  
  
## <a name="nested-transactions"></a>入れ子になったトランザクション  
 A[入れ子にされたトランザクション](https://msdn.microsoft.com/en-us/library/ms716985.aspx)セッションにアクティブなトランザクションが存在する場合に、新しいローカル トランザクションを開始するときに発生します。 現在のトランザクションの下に入れ子になったトランザクションとしての新しいトランザクションを開始します。 プロバイダーが入れ子になったトランザクションをサポートしていない場合は、呼び出す`StartTransaction`でアクティブなトランザクションが既にセッションを返します**XACT_E_XTIONEXISTS**です。  
  
## <a name="distributed-transactions"></a>分散トランザクション  
 分散トランザクションは、分散型データを更新するトランザクションです。1 つ以上のネットワーク コンピューター システム上のデータは、します。 分散システムでトランザクションをサポートする場合は、OLE DB トランザクション サポートではなく、.NET Framework を使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)