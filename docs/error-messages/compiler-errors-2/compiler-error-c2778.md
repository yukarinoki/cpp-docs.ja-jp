---
title: コンパイラ エラー C2778 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2778
dev_langs:
- C++
helpviewer_keywords:
- C2778
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f8747c0f2d0434f034ac0a0b84dcce510de0e96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235092"
---
# <a name="compiler-error-c2778"></a>コンパイラ エラー C2778
__declspec(uuid()) で不適切な形式の GUID  
  
 正しくない GUID が指定された、 [uuid](../../cpp/uuid-cpp.md)拡張属性。  
  
 GUID は、次の形式の 16 進数の文字列である必要があります。  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 `uuid`拡張属性がで認識される文字列を受け取る[CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589)中かっこの区切り記号の有無、します。  
  
 次の例では、C2778 が生成されます。  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```