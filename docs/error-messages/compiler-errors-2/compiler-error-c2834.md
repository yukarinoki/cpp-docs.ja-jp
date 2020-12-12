---
description: 詳細については、「コンパイラエラー C2834」を参照してください。
title: コンパイラ エラー C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: 6f74853f264af653988ed77ddb9a9c7935f3c542
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194437"
---
# <a name="compiler-error-c2834"></a>コンパイラ エラー C2834

' operator operator ' はグローバルに修飾されなければなりません

`new`演算子と `delete` 演算子は、それらが存在するクラスに関連付けられています。 スコープ解決を使用して、 `new` または別のクラスのバージョンを選択することはできません `delete` 。 Or 演算子の複数の形式を実装するに `new` は `delete` 、追加の仮パラメーターを使用して、演算子のバージョンを作成します。
