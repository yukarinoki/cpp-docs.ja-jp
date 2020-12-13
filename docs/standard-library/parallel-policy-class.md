---
description: '詳細情報: parallel_policy クラス'
title: parallel_policy クラス
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_policy
ms.openlocfilehash: 1cead0bcc44256bf7d41d061d592849a7411b057
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340802"
---
# <a name="parallel_policy-class"></a>parallel_policy クラス

並列アルゴリズムのオーバーロードを明確にするための一意の型として使用され、並列アルゴリズムの実行が並列化される可能性があることを示します。

## <a name="syntax"></a>構文

```cpp
class execution::parallel_policy;
```

## <a name="remarks"></a>解説

ポリシーを使用した並列アルゴリズムの実行中に、 `execution::parallel_policy` 要素アクセス関数の呼び出しがキャッチされない例外によって終了した場合は、が `terminate()` 呼び出されます。
