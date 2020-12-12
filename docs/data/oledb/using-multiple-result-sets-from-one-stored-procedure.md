---
description: 詳細については、「1つのストアドプロシージャから複数の結果セットを使用する」を参照してください。
title: 1 つのストアド プロシージャからの複数の結果セットの使用
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 8e6b7a51635caf9ddfd86dddcad0e2a3f94bb7dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319119"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>1 つのストアド プロシージャからの複数の結果セットの使用

ほとんどのストアドプロシージャでは、複数の結果セットが返されます。 通常、このようなストアドプロシージャには1つ以上の select ステートメントが含まれます。 コンシューマーは、すべての結果セットを処理するために、このインクルードを考慮する必要があります。

## <a name="to-handle-multiple-result-sets"></a>複数の結果セットを処理するには

1. `CCommand` `CMultipleResults` テンプレート引数としてを使用し、任意のアクセサー (通常は動的または手動のアクセサー) を使用して、クラスを作成します。 別の種類のアクセサーを使用する場合は、各行セットの出力列を特定できないことがあります。

1. ストアドプロシージャを通常どおり実行し、列をバインドします (「 [How Do I Fetch Data?](../../data/oledb/fetching-data.md)」を参照してください)。

1. データを使用します。

1. `GetNextResult`クラスでを呼び出し `CCommand` ます。 別の結果行セットが使用可能な場合は `GetNextResult` S_OK を返し、手動アクセサーを使用している場合は列を再バインドする必要があります。 に `GetNextResult` よってエラーが返された場合、それ以上の結果セットは使用できません。

## <a name="see-also"></a>関連項目

[ストアドプロシージャの使用](../../data/oledb/using-stored-procedures.md)
