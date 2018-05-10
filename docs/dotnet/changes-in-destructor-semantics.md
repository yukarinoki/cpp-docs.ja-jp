---
title: デストラクターのセマンティクスの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finalizers [C++]
- destructors, C++
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 8a3d078300ca0e51ba8eb035d5428d300b0413a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="changes-in-destructor-semantics"></a>デストラクターのセマンティクスの変更
クラスのデストラクターのセマンティクスは大幅に変更マネージ拡張から C++ の Visual C にします。  
  
 マネージ拡張では、参照クラス内にある値クラスがクラスのデストラクターができました。 これは、新しい構文で変更されていません。 ただし、クラスのデストラクターのセマンティクスは変更されています。 このトピックのねらいでの理由を変更して、既存の CLR コードの変換に与える影響について説明します。 2 つのバージョンの言語の間で最も重要なプログラマ向けの変更と考えられます。  
  
## <a name="non-deterministic-finalization"></a>非確定的な終了処理  
 オブジェクトに関連付けられているメモリが関連付けられている、ガベージ コレクターによって回収される前に`Finalize`メソッド、存在する場合が呼び出されます。 オブジェクトのプログラムの有効期間に関連付けられていないことがあるため、一種のスーパー デストラクターとして、このメソッドの考えることができます。 これを最終処理と呼びます。 タイミングときまたはでもだけかどうか、`Finalize`メソッドが呼び出されますが定義されていません。 これは、ガベージ コレクションの非確定的な終了処理動作するときに、次の新機能が意味です。  
  
 非確定的な終了処理は、動的メモリ管理とも連携します。 使用可能なメモリが不足しているになると、ガベージ コレクターが取り込まれます。 ガベージ収集される環境では、空きメモリ容量のデストラクターは必要ありません。 非確定的な終了処理場合機能しません、ただし、オブジェクトがデータベース接続または何らかのロックなどの重要なリソースを維持します。 この場合、そのリソースをできるだけ早くリリースお必要があります。 世界では、ネイティブ、コンス トラクターとデストラクターのペアを使用して実現されます。 オブジェクトの有効期間が終わるとすぐには、デストラクターが呼び出さ内部で宣言されているローカルのブロックの終了時、または、例外がスローされて戻されることによって、スタックしたときと、リソースが自動的に解放します。 このアプローチはあまり、し、そのマネージ拡張でが含まれなかったです。  
  
 CLR によって提供されるソリューションは、実装するクラス、`Dispose`のメソッド、`IDisposable`インターフェイスです。 ここでの問題は`Dispose`がユーザーによって明示的に呼び出す必要があります。 これは、エラーが発生しやすいです。 C# 言語の特殊な形式でのオートメーションのわずかなフォームを提供する`using`ステートメントです。 マネージ拡張のデザインには、特別なサポートが提供されていません。  
  
## <a name="destructors-in-managed-extensions-for-c"></a>C++ マネージ拡張でデストラクター  
 マネージ拡張では、参照クラスのデストラクターは、次の 2 つの手順を使用して実装されます。  
  
1.  ユーザーが指定したデストラクターが内部的に名前が変更`Finalize`です。 クラスは基底クラスにある場合 (CLR オブジェクト モデルでは、単一継承のみがサポートされるを忘れないでください)、コンパイラはユーザーが指定したコードの実行のファイナライザーの呼び出しを挿入します。 たとえば、マネージ拡張言語の仕様から取得した、次の単純な階層があるとします。  
  
```  
__gc class A {  
public:  
   ~A() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   ~B() { Console::WriteLine(S"in ~B");  }  
};  
```  
  
 この例では両方のデストラクターも`Finalize`します。 `B``Finalize`の呼び出しが`A`の`Finalize`追加メソッドの呼び出しの後`WriteLine`です。 これは、どのようなガベージ コレクターが既定では呼び出す終了処理中にします。 この内部変換のようを次に示します。  
  
```  
// internal transformation of destructor under Managed Extensions  
__gc class A {  
public:  
   void Finalize() { Console::WriteLine(S"in ~A"); }  
};  
  
__gc class B : public A {  
public:  
   void Finalize() {   
      Console::WriteLine(S"in ~B");  
      A::Finalize();   
   }  
};  
```  
  
1.  2 番目の手順では、コンパイラは仮想デストラクターを合成します。 このデストラクターは、直接または、削除式のアプリケーションのいずれかに起動する、拡張機能の管理ユーザーのプログラムです。 ガベージ コレクターによっては呼び出されません。  
  
     2 つのステートメントは、この合成デストラクター内に配置します。 呼び出しは、1 つ`GC::SuppressFinalize`のない複数の呼び出しがあることを確認する`Finalize`です。 2 番目の実際の呼び出しは、 `Finalize`、そのクラスのユーザーが指定したデストラクターを表します。 ようになりますがこれを次に示します。  
  
```  
__gc class A {  
public:  
   virtual ~A() {  
      System::GC::SuppressFinalize(this);  
      A::Finalize();  
   }  
};  
  
__gc class B : public A {  
public:  
   virtual ~B() {  
      System::GC::SuppressFinalize(this);  
      B::Finalize();  
   }  
};  
```  
  
 この実装により、ユーザーが明示的にクラスを呼び出すときに`Finalize`メソッドようになりましたなく、コントロールがあるない時にこれは本当に関連付けないで、`Dispose`メソッドのソリューションです。 これは、Visual C で変更されます。  
  
## <a name="destructors-in-new-syntax"></a>新しい構文でデストラクター  
 新しい構文では、デストラクターの名前が変更に内部的には、`Dispose`メソッドと、参照クラスが実装に自動的に拡張、`IDispose`インターフェイスです。 つまり、Visual c は、当社のクラスのペアが変換されるとおり。  
  
```  
// internal transformation of destructor under the new syntax  
__gc class A : IDisposable {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~A");  
   }  
};  
  
__gc class B : public A {  
public:  
   void Dispose() {   
      System::GC::SuppressFinalize(this);  
      Console::WriteLine( "in ~B");    
      A::Dispose();   
   }  
};  
```  
  
 新しい構文では、いずれかのデストラクターが明示的に呼び出すとき、または`delete`が、基になる、追跡ハンドルに適用される`Dispose`メソッドが自動的に呼び出されます。 派生クラスの呼び出しであるかどうか、`Dispose`合成されたメソッドの終了時、基底クラスのメソッドを挿入します。  
  
 しかし、これはいない確定的な終了処理まで。 ですが、接続するためにローカルの参照オブジェクトの追加のサポートが必要です。 (これは、マネージ拡張で相当するサポートしませんおよびではない、変換の問題)。  
  
## <a name="declaring-a-reference-object"></a>参照オブジェクトを宣言します。  
 Visual C でサポート参照クラスのオブジェクトの宣言またはクラスのメンバーとしてローカル スタックに直接アクセスできる場合と同様です。 デストラクターとの関連付けと組み合わせると、`Dispose`メソッド、結果は参照型のセマンティクスは終了処理の自動化された呼び出しです。  
  
 最初に、定義参照クラス オブジェクトの作成は、クラス コンス トラクターを使用して、リソースの取得として機能するようにします。 次に、クラスのデストラクター内でオブジェクトが作成されたときに取得したリソースを解放します。  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // everything else...  
};  
```  
  
 オブジェクトは、付属の hat ことがなく、型名を使用してローカルに宣言されます。 メソッドの呼び出しなど、オブジェクトのすべての使用は、メンバー選択ドットを使用して行われます (`.`) 矢印ではなく (`->`)。 関連付けられているデストラクター、変換をブロックの最後に、 `Dispose`、次のように、自動的に呼び出されます。  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here -  
   // that is, r.Dispose() is invoked  
}  
```  
  
 同様、`using`内 (C#) ステートメントでは、これはいない対立するもので参照型はすべて、基になる CLR の制約は CLR ヒープに割り当てられる必要があります。 基になるセマンティクスは変更されません。 ユーザー同等が書き込まれ、次の (および、これは、コンパイラによって実行される変換の内部で、可能性があります)。  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 実際には、新しい構文では、もう一度としてデストラクターと組み合わせコンス トラクター自動取得/解放メカニズムは、ローカル オブジェクトの有効期間に関連付けられています。  
  
## <a name="declaring-an-explicit-finalize"></a>明示的な Finalize を宣言します。  
 新しい構文ではこれまで見てきたよう、デストラクター、`Dispose`メソッドです。 この、デストラクターが明示的に呼び出されないときに、ガベージ コレクター終了処理中には見つけることを以前と関連付けられている`Finalize`オブジェクトのメソッドです。 破棄、および終了処理の両方をサポートするために、ファイナライザーを提供するための特別な構文が導入されています。 例えば:  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 `!`プレフィックスがチルダと似ています (`~`) クラスのデストラクターを導入する - は、後の有効期間の両方のメソッドがクラスの名前を付けることトークンを取得します。 場合、合成`Finalize`メソッドが派生クラスの基本クラスの呼び出し中に発生`Finalize`メソッドは、最後に挿入します。 デストラクターが明示的に呼び出される場合は、ファイナライザーが抑制されます。 変換のようを次に示します。  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>C++ マネージ拡張から Visual C 2010 へ移動  
 これでコンパイルした Visual C 参照クラスには、非単純デストラクターが含まれている場合、C++ プログラムのマネージ拡張の実行時の動作が変更されます。 必要な変換アルゴリズムは、次のようにします。  
  
1.  デストラクターが存在する場合は、そのクラスのファイナライザーを書き直してください。  
  
2.  場合、`Dispose`メソッド、クラスのデストラクターに書き換えます。  
  
3.  デストラクターはあるがある場合ありません`Dispose`メソッドの最初の項目の実行中にデストラクターを保持します。  
  
 マネージ拡張からコードを移行するには、新しい構文に、この変換の実行を見逃す可能性がします。 アプリケーション依存関係のある何らかの方法で関連付けられている終了処理メソッドの実行時に、アプリケーションの動作はサイレント モードでからが異なる場合、意図したものとします。  
  
## <a name="see-also"></a>関連項目  
 [マネージ型 (C + + CL)](../dotnet/managed-types-cpp-cl.md)   
 [デストラクターとファイナライザーを使用する方法: を定義およびクラスと構造体を使用 (C + + CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)