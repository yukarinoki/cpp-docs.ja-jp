---
description: 詳細については、「コンパイラエラー C2946」を参照してください。
title: コンパイラ エラー C2946
ms.date: 11/04/2016
f1_keywords:
- C2946
helpviewer_keywords:
- C2946
ms.assetid: c86dfbfc-7702-4f09-8a53-d205710e99c2
ms.openlocfilehash: 7a74b17c10acd55a254c0d7fba5c8269689e3094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249504"
---
# <a name="compiler-error-c2946"></a>コンパイラ エラー C2946

明示的なインスタンス生成。'class' はテンプレート クラスの特殊化ではありません

非テンプレート クラスは明示的にインスタンス化できません。

## <a name="example"></a>例

次の例では C2946 が生成されます。

```cpp
// C2946.cpp
class C {};
template C;  // C2946
int main() {}
```
