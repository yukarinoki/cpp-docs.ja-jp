---
title: コンパイラの警告 (レベル 1) C4692 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4692
dev_langs:
- C++
helpviewer_keywords:
- C4692
ms.assetid: f6fb3acc-8228-491a-9c30-ce302d8a9c75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a908aae7e561f78514cda1f31b78060ce88d90ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4692"></a>コンパイラの警告 (レベル 1) C4692
'関数': 公開されたメンバーのシグネチャはアセンブリ プライベート ネイティブ型 'native_type' を含んでいます  
  
 アセンブリの外部で参照できる型に、アセンブリの外部で参照できないネイティブ型をシグネチャに含むメンバー関数が含まれています。 このため、そのメンバー関数は、それに含まれる型がアセンブリの外部でインスタンス化されている場合は呼び出すことができません。  
  
 詳細については、次を参照してください。[可視性を入力](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility)です。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4692 を生成します。  
  
```  
// C4692.cpp  
// compile with: /W1 /c /clr  
#pragma warning(default:4692)  
class Private_Native_Class {};  
public class Public_Native_Class {};  
public ref class Public_Ref_Class {  
public:  
   void Test(Private_Native_Class *) {}   // C4692  
   void Test2(Public_Native_Class *) {}   // OK  
};  
```