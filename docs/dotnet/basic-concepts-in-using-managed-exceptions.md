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
ms.openlocfilehash: b4eb74fe3e485f12ac7f43b0a8a56800ef0535e7
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423847"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>マネージド例外の使用についての基本概念

このトピックでは、マネージ アプリケーションでの例外処理について説明します。 つまり、アプリケーションでコンパイルされる、 **/clr**コンパイラ オプション。

## <a name="in-this-topic"></a>このトピックの内容

- [/Clr での例外をスローします。](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [CLR の拡張機能の Try/catch ブロック](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>Remarks

コンパイルする場合、 **/clr**オプション、標準と CLR の例外を処理できる<xref:System.Exception>クラスは、CLR の例外を処理するための多くの便利なメソッドを提供し、ユーザー定義の例外の基底クラスとしてはお勧めしますクラス。

インターフェイスから派生した例外の種類のキャッチはサポートされていません **/clr**します。 また、共通言語ランタイムは許可されていません。 スタック オーバーフローの例外をキャッチするにはスタック オーバーフロー例外は、プロセスを終了します。

マネージ コードとアンマネージ アプリケーションでの例外処理の相違点の詳細については、次を参照してください。[例外処理動作のマネージ拡張で C++ の相違](../dotnet/differences-in-exception-handling-behavior-under-clr.md)します。

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> /Clr での例外をスローします。

CLR 型を識別するハンドルをスローする、C++ throw 式が拡張されます。 次の例では、カスタム例外型を作成し、し、その型のインスタンスがスローされます。

```
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

値の型は、スローされる前にボックス化する必要があります。

```
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

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> CLR の拡張機能の Try/catch ブロック

同じ**お試しください**/**キャッチ**CLR とネイティブの例外の両方をキャッチするためのブロック構造を使用できます。

```
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

スロー関数と処理関数の間、ランタイム スタックで可能性のあるデストラクターに C++ オブジェクトのアンワインドが発生します。 CLR 型がヒープに割り当てられている、ため、アンワインドはそれらに適用されません。

スローされた例外のイベントの順序は次のとおりです。

1. ランタイムが検索または seh を使う場合、適切な catch 句のスタックを走査、フィルター、例外をキャッチする、SEH を除く。 Catch 句構文の順序で最初に検索し、下へ動的に呼び出し履歴。

1. 適切なハンドラーが見つかったら、スタックがそのポイントにアンワインドされます。 スタック上の各関数呼び出しについては、そのローカルのオブジェクトが破棄され、ブロックが実行される _ _finally、ほとんどの外側に入れ子になった。

1. スタックがアンワインドされると、catch 句が実行されます。

### <a name="catching-unmanaged-types"></a>アンマネージ型をキャッチします。

非管理対象のオブジェクトの種類がスローされたときに、型の例外でラップ<xref:System.Runtime.InteropServices.SEHException>します。 適切な検索するときに**キャッチ**句では、2 つの可能性があります。

- ネイティブ C++ の型が発生した場合、例外がラップ解除され、検出された型と比較します。 この比較により、通常の方法でキャッチするネイティブ C++ の型。

- ただし場合、**キャッチ**型の句**SEHException**またはその基本クラスのいずれかが最初に調べられ、句は、例外をインターセプトします。 そのため、いずれかの catch 句の CLR 型の前に、まずネイティブ C++ の型をキャッチするすべての catch 句を配置する必要があります。

次の点に注意してください。

```
catch(Object^)
```

と、呼び出し

```
catch(...)
```

両方の SEH 例外を含む任意のスローされた型をキャッチします。

アンマネージ型は catch(Object^) によってキャッチされました、放り投げたオブジェクトは破棄されません。

使用することをお勧めスローおよびキャッチする例外をアンマネージ、時に、 [/EHsc](../build/reference/eh-exception-handling-model.md)コンパイラ オプションの代わりに **/EHs**または **/EHa**します。

## <a name="see-also"></a>関連項目

[例外処理](../windows/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../windows/safe-cast-cpp-component-extensions.md)<br/>
[例外処理](../cpp/exception-handling-in-visual-cpp.md)