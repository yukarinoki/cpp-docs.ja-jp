---
title: コンパイラの警告 (レベル 3) C4240 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4240
dev_langs:
- C++
helpviewer_keywords:
- C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f0691230454ffd935d67c99f58b857cdc1ce0f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4240"></a>コンパイラの警告 (レベル 3) C4240
使用される標準の拡張機能: 'のアクセス指定子' である 'classname' が 'アクセス指定子'、以前のバージョンで現在定義へのアクセスが定義されました  
  
 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))、入れ子になったクラスに、アクセスを変更することはできません。 既定 Microsoft 拡張機能 (/Ze)、することができますがこの警告が発生します。  
  
## <a name="example"></a>例  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```