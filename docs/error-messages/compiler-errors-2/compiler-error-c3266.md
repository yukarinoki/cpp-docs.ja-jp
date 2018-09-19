---
title: コンパイラ エラー C3266 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3266
dev_langs:
- C++
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1c796f4784c61fc38a725112b40781f30fa6926
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46069561"
---
# <a name="compiler-error-c3266"></a>コンパイラ エラー C3266

'class' : クラス コンストラクターは 'void' パラメーター リストを必要とします

/clr プログラミングを使用するクラスのクラス コンストラクターは、パラメーターを受け取ることはできません。

次の例では C3266 が生成されます。

```
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
