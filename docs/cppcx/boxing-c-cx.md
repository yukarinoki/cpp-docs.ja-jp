---
description: '詳細情報: ボックス化 (C++/CX)'
title: ボックス化 (C++/CX)
ms.date: 12/30/2016
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
ms.openlocfilehash: 50b7f3f071fcd0109a85fb24985024666bd8fad3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302739"
---
# <a name="boxing-ccx"></a>ボックス化 (C++/CX)

*ボックス* 化は、入力型として Platform:: Object ^ を取るメソッドに変数が渡されたときに、ref クラス内で、 [Windows:: Foundation::D atetime](/uwp/api/windows.foundation.datetime)などの値型の変数、またはのような基本的なスカラー型をラップしてい **`int`** ます。 [](../cppcx/platform-object-class.md)

## <a name="passing-a-value-type-to-an-object-parameter"></a>Object^ パラメーターへの値の型の引き渡し

変数を明示的にボックス化しなくても、型 [Platform::Object^](../cppcx/platform-object-class.md)のメソッド パラメーターに渡すことはできますが、以前にボックス化されたことがある値を取得するときは、明示的にキャストして元の型に戻す必要があります。

[!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]

### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Platform:: IBox を使用した \<T> null 許容値型のサポート

C# および Visual Basic では、null 許容値型の概念をサポートしています。 C++/CX では、型を使用し `Platform::IBox<T>` て、null 許容値型パラメーターをサポートするパブリックメソッドを公開できます。 次の例は、C# の呼び出し元が引数の1つに null を渡すときに null を返す C++/CX パブリックメソッドを示しています。

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
[C++/CX 言語リファレンス](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[名前空間のリファレンス](../cppcx/namespaces-reference-c-cx.md)
