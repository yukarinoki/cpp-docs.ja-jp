---
title: コンパイラ エラー C3893 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3893
dev_langs:
- C++
helpviewer_keywords:
- C3893
ms.assetid: 90d52eae-6ef2-4db1-b7ad-92f9e8b140fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 857d13de61f03bf0784d8cd10ad092d16f7acdaa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087048"
---
# <a name="compiler-error-c3893"></a>コンパイラ エラー C3893

'var': initonly データ メンバーの左辺値の使用は、クラス 'type_name' のインスタンス コンス トラクターでのみ使用できます。

静的[initonly](../../dotnet/initonly-cpp-cli.md)データ メンバーは、静的コンス トラクターで取得された、アドレスを持つことができますのみです。

インスタンス (静的ではない) initonly データ メンバーは、取得されたインスタンス (静的ではない) コンス トラクターで、アドレスだけを設定できます。

次の例では、C3893 が生成されます。

```
// C3893.cpp
// compile with: /clr
ref struct Y1 {
   Y1() : data_var(0) {
      int% i = data_var;   // OK
   }
   initonly int data_var;
};

int main(){
   Y1^ y= gcnew Y1;
   int% i = y->data_var;   // C3893
}
```