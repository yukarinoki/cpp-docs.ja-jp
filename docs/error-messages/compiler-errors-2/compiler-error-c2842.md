---
title: コンパイラ エラー C2842 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2842
dev_langs:
- C++
helpviewer_keywords:
- C2842
ms.assetid: 8674f08d-9f50-46ad-9229-abc6b74fa0e5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fe0a95edfa484eb8606b914424e52483c4c1c52d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245297"
---
# <a name="compiler-error-c2842"></a>コンパイラ エラー C2842
'class' : マネージ型または WinRT 型はそれ自体の 'operator new' または 'operator delete' を定義できません  
  
 独自に定義することができます * * 演算子の new または**演算子 delete**ネイティブ ヒープにメモリの割り当てを管理します。 ただし、これらの演算子はマネージ ヒープでのみ割り当てられるため、参照クラスでは定義できません。  

  
 詳細については、次を参照してください。[ユーザー定義の演算子 (C + + CLI)](../../dotnet/user-defined-operators-cpp-cli.md)です。  
  
## <a name="example"></a>例  
 次の例では C2842 が生成されます。  
  
```  
// C2842.cpp  
// compile with: /clr /c  
ref class G {  
   void* operator new( size_t nSize );   // C2842  
};  
```  
