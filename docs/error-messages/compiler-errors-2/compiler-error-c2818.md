---
title: コンパイラ エラー C2818 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2818
dev_langs:
- C++
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10d7f419d528fcd2445b82e29d92442002624909
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2818"></a>コンパイラ エラー C2818
アプリケーションは、'operator ->' をオーバー ロードされた 'type' を型全体に再帰的には  
  
 クラス メンバー アクセス演算子の再定義を含む再帰的な`return`ステートメントです。 再定義する、`->`再帰では演算子、関数をオーバーライドして、再帰ルーチン オペレーターからと呼ばれる別の関数に移動する必要があります。