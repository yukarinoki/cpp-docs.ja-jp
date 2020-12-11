---
description: 詳細については、「コンパイラエラー C2722」を参照してください。
title: コンパイラエラー C2722
ms.date: 11/04/2016
f1_keywords:
- C2722
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
ms.openlocfilehash: 10d1af61f0b82621469f2d6e91d97296c59f22cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155593"
---
# <a name="compiler-error-c2722"></a>コンパイラエラー C2722

':: operator ': 次の演算子コマンドが正しくありません。' operator operator ' を使用します

`operator`ステートメント `::new` はまたは `::delete` を再定義します。 `new`And `delete` 演算子はグローバルであるため、スコープ解決演算子 ( `::` ) は無意味です。 `::` 演算子を削除します。
