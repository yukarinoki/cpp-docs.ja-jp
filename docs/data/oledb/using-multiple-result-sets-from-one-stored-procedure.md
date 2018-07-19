---
title: ストアド プロシージャのいずれかからの複数の結果セットの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6393901839e8450ebc45b11f1d4bd2250da2ca56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106311"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>1 つのストアド プロシージャからの複数の結果セットの使用
ほとんどのストアド プロシージャは、複数の結果セットを返します。 このようなストアド プロシージャが通常 1 つを含むまたは以上の select ステートメント。 コンシューマーは、すべての結果セットの処理を行うために考慮する必要があります。  
  
### <a name="to-handle-multiple-result-sets"></a>複数の結果を処理するために次のように設定します。  
  
1.  作成、`CCommand`クラス`CMultipleResults`テンプレート引数として、任意のアクセサーを持つ。 通常、これは動的であるか手動アクセサーです。 アクセサーの別の型を使用する場合にそれぞれの行セットの出力列を判断できません。  
  
2.  通常どおり、ストアド プロシージャを実行し、列をバインド (を参照してください[データのフェッチ操作方法?](../../data/oledb/fetching-data.md))。  
  
3.  データを使用します。  
  
4.  呼び出す`GetNextResult`上、`CCommand`クラスです。 別の結果行セットがある場合は`GetNextResult`S_OK を返しますと手動のアクセサーを使用している場合、列を再バインドする必要があります。 場合`GetNextResult`エラーを返しますがさらに結果は使用可能な設定されません。  
  
## <a name="see-also"></a>関連項目  
 [ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)