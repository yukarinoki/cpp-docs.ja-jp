---
title: コンパイラ エラー C2834 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2834
dev_langs:
- C++
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b94e1a3fba9bc3589af020340651b4546347cf1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089347"
---
# <a name="compiler-error-c2834"></a>コンパイラ エラー C2834

'operator 演算子' はグローバルに修飾する必要があります。

`new`と`delete`演算子に関連付けられているクラスは、その場所します。 バージョンを選択するスコープ解決演算子を使用することはできません`new`または`delete`別のクラスから。 複数のフォームを実装するために、`new`または`delete`演算子が余分の仮パラメーターを持つ演算子のバージョンを作成します。