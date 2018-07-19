---
title: コンパイラ エラー C2099 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28f525676f6d9238838f0dbc245d9771f99ebeb5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170818"
---
# <a name="compiler-error-c2099"></a>コンパイラ エラー C2099
初期化子が定数ではありません。  
  
 このエラーは C コンパイラでのみ発生し、非自動変数に対してのみ発生します。  コンパイラは、プログラムの開始時に非自動変数を初期化します。変数の初期化に使用される値は定数でなければなりません。  
  
## <a name="example"></a>例  
 次の例では C2099 エラーが生成されます。  
  
```  
// C2099.c  
int j;  
int *p;  
j = *p;   // C2099 *p is not a constant  
```  
  
## <a name="example"></a>例  
 浮動小数点の有効桁数の環境設定 (詳細については「 **_controlfp_s** 」を参照) が実行時とコンパイル時では異なるため、 [/fp:strict](../../c-runtime-library/reference/controlfp-s.md) で式への定数の圧縮を実行できない場合にも、C2099 が発生します。  
  
 定数の圧縮が失敗すると、コンパイラは C で使用できない動的な初期化を呼び出します。  
  
 このエラーを解決するには、モジュールを .cpp ファイルとしてコンパイルするか、式を簡単にします。  
  
 詳細については、「 [/fp (Specify Floating-Point Behavior)](../../build/reference/fp-specify-floating-point-behavior.md)」を参照してください。  
  
 次の例では C2099 エラーが生成されます。  
  
```  
// C2099_2.c  
// compile with: /fp:strict /c  
float X = 2.0 - 1.0;   // C2099  
float X2 = 1.0;   // OK  
```