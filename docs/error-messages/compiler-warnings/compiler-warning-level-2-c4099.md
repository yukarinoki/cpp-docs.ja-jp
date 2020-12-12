---
description: '詳細情報: コンパイラの警告 (レベル 2) C4099'
title: コンパイラの警告 (レベル 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: c35ce10560ca81f9457f6a21c4c55d96996e7645
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326518"
---
# <a name="compiler-warning-level-2-c4099"></a>コンパイラの警告 (レベル 2) C4099

' identifier ': ' objecttype1 ' を使用して最初に検出された型名は ' objecttype2 ' を使用して表示されるようになりました

構造体として宣言されたオブジェクトは、クラスとして定義されます。また、クラスとして宣言されたオブジェクトは、構造体として定義されます。 コンパイラは、定義で指定された型を使用します。

## <a name="example"></a>例

次の例では、C4099 が生成されます。

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```
