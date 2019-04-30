---
title: コンパイラの警告 (レベル 1) C4407
ms.date: 11/04/2016
f1_keywords:
- C4407
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
ms.openlocfilehash: 5142e3800f3ad716166a27e3b0407a40999b5746
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408408"
---
# <a name="compiler-warning-level-1-c4407"></a>コンパイラの警告 (レベル 1) C4407

メンバー表記に異なるポインターの間でのキャスト、コンパイラは正しくないコードを生成可能性があります。

不正なキャストが検出されました。

Visual C 2005 で行ったコンパイラ準拠作業により C4407 で生成されることができます。 修飾名とアドレス演算子に今すぐメンバーへのポインターが必要です (&)。

C4407 は、複数の継承メンバーへのポインター - を単一継承メンバーへのポインターの間でキャストする場合に発生します。 これはうまくができない場合があります単一継承メンバーへのポインターの表現は十分な情報を保持しないため。 コンパイルすると、 **/vmm**役立つ場合があります (詳細については、次を参照してください。 [/vmm、/vms、/vmv (通常)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md))。 基本クラスを再配置することもできます。コンパイラは、基底クラスは派生クラスからゼロ以外のオフセットにあるために、変換に情報が失われる検出します。

次の例では、C4407 が生成されます。

```
// C4407.cpp
// compile with: /W1 /c
struct C1 {};
struct C2 {};
struct C3 : C1, C2 {};

typedef void(C3::*PMF_C3)();
typedef void(C2::*PMF_C2)();

PMF_C2 f1(PMF_C3 pmf) {
   return (PMF_C2)pmf;   // C4407, change type of cast,
   // or reverse base class inheritance of C3 (i.e. : C2, C1)
}
```