---
title: コンパイラの警告 (レベル 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 5f9b8ce710879913fdad1be5c0f22f8e3f4ed9d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408330"
---
# <a name="compiler-warning-level-1-c4311"></a>コンパイラの警告 (レベル 1) C4311

'変数' : ポインターを '型' から '型' へ切り詰めます。

この警告は 64 ビット ポインターの切り捨ての問題を検出します。 たとえば、コードが 64 ビット アーキテクチャ用にコンパイルされている場合、ポインターの値 (64 ビット) は `int` (32 ビット) に代入されるときに切り詰められます。 詳細については、次を参照してください。[ポインターの使用規則](/windows/desktop/WinProg64/rules-for-using-pointers)します。

警告 C4311 の一般的な原因に関する詳細については、次を参照してください。[一般的なコンパイラ エラー](/windows/desktop/WinProg64/common-compiler-errors)します。

次のコード例では、64 ビットをターゲットとしたコンパイル時に警告 C4311 を生成し、修正する方法を示します。

```
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```