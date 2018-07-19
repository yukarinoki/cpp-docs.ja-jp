---
title: コンパイラ エラー C2348 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2348
dev_langs:
- C++
helpviewer_keywords:
- C2348
ms.assetid: 4c4d701f-ccf1-46fe-9ddb-3f341684f269
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9728b044d05374e46b685df385409ddc3cb614f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33222242"
---
# <a name="compiler-error-c2348"></a>コンパイラ エラー C2348
'type name': C スタイルの集合ではありません、埋め込み IDL 内でエクスポートできません。  
  
 配置する、`struct`を含む .idl ファイル、[エクスポート](../../windows/export.md)、属性、`struct`データのみを含める必要があります。  
  
 次の例では、C2348 が生成されます。  
  
```  
// C2348.cpp  
// C2348 error expected  
[ module(name="SimpleMidlTest") ];  
  
[export]  
struct Point {  
   // Delete the following two lines to resolve.  
   Point() : m_i(0), m_j(0) {}  
   Point(int i, int j) : m_i(i), m_j(j) {}  
  
   int m_i;  
   int m_j;  
};  
```