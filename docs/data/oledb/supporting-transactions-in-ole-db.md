---
title: OLE DB でのトランザクションのサポート |Microsoft Docs
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
ms.openlocfilehash: 932185002032ab86ca80b2b3384bfe6cbb69f8b1
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338711"
---
# <a name="supporting-transactions-in-ole-db"></a>OLE DB でのトランザクションのサポート
A[トランザクション](../../data/transactions-mfc-data-access.md)グループ、またはバッチの場合は、コミットない (場合のいずれかが失敗した) か、または成功すべてが同時にコミットして、一連のデータ ソースを更新する方法は、トランザクション全体がロールバックされます。 このプロセスは、データ ソースの結果の整合性を維持します。  
  
 OLE DB では、次の 3 つの方法でトランザクションをサポートしています。  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/library/ms713008.aspx)  
  
-   [ITransaction::Abort](https://msdn.microsoft.com/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>セッションとトランザクションの関係  
 1 つのデータ ソース オブジェクトは、特定の時点でトランザクションのスコープの内外をそれぞれが 1 つまたは複数のセッション オブジェクトを作成できます。  
  
 セッションに、トランザクションが入力していない場合、そのセッションで、データ ストアに対して行われたすべての作業はメソッド呼び出しのたびに即座にコミットします。 (これとも呼ば自動コミット モードまたは暗黙的なモードです。)  
  
 セッションでは、トランザクションが入ると、そのセッションで、データ ストアに対して行われたすべての作業がトランザクションの一部とがコミットまたは中止単一ユニットとして。 (これとも呼ば手動コミット モードです。)  
  
 トランザクションのサポートは、プロバイダー固有です。 使用するプロバイダーは、トランザクションをサポートしているセッション オブジェクトをサポートしている場合`ITransaction`と`ITransactionLocal`単純なを入力できます (つまり、入れ子になっていない) トランザクション。 OLE DB テンプレート クラス[CSession](../../data/oledb/csession-class.md) Visual C にトランザクションのサポートを実装することをお勧めの方法であり、これらのインターフェイスをサポートしています。  
  
## <a name="starting-and-ending-the-transaction"></a>最初と最後のトランザクション  
 呼び出す、 `StartTransaction`、 `Commit`、および`Abort`コンシューマーの行セット オブジェクト内のメソッド。  
  
 呼び出す`ITransactionLocal::StartTransaction`新しいローカル トランザクションが開始されます。 トランザクションを開始するときに後続の操作で要求されるすべての変更は実際には適用されませんをデータ ストアに、トランザクションをコミットするまで。  
  
 呼び出す`ITransaction::Commit`または`ITransaction::Abort`トランザクションを終了します。 `Commit` データ ストアに適用するトランザクションのスコープ内のすべての変更を発生します。 `Abort` トランザクションを開始する前に、トランザクションを中止して、データ ストアのスコープ内のすべての変更は、状態のままに、その原因がありました。  
  
## <a name="nested-transactions"></a>入れ子になったトランザクション  
 A[トランザクションを入れ子になった](https://msdn.microsoft.com/library/ms716985.aspx)セッションにアクティブなトランザクションが存在する場合は、新しいローカル トランザクションを開始するときに発生します。 現在のトランザクションの下に入れ子になったトランザクションとしての新しいトランザクションを開始します。 呼び出して、プロバイダーが入れ子になったトランザクションをサポートしていない場合`StartTransaction`XACT_E_XTIONEXISTS が返されます、セッションにアクティブなトランザクションがあるときにします。  
  
## <a name="distributed-transactions"></a>分散トランザクション  
 分散トランザクションは分散型のデータを更新するトランザクションです。つまり、1 つ以上のネットワーク コンピューターのシステム データ。 分散システムでトランザクションをサポートする場合は、OLE DB のトランザクション サポートではなく、.NET Framework を使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [アクセサーの使用](../../data/oledb/using-accessors.md)