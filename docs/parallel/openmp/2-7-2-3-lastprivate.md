---
title: 2.7.2.3 lastprivate |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25edca8391eb094691ef4fea3c360d351f979b43
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385964"
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

`lastprivate`句によって提供される機能のスーパー セットを提供する、`private`句。 構文、`lastprivate`句を次に示します。

```
lastprivate(variable-list)
```

指定する変数、*変数一覧*が`private`句セマンティクスです。 ときに、`lastprivate`コンストラクト作業の共有、それぞれの値を識別するディレクティブの句が表示されます`lastprivate`に関連付けられているループ、または構文的に最後のセクション ディレクティブでは、順に最後のイテレーションからの変数が割り当てられている、変数の元のオブジェクト。 変数の最後の反復によって値が割り当て、**の**または**の並列**、またはの構文的に最後のセクションで、**セクション**または**セクションの並列**ディレクティブ、不確定な値が、構築後にあります。 割り当てられていないサブオブジェクトも、構築後に、不確定な値であります。

制限、`lastprivate`句は、次のとおり。

- すべての制限の`private`を適用します。

- として指定されているクラス型の変数を`lastprivate`あいまいでないアクセス可能なコピー代入演算子を指定する必要があります。

- 並行領域内でプライベート変数に表示される、`reduction`の句、**並列**でディレクティブを指定することはできません、 `lastprivate` parallel コンストラクトにバインドされる動作共有ディレクティブの句。