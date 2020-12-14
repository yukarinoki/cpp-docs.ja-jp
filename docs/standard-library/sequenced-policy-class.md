---
description: '詳細情報: sequenced_policy クラス'
title: sequenced_policy クラス
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: e4d19e3649e3c768e8efc062baaf735e28a8fc22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250414"
---
# <a name="sequenced_policy-class"></a>sequenced_policy クラス

並列アルゴリズムのオーバーロードを明確にするために一意の型として使用され、並列アルゴリズムの実行を並列化できないようにする必要があります。

## <a name="syntax"></a>構文

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>解説

ポリシーを使用した並列アルゴリズムの実行中に、 `execution::sequenced_policy` 要素アクセス関数の呼び出しがキャッチされない例外によって終了した場合は、が `terminate()` 呼び出されます。
