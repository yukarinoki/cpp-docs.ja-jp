---
description: 詳細については、「コンパイラエラー C2492」を参照してください。
title: コンパイラ エラー C2492
ms.date: 11/04/2016
f1_keywords:
- C2492
helpviewer_keywords:
- C2492
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
ms.openlocfilehash: ef31b2136a2cfc0422832899dba14ffb3108d965
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283676"
---
# <a name="compiler-error-c2492"></a>コンパイラ エラー C2492

'*variable*': スレッドストレージ存続期間を持つデータは dll インターフェイスを含むことはできません

変数は、 [スレッド](../../cpp/thread.md) 属性と DLL インターフェイスを使用して宣言されます。 変数のアドレス `thread` は実行時までわからないため、DLL のインポートまたはエクスポートにリンクすることはできません。

次の例では、C2492 が生成されます。

```cpp
// C2492.cpp
// compile with: /c
class C {
public:
   char   ch;
};

__declspec(dllexport) __declspec(thread) C c_1;   // C2492
__declspec(thread) C c_1;   // OK
```
