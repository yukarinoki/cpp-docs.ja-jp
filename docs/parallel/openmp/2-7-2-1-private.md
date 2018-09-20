---
title: 2.7.2.1 プライベート |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 079b4b84-f2b3-4050-a0ac-289493c36b3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d06650a784b5b59405f446f4701918393b21fa3b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387238"
---
# <a name="2721-private"></a>2.7.2.1 private

`private`句のチームでは、各スレッドに対してプライベートにするには、変数の一覧の変数を宣言します。 構文、`private`句を次に示します。

```
private(variable-list)
```

指定される変数の動作を`private`句を次に示します。 自動ストレージ存続期間で新しいオブジェクトは、構造に割り当てられます。 新しいオブジェクトの配置とサイズについては、変数の型によって決まります。 この割り当ては、チーム内の各スレッドの 1 回発生し、必要に応じて、クラス オブジェクトの既定のコンス トラクターが呼び出されますそれ以外の場合、初期値は、不確定ではありません。  変数によって参照されている元のオブジェクトは、コンストラクトに入ったときに中間の値を持つ、コンストラクトの動的範囲内で変更しないで、およびコンストラクトから終了時に中間の値を持ちます。

ディレクティブのコンストラクトの構文の範囲では、変数は、新しいスレッドによって割り当てられたプライベート オブジェクトを参照します。

制限、`private`句は、次のとおり。

- 指定されているクラス型の変数を`private`句は、あいまいでないアクセス可能な既定のコンス トラクターをいる必要があります。

- 指定される変数を`private`句は必要ありません、 **const**-型をクラスがない限り、型を修飾、`mutable`メンバー。

- 指定される変数を`private`句が不完全な型または参照型は必要ありません。

- 表示される変数、`reduction`の句、**並列**でディレクティブを指定することはできません、 `private` parallel コンストラクトにバインドされる動作共有ディレクティブの句。