---
title: 1 つのストアド プロシージャからの複数の結果セットの使用
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 6163eb8bf18edfc3d205f1d012de0c64c5570693
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209288"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>1 つのストアド プロシージャからの複数の結果セットの使用

ほとんどのストアドプロシージャでは、複数の結果セットが返されます。 通常、このようなストアドプロシージャには1つ以上の select ステートメントが含まれます。 コンシューマーは、すべての結果セットを処理するために、このインクルードを考慮する必要があります。

## <a name="to-handle-multiple-result-sets"></a>複数の結果セットを処理するには

1. テンプレート引数として `CMultipleResults` を持ち、任意のアクセサー (通常は動的または手動のアクセサー) を使用して、`CCommand` クラスを作成します。 別の種類のアクセサーを使用する場合は、各行セットの出力列を特定できないことがあります。

1. ストアドプロシージャを通常どおり実行し、列をバインドします (「 [How Do I Fetch Data?](../../data/oledb/fetching-data.md)」を参照してください)。

1. データを使用します。

1. `CCommand` クラスで `GetNextResult` を呼び出します。 別の結果行セットが使用できる場合、`GetNextResult` は S_OK を返し、手動アクセサーを使用している場合は列を再バインドする必要があります。 `GetNextResult` によってエラーが返された場合、それ以上の結果セットは使用できません。

## <a name="see-also"></a>参照

[ストアド プロシージャの使用](../../data/oledb/using-stored-procedures.md)
