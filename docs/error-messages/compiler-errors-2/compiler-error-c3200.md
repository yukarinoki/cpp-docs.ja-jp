---
title: コンパイラ エラー C3200 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3200
dev_langs:
- C++
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa34ea006b06138290417387bd393589b630aa4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33251308"
---
# <a name="compiler-error-c3200"></a>コンパイラ エラー C3200
'template': テンプレート パラメーター 'parameter' に対する無効なテンプレート引数には、クラス テンプレートが必要です。  
  
 クラス テンプレートに無効な引数が渡されます。 クラス テンプレートは、パラメーターとしてテンプレートを受け付けます。 次の例では、呼び出す`Y<int, int> aY`C3200 が生成されます。 最初のパラメーターをテンプレートをなどある必要があります`Y<X, int> aY`です。  
  
```  
// C3200.cpp  
template<typename T>  
class X  
{  
};  
  
template<template<typename U> class T1, typename T2>  
class Y  
{  
};  
  
int main()  
{  
   Y<int, int> y;   // C3200  
}  
```