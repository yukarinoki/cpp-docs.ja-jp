---
title: コンパイラ エラー C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 1909fb999dd0f60224029b726f773c11fa69ee40
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347156"
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