---
description: 詳細については、「コンパイラエラー C2384」を参照してください。
title: コンパイラ エラー C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: f72db8d5beb871bbb9adf1cdc234769705db2b9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272514"
---
# <a name="compiler-error-c2384"></a>コンパイラ エラー C2384

'member' : __declspec(thread) をマネージド クラスまたは WinRT クラスのメンバーに適用できません

[スレッド](../../cpp/thread.md) **`__declspec`** 修飾子は、マネージクラスまたは Windows ランタイムクラスのメンバーでは使用できません。

マネージド コード内の静的なスレッド ローカル ストレージは、静的に読み込まれた DLL に対してのみ使用できます。DLL は、プロセスの開始時に静的に読み込まれる必要があります。 Windows ランタイムでは、スレッド ローカル ストレージはサポートされません。

次の例では、C2384 を生成し、C++/CLI コードで修正する方法を示しています。

```cpp
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
