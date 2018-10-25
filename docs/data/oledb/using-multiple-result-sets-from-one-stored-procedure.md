---
title: ストアド プロシージャのいずれかからの複数の結果セットの使用 |Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: ac30f74a593f79cea7f252c454f19b85260e27b8
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50078514"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>1 つのストアド プロシージャからの複数の結果セットの使用

ほとんどのストアド プロシージャは、複数の結果セットを返します。 このようなストアド プロシージャには、通常は、または複数の select ステートメント。 コンシューマーは、すべての結果セットを処理するためにこれらを含めることを検討する必要があります。

## <a name="to-handle-multiple-result-sets"></a>複数の結果を処理するために次のように設定します。

1. 作成、`CCommand`クラス`CMultipleResults`テンプレート引数と好み、通常は、動的または手動アクセサーのアクセサー。 アクセサーの別の型を使用する場合は、それぞれの行セットの出力列を決定できる場合がありますできません。

1. 通常どおり、ストアド プロシージャを実行し、列をバインド (を参照してください[データのフェッチを How Do I?](../../data/oledb/fetching-data.md))。

1. データを使用します。

1. 呼び出す`GetNextResult`上、`CCommand`クラス。 もう 1 つの結果行セットがある場合は`GetNextResult`S_OK を返しますと手動のアクセサーを使用している場合、列を再バインドする必要があります。 場合`GetNextResult`エラーが返されますが、使用可能な結果をさらには設定されません。

## <a name="see-also"></a>関連項目

[ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)