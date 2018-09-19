---
title: コンパイラの警告 C4687 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4687
dev_langs:
- C++
helpviewer_keywords:
- C4687
ms.assetid: 2f28e0b1-7358-4c88-bd70-aad8f0aa004c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9d813ce6d666431cfc3f74d1409012a4a0aec897
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118714"
---
# <a name="compiler-warning-c4687"></a>コンパイラの警告 C4687

'class': シールドされた抽象クラスはインターフェイス 'interface' を実装できません

シールされた抽象型は、通常は静的メンバー関数を保持する便利なのみできます。

詳細については、次を参照してください。[抽象](../../windows/abstract-cpp-component-extensions.md)と[シール](../../windows/sealed-cpp-component-extensions.md)します。

C4687 をエラーとして既定で発行されます。 C4687 を抑制することができます、[警告](../../preprocessor/warning.md)プラグマ。 シールされた抽象型にインターフェイスを実装する場合は、C4687 を抑制することができます。

## <a name="example"></a>例

次の例では、C4687 が生成されます。

```
// C4687.cpp
// compile with: /clr /c
interface class A {};

ref struct B sealed abstract : A {};   // C4687
ref struct C sealed : A {};   // OK
ref struct D abstract : A {};   // OK
```