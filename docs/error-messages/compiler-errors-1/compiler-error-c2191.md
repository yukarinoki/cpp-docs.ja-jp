---
description: 詳細については、「コンパイラエラー C2191」を参照してください。
title: コンパイラ エラー C2191
ms.date: 11/04/2016
f1_keywords:
- C2191
helpviewer_keywords:
- C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
ms.openlocfilehash: b3b2133e70eeae566a972b0e5db11105b316d6f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337663"
---
# <a name="compiler-error-c2191"></a>コンパイラ エラー C2191

2番目のパラメーターリストが最初より長くなっています

C 関数が、より長いパラメーターリストを使用して2回宣言されました。 C は、オーバーロードされた関数をサポートしていません。

## <a name="example"></a>例

次の例では、C2191 が生成されます。

```c
// C2191.c
// compile with: /Za /c
void func( int );
void func( int, float );   // C2191 different parameter list
void func2( int, float );   // OK
```
