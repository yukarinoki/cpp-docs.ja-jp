---
description: '詳細情報: コンパイラの警告 (レベル 1) C4311'
title: コンパイラの警告 (レベル 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 30e630744a6c86604ea3d5a748d3b64316623c25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311670"
---
# <a name="compiler-warning-level-1-c4311"></a>コンパイラの警告 (レベル 1) C4311

'変数' : ポインターを '型' から '型' へ切り詰めます。

この警告は 64 ビット ポインターの切り捨ての問題を検出します。 たとえば、コードが64ビットアーキテクチャ用にコンパイルされている場合、ポインターの値 (64 ビット) は、(32 ビット) に割り当てられている場合は切り捨てられ **`int`** ます。 詳細については、「 [ポインターを使用するための規則](/windows/win32/WinProg64/rules-for-using-pointers)」を参照してください。

警告 C4311 の一般的な原因の詳細については、「 [一般的なコンパイラエラー](/windows/win32/WinProg64/common-compiler-errors)」を参照してください。

次のコード例では、64 ビットをターゲットとしたコンパイル時に警告 C4311 を生成し、修正する方法を示します。

```cpp
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```
