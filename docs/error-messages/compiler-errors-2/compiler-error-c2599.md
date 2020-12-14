---
description: 詳細については、「コンパイラエラー C2599」を参照してください。
title: コンパイラ エラー C2599
ms.date: 11/04/2016
f1_keywords:
- C2599
helpviewer_keywords:
- C2599
ms.assetid: 88515f36-7589-47e2-862e-0de8b18d6668
ms.openlocfilehash: e1365ee2570d4af524f7e4dbd36a411916efb9c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312047"
---
# <a name="compiler-error-c2599"></a>コンパイラ エラー C2599

' enum ': 列挙型の事前宣言は許可されていません

コンパイラは、マネージ列挙型の事前宣言をサポートしなくなりました。

Enum 型の事前宣言は、 [/za](../../build/reference/za-ze-disable-language-extensions.md)では許可されていません。

次の例では、C2599 が生成されます。

```cpp
// C2599.cpp
// compile with: /clr /c
enum class Status;   // C2599

enum class Status2 { stop2, hold2, go2};

ref struct MyStruct {
   // Delete the following line to resolve.
   Status m_status;

   Status2 m_status2;   // OK
};

enum class Status { stop, hold, go };
```
