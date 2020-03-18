---
title: sequenced_policy クラス
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: 5647f20b560828016231a9bbd38977c51211e6bb
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444919"
---
# <a name="sequenced_policy-class"></a>sequenced_policy クラス

並列アルゴリズムのオーバーロードを明確にするために一意の型として使用され、並列アルゴリズムの実行を並列化できないようにする必要があります。

## <a name="syntax"></a>構文

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>コメント

`execution::sequenced_policy` ポリシーを使用した並列アルゴリズムの実行中に、要素アクセス関数の呼び出しがキャッチされない例外によって終了した場合、`terminate()` が呼び出されます。
