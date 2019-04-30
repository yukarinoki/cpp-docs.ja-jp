---
title: コンパイラの警告 (レベル 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: 0a9ceb332888e306b8cb3bcbe1832f773d02d63d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401944"
---
# <a name="compiler-warning-level-3-c4414"></a>コンパイラの警告 (レベル 3) C4414

'function': 関数へのジャンプを短いが近くに変換

短いジャンプは、命令から制限の範囲内のアドレスに分岐するコンパクトな命令を生成します。 命令にジャンプし、ターゲット アドレスなど、関数定義の間の距離を表す短いオフセットが含まれています。 リンク中には、関数を短いオフセットから到達可能な範囲外に移動する移動または対象のリンク時の最適化が関数にあります。 コンパイラは、近いまたはまでのいずれかに、jmp 命令を必要とすると、ジャンプの特殊なレコードを生成する必要があります。 コンパイラでは、変換が行われます。

たとえば、次のコードでは、C4414 が生成されます。

```
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```