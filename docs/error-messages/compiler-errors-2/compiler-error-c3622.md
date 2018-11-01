---
title: コンパイラ エラー C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 69565a1a2d159623bca927a94543834d18c13299
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518093"
---
# <a name="compiler-error-c3622"></a>コンパイラ エラー C3622

'class': 'keyword' をインスタンス化できないように宣言されたクラス

としてマークされたクラスをインスタンス化しようとした[抽象](../../windows/abstract-cpp-component-extensions.md)します。 としてマークされているクラス`abstract`、基本クラスであることができますが、インスタンス化できません。

## <a name="example"></a>例

次の例では、C3622 が生成されます。

```
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
