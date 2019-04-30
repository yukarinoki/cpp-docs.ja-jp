---
title: コンパイラ エラー C2062
ms.date: 11/04/2016
f1_keywords:
- C2062
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
ms.openlocfilehash: dcfac9629a90b82744f87ec105c30301b2102cdf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408746"
---
# <a name="compiler-error-c2062"></a>コンパイラ エラー C2062

型 'type' の予期しません。

コンパイラは、型名を予期していません。

次の例では、C2062 が生成されます。

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 発生することもまた、コンパイラの方法は、コンス トラクターのパラメーター リストで定義されていない型の処理。 コンパイラには、未定義の型 (スペル ミスですか?) が発生すると、コンス トラクターは、式を指定し、c2062 と仮定します。 を解決するには、コンス トラクターのパラメーター リストで定義された型をのみ使用します。