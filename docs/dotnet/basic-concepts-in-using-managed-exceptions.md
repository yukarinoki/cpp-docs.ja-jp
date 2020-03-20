---
title: マネージド例外の使用についての基本概念
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: cf241d4e599ad58c2e39680d8ed4e4e250b42b18
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/10/2019
ms.locfileid: "79545379"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>マネージド例外の使用についての基本概念

このトピックでは、マネージアプリケーションの例外処理について説明します。 つまり、 **/clr**コンパイラオプションを使用してコンパイルされたアプリケーションです。

## <a name="in-this-topic"></a>このトピックの内容

- [/Clr で例外をスローしています](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR 拡張機能の try/Catch ブロック](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>コメント

**/Clr**オプションを使用してコンパイルする場合は、clr 例外だけでなく、標準 <xref:System.Exception> クラスにも clr 例外を処理するための便利なメソッドが多数用意されており、ユーザー定義の例外クラスの基本クラスとして推奨されています。

インターフェイスから派生した例外の種類のキャッチは、 **/clr**ではサポートされていません。 また、共通言語ランタイムでは、スタックオーバーフロー例外をキャッチすることはできません。スタックオーバーフロー例外が発生すると、プロセスが終了します。

マネージアプリケーションとアンマネージアプリケーションの例外処理の相違点の詳細については、「 [ C++のマネージ拡張機能での例外処理動作の相違点](../dotnet/differences-in-exception-handling-behavior-under-clr.md)」を参照してください。

##  <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/Clr で例外をスローしています

Throw C++式は、CLR 型へのハンドルをスローするように拡張されています。 次の例では、カスタムの例外の種類を作成し、その型のインスタンスをスローします。

```cpp
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

値型は、スローされる前にボックス化する必要があります。

```cpp
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

##  <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR 拡張機能の try/Catch ブロック

CLR とネイティブの両方の例外をキャッチするために、同じ**try**/**catch**ブロック構造を使用できます。

```cpp
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>出力

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>オブジェクトのC++アンワインドの順序

アンワインドはC++ 、スロー関数と処理関数の間の実行時スタックにあるデストラクターを持つオブジェクトに対して発生します。 CLR 型はヒープに割り当てられるため、アンワインドは適用されません。

スローされた例外のイベントの順序は次のとおりです。

1. ランタイムは、例外をキャッチするために、適切な catch 句を検索します。または SEH の場合は、SEH のフィルターを除きます。 Catch 句は、最初に構文の順序で検索され、次にコールスタックを動的に停止します。

1. 正しいハンドラーが見つかると、その時点までスタックがアンワインドされます。 スタック上の各関数呼び出しについては、そのローカルのオブジェクトが破棄され、ブロックが実行される __finally、ほとんどの外側に入れ子になった。

1. スタックがアンワインドされると、catch 句が実行されます。

### <a name="catching-unmanaged-types"></a>アンマネージ型のキャッチ

アンマネージオブジェクト型がスローされると、<xref:System.Runtime.InteropServices.SEHException>型の例外でラップされます。 適切な**catch**句を検索する場合、2つの可能性があります。

- ネイティブC++型が検出されると、例外がラップ解除され、検出された型と比較されます。 この比較により、 C++ネイティブ型を通常の方法でキャッチできます。

- ただし、 **Sehexception**型またはその基本クラスのいずれかの**catch**句が最初に検査された場合、句は例外を受け取ります。 したがって、ネイティブC++型をキャッチするすべての catch 句は、CLR 型の catch 句の前に配置する必要があります。

次の点に注意してください。

```
catch(Object^)
```

and

```
catch(...)
```

は、SEH 例外を含むスローされた型をキャッチします。

アンマネージ型が catch (Object ^) によってキャッチされた場合、スローされたオブジェクトは破棄されません。

アンマネージ例外をスローまたはキャッチする場合は、 **/ehs**または **/eha**ではなく[/ehsc](../build/reference/eh-exception-handling-model.md)コンパイラオプションを使用することをお勧めします。

## <a name="see-also"></a>参照

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[例外処理](../cpp/exception-handling-in-visual-cpp.md)
