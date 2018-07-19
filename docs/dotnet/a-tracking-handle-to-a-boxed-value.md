---
title: ボックス化された値を追跡ハンドル |Microsoft ドキュメント
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
ms.openlocfilehash: 6d3be5a46eab68a7f02bb97c477c1ec0b7fcd54d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33108288"
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>追跡ハンドルからボックス化変換された値へ
値型を参照する追跡ハンドルの使用法は、Visual C を c++ マネージ拡張から変更されました。  
  
 ボックス化とは、統合された CLR 型システムの特性です。 値の型は、参照型は、暗黙の組の中に直接その状態を格納します。 名前付きエンティティは、マネージ ヒープ上に割り当てられた名前のないオブジェクトへのハンドル。 初期化や型の値を割り当てる、 `Object`、たとえば、必要な値の型が - これは、ボックス化の画像は、発生場所 - CLR ヒープ内に配置すること最初、関連付けられているメモリの割り当て、次の値の型の状態をコピーして、この匿名の値の参照/ハイブリッドのアドレスを返すとします。 したがって、ときに 1 つを書き込みます (C#)  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 多く起こっているはによる外見上、わかりやすくするためのコードよりもあります。 C# のデザインには、だけでなく、どのような操作が、内部で行われているが、ボックス化自体の抽象化の複雑さが隠されています。 C++ マネージ拡張、その一方で、懸念の false 感の効率性につながるこれは、明示的な命令を要求することによって、ユーザーの面に配置します。  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 Visual C で暗黙的なボックス化とは。  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 `__box`キーワードは、重要なサービスのいずれかの存在しない場合は、マネージ拡張で c# および Visual Basic などの言語からデザインによって: ボキャブラリと追跡の両方を直接操作すると、マネージ ヒープ上のボックス化されたインスタンスの処理を提供します。 たとえば、次の小さなプログラムがあるとします。  
  
```  
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
  
 3 回の呼び出しで生成された基になるコード`WriteLine`指示された行がそれぞれに関連するオーバーヘッドを表示する (ご協力に感謝していただいた Yves Dolce これらの相違を指す)、入力のボックス化された値にアクセスするさまざまなコストを表示します。呼び出し。  
  
```  
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
  
 ボックス化された値の型を直接渡す`Console::WriteLine`ボックス化とを呼び出す必要がある`ToString()`です。 (当然ながら、初期化するために以前のボックス化がある`br`ため何も実際に配置しない限り、`br`動作をします。  
  
 新しい構文ではボックス化された値の型がサポートかなりより洗練されたに統合されると、型システムの電源を維持したままです。 たとえば、以前のバージョンの小さなプログラムの翻訳を次に示します。  
  
```  
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
 [値の型とその動作 (C + + CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [方法: 明示的にボックス化を要求する](../dotnet/how-to-explicitly-request-boxing.md)