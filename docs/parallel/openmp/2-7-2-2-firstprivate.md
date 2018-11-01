---
title: 2.7.2.2 firstprivate
ms.date: 11/04/2016
ms.assetid: ece6ff12-2be1-4e4f-866c-d39345fd87b5
ms.openlocfilehash: f981c66fd3e0a2f42dcf731954f5054f96ed2973
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605973"
---
# <a name="2722-firstprivate"></a>2.7.2.2 firstprivate

**Firstprivate**句によって提供される機能のスーパー セットを提供する、**プライベート**句。 構文、 **firstprivate**句を次に示します。

```
firstprivate(variable-list)
```

指定する変数*変数一覧*が**プライベート**句セマンティクス」の説明に従って[セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 ページ上。 初期化または構築は、コンス トラクターのスレッドの実行前に、スレッドあたり 1 回実行された場合に発生します。 **Firstprivate** parallel コンストラクトの句は、新しいプライベート オブジェクトの初期値は、これが発生したスレッドの parallel コンストラクトする直前にある元のオブジェクトの値。 **Firstprivate** work-sharing コンス トラクターで句、work-sharing コンス トラクターを実行する各スレッドの新しいプライベート オブジェクトの初期値が時間内に、ポイントする前に存在する元のオブジェクトの値を同じスレッドでは、work-sharing コンス トラクターが発生します。 さらに、C++ のオブジェクトの各スレッドの新しいプライベート オブジェクトは、元のオブジェクトから構築されたコピーです。

制限、 **firstprivate**句は、次のとおり。

- 指定される変数を**firstprivate**句が不完全な型または参照型は必要ありません。

- として指定されているクラス型の変数を**firstprivate**あいまいでないアクセス可能なコピー コンス トラクターを含める必要があります。

- 並行領域内でプライベート変数に表示される、**削減**の句、**並列**でディレクティブを指定することはできません、 **firstprivate**句で、parallel コンストラクトにバインドされる動作共有ディレクティブ。