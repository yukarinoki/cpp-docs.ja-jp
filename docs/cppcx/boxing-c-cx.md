---
title: ボックス化 (C + + CX) |Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e70b908bddbf7034e1d60f16cb0e492c0a707586
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598881"
---
# <a name="boxing-ccx"></a>ボックス化 (C++/CX)
*ボックス化* とは、入力型として [Platform::Object^](http://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)を取るメソッドに変数が渡されたときに、ref クラス内で、値の型変数 ( `int`Windows::Foundation::DateTime [など) または基本的スカラー型 (](../cppcx/platform-object-class.md) など) をラップすることです。  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Object^ パラメーターへの値の型の引き渡し  
 変数を明示的にボックス化しなくても、型 [Platform::Object^](../cppcx/platform-object-class.md)のメソッド パラメーターに渡すことはできますが、以前にボックス化されたことがある値を取得するときは、明示的にキャストして元の型に戻す必要があります。  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform::ibox を使用して\<T > を null 許容値型のサポート  
 C# および Visual Basic では、null 許容値型の概念をサポートしています。 C++/cli 使用することができます、CX、 `Platform::IBox<T>` null 許容値型パラメーターをサポートするパブリック メソッドを公開する型。 次の例は c++/cli CX のパブリック メソッドを c# 呼び出し元が null の引数を渡すと null を返します。  
  
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