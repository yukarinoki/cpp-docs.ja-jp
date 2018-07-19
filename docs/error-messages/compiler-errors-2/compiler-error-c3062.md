---
title: コンパイラ エラー C3062 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3062
dev_langs:
- C++
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da507511cb5f091d5d9432bbfeb36951e3f43c6f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33250567"
---
# <a name="compiler-error-c3062"></a>コンパイラ エラー C3062
'enum': 基になる型が 'type' であるために、列挙子から値が必要です  
  
 列挙体の基になる型を指定できます。 ただし、一部の種類では、列挙子ごとに値を割り当てることが必要です。  
  
 列挙型の詳細については、次を参照してください。[列挙型クラス](../../windows/enum-class-cpp-component-extensions.md)です。  
  
 次の例では、C3062 が生成されます。  
  
```  
// C3062.cpp  
// compile with: /clr  
  
enum class MyEnum : bool { a };   // C3062  
enum class MyEnum2 : bool { a = true};   // OK  
```