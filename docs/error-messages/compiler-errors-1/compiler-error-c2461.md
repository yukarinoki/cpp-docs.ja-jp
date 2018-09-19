---
title: コンパイラ エラー C2461 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39d58b315fdd7e3c4e1899041cebf8400813ed40
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029300"
---
# <a name="compiler-error-c2461"></a>コンパイラ エラー C2461

> '*クラス*': コンス トラクター構文の正式なパラメーターがありません

クラスのコンス トラクターは、仮パラメーターを指定しません。 コンス トラクターの宣言には、仮パラメーター リストを指定する必要があります。 一覧を空にすることができます。

この問題を解決するには、宣言の後に 1 組のかっこを追加*クラス*:: **クラス*します。

## <a name="example"></a>例

次の例では、C2461 を修正する方法を示します。

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```