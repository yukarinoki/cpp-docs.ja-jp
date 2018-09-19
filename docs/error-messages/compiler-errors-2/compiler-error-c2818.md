---
title: コンパイラ エラー C2818 |Microsoft Docs
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
ms.openlocfilehash: f692f52477c988c277f60a689dac5ce83a90acb2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46112045"
---
# <a name="compiler-error-c2818"></a>コンパイラ エラー C2818

アプリケーションは、'operator ->' をオーバー ロードされた 'type' を再帰的な型には

クラスのメンバー アクセス演算子の再定義には、再帰が含まれています。`return`ステートメント。 再定義する、`->`再帰では演算子は、関数をオーバーライドして再帰ルーチン オペレーターからと呼ばれる別の関数に移動する必要があります。