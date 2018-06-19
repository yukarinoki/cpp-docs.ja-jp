---
title: コンパイラ エラー C2834 |Microsoft ドキュメント
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
ms.openlocfilehash: 4eb4fb992f9213c4a4b456f786fd8f81308cec12
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33244785"
---
# <a name="compiler-error-c2834"></a>コンパイラ エラー C2834
'operator 演算子' はグローバルに修飾する必要があります。  
  
 `new`と`delete`演算子はクラスに関連付けられて、その場所します。 バージョンを選択するスコープ解決演算子を使用することはできません`new`または`delete`別のクラスからです。 複数のフォームを実装する、`new`または`delete`演算子は、余分の仮パラメーターを持つ演算子のバージョンを作成します。