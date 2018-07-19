---
title: コンパイラ エラー C2862 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2862
dev_langs:
- C++
helpviewer_keywords:
- C2862
ms.assetid: c04d8499-b799-48a1-9fb4-7902a0b0ac8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bb9aac4a7c4bd43dcd4f0e688c955619133d375f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247516"
---
# <a name="compiler-error-c2862"></a>コンパイラ エラー C2862
'interface': インターフェイスはパブリック メンバーを持つことができますのみ  
  
 保護されているし、プライベート メンバーは、他のメンバー関数からのみアクセスできます。 いずれかのメンバーの実装が提供されませんので、このようなメンバーは、インターフェイスで使用できるはありません。  
  
 次のサンプル C2862 が生成されます。  
  
```  
// C2862.cpp  
// compile with: /c  
#include <unknwn.h>  
  
[object, uuid="60719E20-EF37-11D1-978D-0000F805D73B"]  
__interface IMyInterface {  
   HRESULT mf1(void);   // OK  
protected:  
   HRESULT mf2(int *b);   // C2862  
private:  
   HRESULT mf3(int *c);   // C2862  
};  
```