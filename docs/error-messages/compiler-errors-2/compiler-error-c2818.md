---
description: 詳細については、「コンパイラエラー C2818」を参照してください。
title: コンパイラ エラー C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: e258387af290a8070c1c66a56a7523b46482cf99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194788"
---
# <a name="compiler-error-c2818"></a>コンパイラ エラー C2818

オーバーロードされた ' operator-> ' のアプリケーションは型 ' type ' で再帰的です

クラスメンバーアクセス演算子の再定義には、再帰ステートメントが含まれてい **`return`** ます。 再帰を使用して演算子を再定義するには、 `->` 再帰ルーチンを、operator override 関数から呼び出された別の関数に移動する必要があります。
