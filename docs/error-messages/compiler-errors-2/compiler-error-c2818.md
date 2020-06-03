---
title: コンパイラ エラー C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: 00952e55f1b732bd9af3733f5c0ec575a39116fe
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202112"
---
# <a name="compiler-error-c2818"></a>コンパイラ エラー C2818

オーバーロードされた ' operator-> ' のアプリケーションは型 ' type ' で再帰的です

クラスメンバーアクセス演算子の再定義には、再帰 `return` ステートメントが含まれています。 再帰を使用して `->` 演算子を再定義するには、再帰ルーチンを、operator override 関数から呼び出される別の関数に移動する必要があります。
