---
title: コンパイラの警告 (レベル 1) C4407 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4407
dev_langs:
- C++
helpviewer_keywords:
- C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cbc02c32463703f658cef1d5756926311d89b193
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282952"
---
# <a name="compiler-warning-level-1-c4407"></a>コンパイラの警告 (レベル 1) C4407
メンバーに対して異なるポインターの間でキャスト、コンパイラは正しくないコードを生成可能性があります。  
  
 不正なキャストが検出されました。  
  
 Visual C 2005 で行われたコンパイラ準拠作業により C4407 で生成されることができます。 修飾名とアドレス演算子に今すぐメンバーへのポインターが必要です (&)。  
  
 C4407 は、間、複数の継承ポインター メンバーへの単一継承にメンバーのポインターにキャストする場合に発生することができます。 場合によっては有効しますが、できない場合があります単一継承メンバーへのポインター表現が十分な情報を保持しないため。 コンパイルする、 **/vmm 最適化**役立つ場合があります (詳細については、次を参照してください。 [/vmm の最適化、/vms、/vmv (通常)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md))。 試すこともできます。 基本クラスを再配置コンパイラは基本クラスが派生クラスから 0 以外のオフセットであるために、変換に情報の損失検出します。  
  
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