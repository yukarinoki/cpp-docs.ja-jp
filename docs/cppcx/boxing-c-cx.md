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
ms.openlocfilehash: 7e9ab84bf840f01fbb22ef3b2510056338d10c74
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44108384"
---
# <a name="boxing-ccx"></a>ボックス化 (C++/CX)

*ボックス化*など、値型の変数をラッピングが[::datetime](https://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)— または基本的スカラー型など、 `int`— を受け取るメソッドに変数が渡されたときに、ref クラスで[Platform::object ^](../cppcx/platform-object-class.md)入力型として。

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

[型システム (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[キャスト (C++/CX)](../cppcx/casting-c-cx.md)<br/>
[Visual C 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間参照](../cppcx/namespaces-reference-c-cx.md)