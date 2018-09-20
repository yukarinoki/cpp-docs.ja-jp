---
title: デストラクターのセマンティクスの変更 |Microsoft Docs
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
ms.openlocfilehash: c25045291afed1e8072867ee668716b2f396ef30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420024"
---
# <a name="changes-in-destructor-semantics"></a>デストラクターのセマンティクスの変更

クラスのデストラクターのセマンティクスが大きく変更されたマネージ拡張から C++ 用 Visual C にします。

マネージ拡張では、クラスのデストラクターは値クラス内にあるが、参照クラスを許可でした。 これは、新しい構文で変更されていません。 ただし、クラスのデストラクターのセマンティクスは変更されています。 このトピックのねらいでの理由を変更して、既存の CLR コードの変換に与える影響について説明します。 2 つのバージョン、言語のプログラマ レベルの最も重要な変更です。

## <a name="non-deterministic-finalization"></a>非確定的な終了処理

オブジェクトに関連付けられているメモリが関連付けられているガベージ コレクターによって回収される前に`Finalize`メソッド、存在する場合は呼び出されます。 オブジェクトのプログラムの有効期間に関連付けられていないため、ある種の特殊なデストラクターとして、このメソッドの考えることができます。 これを終了処理と呼びます。 タイミングとまたはでもだけかどうかを`Finalize`メソッドが呼び出されますが定義されていません。 これは、ガベージ コレクションが非確定的な終了処理を動作を意味します。

非決定論的な終了処理では、動的メモリ管理の連動します。 使用可能なメモリが不足になると、ガベージ コレクターが取り込まれます。 ガベージ メモリを解放するデストラクターは必要な環境を収集します。 非決定論的な終了処理は機能しません、ただし、オブジェクトがデータベース接続やある種のロックなどの重要なリソースを維持する場合。 この場合、そのリソースをできるだけ早くリリースする必要があります。 コンス トラクターとデストラクターのペアを使用して実現されるネイティブ環境。 オブジェクトの有効期間が終了するとすぐに宣言は、ローカルのブロックの終了時に、またはスタックは、例外がスローされて戻されることによってときに、デストラクターが実行し、リソースが自動的に解放されます。 このアプローチは非常にそうと、マネージ拡張ではれなかったのです。

CLR によって提供されるソリューションを実装するクラスは、`Dispose`のメソッド、`IDisposable`インターフェイス。 ここで問題なの`Dispose`ユーザーによって明示的な呼び出しが必要です。 これは、エラーが発生しやすい。 C# 言語の特殊な形式でのオートメーションのわずかなフォームを提供する`using`ステートメント。 マネージ拡張のデザインには、特別なサポートが提供されていません。

## <a name="destructors-in-managed-extensions-for-c"></a>C++ マネージ拡張でデストラクター

マネージ拡張では、参照クラスのデストラクターは、次の 2 つの手順を使用して実装されます。

1. ユーザーが指定したデストラクターの内部で名前が変更`Finalize`します。 クラスは、基本クラスがある場合 (CLR オブジェクト モデルでは、単一継承のみがサポートされているを忘れないでください)、コンパイラはユーザーが指定したコードの実行のファイナライザーの呼び出しを挿入します。 たとえば、マネージ拡張言語仕様から取得した次の単純な階層があるとします。

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

この例では、両方のデストラクターが名前変更`Finalize`します。 `B``Finalize`の呼び出しが`A`の`Finalize`追加メソッドの呼び出しの後`WriteLine`します。 これは、どのようなガベージ コレクターは既定で呼び出す終了処理中にします。 この内部変換のようを次に示します。

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

1. 2 番目の手順では、コンパイラは仮想デストラクターを合成します。 このデストラクターは、直接または削除式のアプリケーションのいずれかに起動する、拡張機能の管理ユーザーのプログラムです。 ガベージ コレクターによっては呼び出されません。

     2 つのステートメントは、この合成デストラクター内に配置されます。 1 つの呼び出しは、`GC::SuppressFinalize`のない複数の呼び出しがあることを確認する`Finalize`します。 2 番目の実際の呼び出しは、 `Finalize`、そのクラスのデストラクターはユーザー指定を表します。 ここではこの可能性がありますようになります。

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

この実装によって、ユーザーをクラスを明示的に呼び出す`Finalize`メソッド今すぐなく、コントロールがあるない時に、本当に結び付けられないで、`Dispose`メソッドのソリューションです。 これは、Visual C で変更されます。

## <a name="destructors-in-new-syntax"></a>新しい構文でデストラクター

新しい構文では、デストラクターの内部で名前が、`Dispose`メソッドと参照クラスが実装するために自動的に拡張、`IDispose`インターフェイス。 つまり、Visual C は、クラスのペアが次のように変換されます。

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

新しい構文では、いずれかのデストラクターが明示的に呼び出すとき、または`delete`トラッキング ハンドルで、基になるに適用される`Dispose`メソッドが自動的に呼び出されます。 呼び出し、派生クラスであるかどうか、`Dispose`合成されたメソッドの終了時、基底クラスのメソッドが挿入されます。

しかし、これはない確定的なファイナライズまで。 接続するためにローカル参照オブジェクトの追加のサポートが必要です。 (これに相当するマネージ拡張でサポートがないとではない変換の問題)。

## <a name="declaring-a-reference-object"></a>参照オブジェクトを宣言します。

Visual C の宣言をサポート参照クラスのオブジェクトまたはクラスのメンバーとしてローカル スタックで直接アクセスできる場合と同様です。 デストラクターの関連付けと組み合わせたときに、`Dispose`メソッド、結果は参照型の終了処理のセマンティクスの自動呼び出し。

最初に、オブジェクトの作成は、そのクラス コンス トラクターを使用して、リソースの取得として機能するよう、参照クラスを定義します。 次に、クラスのデストラクター内でオブジェクトが作成されたときに取得したリソースを解放します。

```
public ref class R {
public:
   R() { /* acquire expensive resource */ }
   ~R() { /* release expensive resource */ }

   // everything else...
};
```

オブジェクトは、付属の hat ことがなく、型名を使用してローカルに宣言されます。 メソッドの呼び出しなど、オブジェクトのすべての使用は、メンバーの選択のドットを使用して行われます (`.`) 矢印ではなく (`->`)。 関連付けられているデストラクターでは、変換をブロックの末尾には、 `Dispose`、次のように、自動的に呼び出されます。

```
void f() {
   R r;
   r.methodCall();

   // r is automatically destructed here -
   // that is, r.Dispose() is invoked
}
```

同様、 `using` c# のステートメントでは、これはいないに挑む参照型はすべて、基になる CLR の制約は CLR ヒープに割り当てられる必要があります。 基になるセマンティクスは変更されません。 ユーザー同等が書き込まれ、次の (および内部に、コンパイラによって行われる変換の可能性が)。

```
// equivalent implementation
// except that it should be in a try/finally clause
void f() {
   R^ r = gcnew R;
   r->methodCall();

   delete r;
}
```

実際には、新しい構文では、デストラクターはもう一度ペアになっているコンス トラクターで自動取得/解放としてメカニズムは、ローカル オブジェクトの有効期間に関連付けられています。

## <a name="declaring-an-explicit-finalize"></a>明示的な Finalize を宣言します。

新しい構文ではこれまで見てきたよう、デストラクター、`Dispose`メソッド。 この、デストラクターが明示的に呼び出されない場合、ガベージ コレクター、終了処理中には見つけることを以前と同様、関連付けられている`Finalize`オブジェクトのメソッド。 破棄および終了処理の両方をサポートするには、ファイナライザーを提供するための特別な構文を導入しました。 例えば:

```
public ref class R {
public:
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }
};
```

`!`プレフィックスはチルダに似ています (`~`) クラスのデストラクターを導入する - 後の有効期間の両方の方法で、クラスの名前を付けることトークンを取得する、します。 場合、合成された`Finalize`メソッドが派生クラス、基底クラスの呼び出し内で発生`Finalize`メソッドは、最後に挿入されます。 デストラクターが明示的に呼び出される場合、ファイナライザーは抑制されます。 次の変換のように示します。

```
// internal transformation under new syntax
public ref class R {
public:
   void Finalize() {
      Console::WriteLine( "I am the R::finalizer()!" );
   }
};
```

## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>Visual C 2010 を c++ マネージ拡張からの移行

参照クラスのデストラクターが自明でない場合、必ず Visual C でコンパイルすると、Managed Extensions for C プログラムの実行時の動作が変更されました。 必要な変換アルゴリズムは、次のような。

1. デストラクターが存在する場合は、クラスのファイナライザーに書き換えます。

1. 場合、`Dispose`メソッドが存在する、クラスのデストラクターに書き換えます。

1. デストラクターが存在するがある場合ありません`Dispose`メソッドでは、最初の項目の実行中にデストラクターを保持します。

マネージ拡張から新しい構文に、コードを移動するには、この変換を実行するを見逃す可能性が。 関連付けられているファイナライズ メソッドの実行に何らかの方法で、アプリケーションが依存して、アプリケーションの動作は意図したものからサイレントが異なります。

## <a name="see-also"></a>関連項目

[マネージ型 (C +/cli CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[方法のデストラクターおよびファイナライザー: クラスと構造体定義および使用 (C +/cli CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)