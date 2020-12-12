---
description: 詳細については、「コンパイラエラー C3005」を参照してください。
title: コンパイラ エラー C3005
ms.date: 11/04/2016
f1_keywords:
- C3005
helpviewer_keywords:
- C3005
ms.assetid: 30bad565-e79f-4c3f-82cb-a74bd0baab8f
ms.openlocfilehash: df9e0c94aa0ba47e1c2f63858419c15881f9bd74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272423"
---
# <a name="compiler-error-c3005"></a>コンパイラ エラー C3005

'error_text' : OpenMP 'directive' ディレクティブでは予期しないトークンです

OpenMP ディレクティブの形式が正しくありません。

次の例では C3005 が生成されます。

```c
// C3005.c
// compile with: /openmp
int main()
{
   #pragma omp parallel + for   // C3005
}
```

プラグマと同じ行で始め中かっこを使用した場合も、C3005 が発生します。

```c
// C3005b.c
// compile with: /openmp
int main() {
   #pragma omp parallel {   // C3005 put open brace on next line
   lbl2:;
   }
   goto lbl2;
}
```
