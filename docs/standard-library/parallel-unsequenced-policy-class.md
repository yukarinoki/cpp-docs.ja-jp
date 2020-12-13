---
description: '詳細情報: parallel_unsequenced_policy クラス'
title: parallel_unsequenced_policy クラス
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: e39edc0979bf1374bc6092dbadb032811180f668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340789"
---
# <a name="parallel_unsequenced_policy-class"></a>parallel_unsequenced_policy クラス

並列アルゴリズムのオーバーロードを明確にするための一意の型として使用され、並列アルゴリズムの実行が並列化され、ベクター化される可能性があることを示します。

## <a name="syntax"></a>構文

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>解説

ポリシーを使用した並列アルゴリズムの実行中に、 `execution::parallel_unsequenced_policy` 要素アクセス関数の呼び出しがキャッチされない例外によって終了した場合は、が `terminate()` 呼び出されます。
