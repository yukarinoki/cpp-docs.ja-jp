---
title: コンパイラエラー C2722
ms.date: 11/04/2016
f1_keywords:
- C2722
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
ms.openlocfilehash: 7426df1970dee58cd4363ee345e2286165e375b6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202177"
---
# <a name="compiler-error-c2722"></a>コンパイラエラー C2722

':: operator ': 次の演算子コマンドが正しくありません。' operator operator ' を使用します

`operator` ステートメントは、`::new` または `::delete`を再定義します。 `new` 演算子と `delete` 演算子はグローバルであるため、スコープ解決演算子 (`::`) は無意味です。 `::` 演算子を削除します。
