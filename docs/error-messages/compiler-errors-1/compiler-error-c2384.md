---
title: コンパイラ エラー C2384 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2384
dev_langs:
- C++
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3aa9ec8a6a94f53123c443a1149df7cdbc95c83
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020460"
---
# <a name="compiler-error-c2384"></a>コンパイラ エラー C2384

'member' : __declspec(thread) をマネージド クラスまたは WinRT クラスのメンバーに適用できません

[スレッド](../../cpp/thread.md)`__declspec`修飾子は、Windows ランタイム クラスまたはマネージのメンバーでは使用できません。

マネージド コード内の静的なスレッド ローカル ストレージは、静的に読み込まれた DLL に対してのみ使用できます。DLL は、プロセスの開始時に静的に読み込まれる必要があります。 Windows ランタイムでは、スレッド ローカル ストレージはサポートされません。

次の例では、C2384 を生成し、C++/CLI コードで修正する方法を示しています。

```
// C2384.cpp
// compile with: /clr /c
public ref class B {
public:
   __declspec( thread ) static int tls_i = 1;   // C2384

   // OK - declare with attribute instead
   [System::ThreadStaticAttribute]
   static int tls_j;
};
```