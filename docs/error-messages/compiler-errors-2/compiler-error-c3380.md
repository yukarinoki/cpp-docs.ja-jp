---
title: コンパイラ エラー C3380 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3380
dev_langs:
- C++
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 315031946f9a89f53097e4c2371286fba213f698
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33252449"
---
# <a name="compiler-error-c3380"></a>コンパイラ エラー C3380
'class': 無効なアセンブリ アクセス指定子です。'public' と 'private' のみ使用できます  
  
 マネージ クラスや構造体に適用される場合、 [public](../../cpp/public-cpp.md) キーワードと [private](../../cpp/private-cpp.md) キーワードはクラスがアセンブリ メタデータを通じて公開されるかどうかを示します。 `public` /clr `private` を指定してコンパイルされるプログラムのクラスには、 [または](../../build/reference/clr-common-language-runtime-compilation.md)以外は適用できません。  
  
 `ref`と`value`と共に使用する場合、キーワード[/clr](../../build/reference/clr-common-language-runtime-compilation.md)、クラスが管理されていることを示します (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md))。  
  
 次の例では C3380 が生成されます。  
  
```  
// C3380_2.cpp  
// compile with: /clr  
protected ref class A {   // C3380  
// try the following line instead  
// ref class A {  
public:  
   static int i = 9;  
};  
  
int main() {  
   A^ myA = gcnew A;  
   System::Console::WriteLine(myA->i);  
}  
```  
