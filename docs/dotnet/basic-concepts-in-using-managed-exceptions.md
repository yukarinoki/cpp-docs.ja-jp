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
ms.openlocfilehash: 4eeec5db00ceca5429f4a3a270e1b249a8955249
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230923"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>マネージド例外の使用についての基本概念

このトピックでは、マネージアプリケーションの例外処理について説明します。 つまり、 **/clr**コンパイラオプションを使用してコンパイルされたアプリケーションです。

## <a name="in-this-topic"></a>このトピックの内容

- [/Clr で例外をスローしています](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR 拡張機能の try/Catch ブロック](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>解説

**/Clr**オプションを使用してコンパイルする場合は、clr 例外を処理できます。また、標準クラスを使用すると、 <xref:System.Exception> clr 例外を処理するための便利なメソッドが多数提供され、ユーザー定義の例外クラスの基本クラスとして使用することをお勧めします。

インターフェイスから派生した例外の種類のキャッチは、 **/clr**ではサポートされていません。 また、共通言語ランタイムでは、スタックオーバーフロー例外をキャッチすることはできません。スタックオーバーフロー例外が発生すると、プロセスが終了します。

マネージアプリケーションとアンマネージアプリケーションの例外処理の相違点の詳細については、「 [Managed Extensions for C++ の例外処理動作の相違点](../dotnet/differences-in-exception-handling-behavior-under-clr.md)」を参照してください。

## <a name="throwing-exceptions-under-clr"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a>/Clr で例外をスローしています

C++ の throw 式は、CLR 型へのハンドルをスローするように拡張されています。 次の例では、カスタムの例外の種類を作成し、その型のインスタンスをスローします。

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

## <a name="trycatch-blocks-for-clr-extensions"></a><a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a>CLR 拡張機能の try/Catch ブロック

**`try`** / **`catch`** CLR とネイティブの両方の例外をキャッチするために、同じブロック構造を使用できます。

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

### <a name="order-of-unwinding-for-c-objects"></a>C++ オブジェクトのアンワインドの順序

アンワインドは、スロー関数と処理関数の間の実行時スタック上にある可能性のあるデストラクターを持つ C++ オブジェクトに対して発生します。 CLR 型はヒープに割り当てられるため、アンワインドは適用されません。

スローされた例外のイベントの順序は次のとおりです。

1. ランタイムは、例外をキャッチするために、適切な catch 句を検索します。または SEH の場合は、SEH のフィルターを除きます。 Catch 句は、最初に構文の順序で検索され、次にコールスタックを動的に停止します。

1. 正しいハンドラーが見つかると、その時点までスタックがアンワインドされます。 スタック上の関数呼び出しごとに、ローカルオブジェクトが破棄されされ、__finally ブロックが、最も入れ子になった外側から実行されます。

1. スタックがアンワインドされると、catch 句が実行されます。

### <a name="catching-unmanaged-types"></a>アンマネージ型のキャッチ

アンマネージオブジェクト型がスローされると、型の例外でラップされ <xref:System.Runtime.InteropServices.SEHException> ます。 適切な句を検索する場合 **`catch`** 、2つの可能性があります。

- ネイティブ C++ 型が検出された場合、例外はラップ解除され、検出された型と比較されます。 この比較により、ネイティブ C++ 型を通常の方法でキャッチできます。

- ただし、 **`catch`** **sehexception**型の句またはその基本クラスのいずれかを最初に検査すると、句によって例外がインターセプトされます。 したがって、ネイティブ C++ 型をキャッチするすべての catch 句は、CLR 型の catch 句の前に配置する必要があります。

次の点に注意してください。

```
catch(Object^)
```

と

```
catch(...)
```

は、SEH 例外を含むスローされた型をキャッチします。

アンマネージ型が catch (Object ^) によってキャッチされた場合、スローされたオブジェクトは破棄されません。

アンマネージ例外をスローまたはキャッチする場合は、 **/ehs**または **/eha**ではなく[/ehsc](../build/reference/eh-exception-handling-model.md)コンパイラオプションを使用することをお勧めします。

## <a name="see-also"></a>関連項目

[例外処理](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[例外処理](../cpp/exception-handling-in-visual-cpp.md)
