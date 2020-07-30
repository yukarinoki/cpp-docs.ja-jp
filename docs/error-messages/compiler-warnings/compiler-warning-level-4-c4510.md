---
title: コンパイラの警告 (レベル 4) C4510
description: コンパイラの警告 C4510 の説明と解決策。
ms.date: 09/22/2019
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: e4bb688266d9fe638978d2d3fa2666b83b3e6cc9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225255"
---
# <a name="compiler-warning-level-4-c4510"></a>コンパイラの警告 (レベル 4) C4510

> '*class*': 既定のコンストラクターを生成できませんでした

コンパイラは、ユーザー定義のコンストラクターを持たない、指定されたクラスの既定のコンストラクターを生成できません。 この型のオブジェクトは作成できません。

次のように、コンパイラが既定のコンストラクターを生成しないようにする状況がいくつかあります。

- **`const`** データメンバー。

- 参照であるデータメンバー。

この問題を解決するには、これらのメンバーを初期化するクラスのユーザー定義の既定のコンストラクターを作成します。
