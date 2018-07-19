---
title: ボックス化 (C + + CX) |Microsoft ドキュメント
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e47313f65c4129bbc6fbf0a7bfbf698eb092f9f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33086500"
---
# <a name="boxing-ccx"></a>ボックス化 (C++/CX)
*ボックス化* とは、入力型として [Platform::Object^](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)を取るメソッドに変数が渡されたときに、ref クラス内で、値の型変数 ( `int`Windows::Foundation::DateTime [など) または基本的スカラー型 (](../cppcx/platform-object-class.md) など) をラップすることです。  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Object^ パラメーターへの値の型の引き渡し  
 変数を明示的にボックス化しなくても、型 [Platform::Object^](../cppcx/platform-object-class.md)のメソッド パラメーターに渡すことはできますが、以前にボックス化されたことがある値を取得するときは、明示的にキャストして元の型に戻す必要があります。  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform::ibox 使用\<T > を null 許容値型をサポートするには  
 C# および Visual Basic では、null 許容値型の概念をサポートしています。 C + + CX、行うこともできます、 `Platform::IBox<T>` null 許容値型パラメーターをサポートするパブリック メソッドを公開する型。 次の例は、C + + CX のパブリック メソッド、c# 呼び出し元が null の引数を渡すと null を返すにします。  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 C# XAML クライアントでは、これを次のように利用できます。  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>関連項目  
 [型システム (C++/CX)](../cppcx/type-system-c-cx.md)   
 [キャスト (C + + CX)](../cppcx/casting-c-cx.md)   
 [Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)   
 [名前空間参照](../cppcx/namespaces-reference-c-cx.md)