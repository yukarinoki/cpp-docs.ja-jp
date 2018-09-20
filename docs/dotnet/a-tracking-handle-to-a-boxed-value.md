---
title: 追跡ハンドルからボックス化された値へ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c7e26efae93b509700c3bb0c992d9f397559e99f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380731"
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>追跡ハンドルからボックス化変換された値へ

参照値の型の追跡ハンドルの使用状況は、Visual c の C++ マネージ拡張から変更されました。

ボックス化とは、統合された CLR 型システムの特性です。 値の型は、参照型は暗黙的なペアを直接その状態を格納します。 名前付きエンティティが、マネージ ヒープで割り当てられた名前のないオブジェクトを識別するハンドル。 初期化や型の値の割り当て、 `Object`、たとえば、まず必要があります、値の型が、-、ボックス化のイメージが発生したは、CLR ヒープ内に配置すること、関連付けられているメモリを割り当てることによって、値型の状態をコピーして、し、この匿名の値の参照/ハイブリッドのアドレスを返すとします。 C# で書き込むいずれかの場合このため、

```cpp
object o = 1024; // C# implicit boxing
```

コードの簡潔さによって明らかにされますよりも大幅に向上します。 C# のデザインには、だけでなく、内部的には、どのような操作が起きているが、ボックス化自体の抽象化の複雑さが隠蔽されます。 マネージ効率感が false になります、明示的な指示を要求することによって、ユーザーの顔にこのことに気を C++ では、その一方で、拡張します。

```cpp
Object *o = __box( 1024 ); // Managed Extensions explicit boxing
```

Visual C で暗黙的なボックス化とは。

```cpp
Object ^o = 1024; // new syntax implicit boxing
```

`__box`キーワードが重要なサービスのいずれかの存在しない場合は、マネージ拡張では機能 c# および Visual Basic などの言語から設計: マネージ ヒープ上のボックス化されたインスタンスを直接操作するためのボキャブラリと追跡の両方の処理を提供します。 たとえば、次の小さなプログラムがあるとします。

```cpp
int main() {
   double result = 3.14159;
   __box double * br = __box( result );

   result = 2.7;
   *br = 2.17;
   Object * o = br;

   Console::WriteLine( S"result :: {0}", result.ToString() ) ;
   Console::WriteLine( S"result :: {0}", __box(result) ) ;
   Console::WriteLine( S"result :: {0}", br );
}
```

3 回の呼び出しで生成された基になるコード`WriteLine`指示された行がそれぞれに関連するオーバーヘッドを表示する (くれたいただいた Yves Dolce これらの相違点を指摘)、入力のボックス化された値の値にアクセスするさまざまなコストを表示します。呼び出し。

```cpp
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;
ldstr      "result :: {0}"
ldloca.s   result  // ToString overhead
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead
call       void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", __box(result) ) ;
Ldstr    " result :: {0}"
ldloc.0
box    [mscorlib]System.Double // box overhead
call    void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", br );
ldstr    "result :: {0}"
ldloc.0
call     void [mscorlib]System.Console::WriteLine(string, object)
```

ボックス化された値の型に直接渡す`Console::WriteLine`、ボックス化と呼び出す必要がある`ToString()`します。 (もちろん、初期化するために以前のボックス化がある`br`ため何か本当に配置しない限り、`br`させる。

新しい構文では、ボックス化された値の型のサポートは、その力を維持しながら非常に洗練された、型システム内で統合です。 たとえば、以前の小さなプログラムの変換は、次に示します。

```cpp
int main()
{
   double result = 3.14159;
   double^ br = result;
   result = 2.7;
   *br = 2.17;
   Object^ o = br;
   Console::WriteLine( "result :: {0}", result.ToString() );
   Console::WriteLine( "result :: {0}", result );
   Console::WriteLine( "result :: {0}", br );
}
```

## <a name="see-also"></a>関連項目

[値型とその動作 (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[方法: 明示的にボックス化を要求する](../dotnet/how-to-explicitly-request-boxing.md)