---
title: コンパイラ エラー C2834
ms.date: 11/04/2016
f1_keywords:
- C2834
helpviewer_keywords:
- C2834
ms.assetid: 28f9f6eb-ab2a-4e64-aaaa-9d14f955de41
ms.openlocfilehash: a6a7bc0591fd51c808c303e94eeaaffd6111ffcd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80201930"
---
# <a name="compiler-error-c2834"></a>コンパイラ エラー C2834

' operator operator ' はグローバルに修飾されなければなりません

`new` 演算子と `delete` 演算子は、それらが存在するクラスに関連付けられています。 スコープ解決を使用して `new` のバージョンを選択したり、別のクラスから `delete` したりすることはできません。 `new` または `delete` 演算子の複数の形式を実装するには、追加の仮パラメーターを使用して、演算子のバージョンを作成します。
